# Azure node for strong signal

#Command to generate config.
$ cd /home/ubuntu/node1

$ geth --syncmode "fast" --cache 4096 --maxpeers 200 --datadir /home/ubuntu/node1 --http --http.addr 0.0.0.0 --http.corsdomain '*' --http.api personal,admin,eth,net,web3,txpool,debug --ws --ws.addr 0.0.0.0 --ws.origins '*' --ws.api personal,admin,eth,net,web3,txpool,debug --ethstats CT247A1:STRONG4EVER@strongstats.mortysnode.nl:3000 --nousb dumpconfig > config.toml

$ cd /home/ubuntu/node2

$ geth --syncmode "fast" --cache 4096 --maxpeers 200 --datadir /home/ubuntu/node2 --http --http.addr 0.0.0.0 --http.corsdomain '*' --http.api personal,admin,eth,net,web3,txpool,debug --ws --ws.addr 0.0.0.0 --ws.origins '*' --ws.api personal,admin,eth,net,web3,txpool,debug --ethstats CT247A2:STRONG4EVER@strongstats.mortysnode.nl:3000 --nousb dumpconfig > config.toml


