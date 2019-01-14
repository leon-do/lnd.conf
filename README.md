```
# lnd.conf
# sudo iptables -A INPUT -p tcp --dport 10009 -j ACCEPT

bitcoin.node=bitcoind
bitcoin.active=1
bitcoin.mainnet=1
bitcoind.rpcuser=user-name-here-9348752345
bitcoind.rpcpass=user-passowrd-here-3462346
bitcoind.zmqpubrawblock=tcp://127.0.0.1:28332
bitcoind.zmqpubrawtx=tcp://127.0.0.1:28333
debuglevel=info

rpclisten=0.0.0.0:10009
```

```
# bitcoin.conf
# sudo iptables -A INPUT -p tcp --dport 8332 -j ACCEPT

#ligthning shit
zmqpubrawblock=tcp://127.0.0.1:28332
zmqpubrawtx=tcp://127.0.0.1:28333


# server=1 tells Bitcoin-Qt and bitcoind to accept JSON-RPC commands
server=1

# On client-side, you add the normal user/password pair to send commands:
rpcuser=user-name-here-9348752345
rpcpassword=user-passowrd-here-3462346

rpcallowip=192.168.0.5

```

![](https://i.imgur.com/Hk9S9DJ.png)

```
const Client = require('bitcoin-core')

const bitcoin = new Client({
    host: '192.168.0.7',
    port: 18332,
    username: 'user-name-here-9348752345',
    password: 'user-passowrd-here-3462346'
});

start()
async function start() {
  const balance = await bitcoin.getBalance('*', 0);
  console.log({balance})

  const address = await bitcoin.command('getnewaddress')
  console.log({address})
}
```

`https://dev.lightning.community/tutorial/01-lncli/`
