# Download the Certificate Tool
curl -sO https://packages.wazuh.com/4.3/wazuh-certs-tool.sh
curl -sO https://packages.wazuh.com/4.3/config.yml

# Configure the Nodes
# Edit the config.yml to define the Wazuh indexer, server, and dashboard nodes:
cat <<EOF > config.yml
nodes:
  # Wazuh indexer nodes
  indexer:
    - name: node-1
      ip: <indexer-node-ip>
    # - name: node-2
    #   ip: <indexer-node-ip>
    # - name: node-3
    #   ip: <indexer-node-ip>

  # Wazuh server nodes
  server:
    - name: wazuh-1
      ip: <wazuh-manager-ip>

  # Wazuh dashboard node
  dashboard:
    - name: dashboard
      ip: <dashboard-node-ip>
EOF

# Generate Certificates
# For a Single Node:
./wazuh-certs-tool.sh

# For Multiple Nodes:
bash ./wazuh-certs-tool.sh -A

# Package the certificates into a tar archive
tar -cvf ./wazuh-certificates.tar -C ./wazuh-certificates/ .

# Install Wazuh Indexer
apt-get -y install wazuh-indexer

# Install the GPG Key
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import && chmod 644 /usr/share/keyrings/wazuh.gpg

# Add the Repository
echo "deb [signed-by=/usr/share/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list

# Update Package Information
apt-get update

# Verify the Certificates
openssl x509 -subject -nameopt RFC2253 -noout -in hostname.pem
