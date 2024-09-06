**Download the Certificate Tool**
   To secure the communication between components:
   ```bash
   curl -sO https://packages.wazuh.com/4.3/wazuh-certs-tool.sh
   curl -sO https://packages.wazuh.com/4.3/config.yml
Configure the Nodes Edit the config.yml to define the Wazuh indexer, server, and dashboard nodes:

yaml
Copy code
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
Generate Certificates Run the certificate tool to generate certificates for secure communication between the nodes:

For a single node:

bash
Copy code
./wazuh-certs-tool.sh
For multiple nodes:

bash
Copy code
bash ./wazuh-certs-tool.sh -A
tar -cvf ./wazuh-certificates.tar -C ./wazuh-certificates/ .
Install Wazuh Indexer

bash
Copy code
apt-get -y install wazuh-indexer
Install the GPG Key

bash
Copy code
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import && chmod 644 /usr/share/keyrings/wazuh.gpg
Add the Repository

bash
Copy code
echo "deb [signed-by=/usr/share/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list
Update Package Information

bash
Copy code
apt-get update
Verify the Certificates You can verify the certificate common name (CN) with the following command:

bash
Copy code
openssl x509 -subject -nameopt RFC2253 -noout -in hostname.pem
