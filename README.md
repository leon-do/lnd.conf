```
# sudo iptables -A INPUT -p tcp --dport 10009 -j ACCEPT

bitcoin.node=bitcoind
bitcoin.active=1
bitcoin.mainnet=1
bitcoind.rpcuser=user-name-here
bitcoind.rpcpass=user-passowrd-here
bitcoind.zmqpubrawblock=tcp://127.0.0.1:28332
bitcoind.zmqpubrawtx=tcp://127.0.0.1:28333
debuglevel=info

rpclisten=0.0.0.0:10009
```
