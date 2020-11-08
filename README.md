# Azure node for strong signal

# Clone this repo at home directory (/home/ubuntu):
$ git clone https://github.com/sudhirpoodar/ether-node.git

# Change branch to azure node
$ git checkout azure-node

# Run below command to move file to their location
$ mv /home/ubuntu/ether-node/node1 /home/ubuntu/node1
$ mv /home/ubuntu/ether-node/node2 /home/ubuntu/node2
$ mv /home/ubuntu/ether-node/html /var/www/html
$ sudo mv /home/ubuntu/node1/geth1.service /etc/systemd/system/
$ sudo mv /home/ubuntu/node2/geth2.service /etc/systemd/system/
$ sudo systemctl daemon-reload

# Command to generate config.(OPTIONAL STEP)

$ cd /home/ubuntu/node1

$ geth --syncmode "fast" --cache 4096 --maxpeers 200 --datadir /home/ubuntu/node1 --http --http.addr 0.0.0.0 --http.corsdomain '*' --http.api personal,admin,eth,net,web3,txpool,debug --ws --ws.addr 0.0.0.0 --ws.origins '*' --ws.api personal,admin,eth,net,web3,txpool,debug --ethstats CT247A1:STRONG4EVER@strongstats.mortysnode.nl:3000 --nousb dumpconfig > config.toml

$ cd /home/ubuntu/node2

$ geth --syncmode "fast" --cache 4096 --maxpeers 200 --datadir /home/ubuntu/node2 --http --http.addr 0.0.0.0 --http.port 9545 --http.corsdomain '*' --http.api personal,admin,eth,net,web3,txpool,debug --ws --ws.addr 0.0.0.0 --ws.port 9546 --ws.origins '*' --ws.api personal,admin,eth,net,web3,txpool,debug --ethstats CT247A2:STRONG4EVER@strongstats.mortysnode.nl:3000 --nousb dumpconfig > config.toml

# Command to start geth services.

$ sudo systemctl start geth1.service
$ sudo systemctl status geth2.service
