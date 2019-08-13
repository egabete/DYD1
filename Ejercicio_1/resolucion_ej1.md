## Ejericio 1

- Instalar el cliente GETH y sus dependencias siguiendo las instrucciones del siguiente link:
https://github.com/ethereum/go-ethereum/wiki/Installation-Instructions-for-Ubuntu

- Una vez instalemos todo podremos ver la version instalada ejecutando el comando
`geth --version`

![geth version](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/geth_version.png)

- Creamos el archivo genesis segun se indica en https://github.com/ethereum/go-ethereum

        {
            "config": {
            "chainId": 0,
            "homesteadBlock": 0,
            "eip155Block": 0,
            "eip158Block": 0
            },
            "alloc": {
                "0x0000000000000000000000000000000000000001": {
                    "balance": "111111100"
                },
                "0x0000000000000000000000000000000000000002": {
                    "balance": "222222200"
                } //generamos 2 cuentas iniciales con tokens preasignados
            },
            "coinbase": "0x0000000000000000000000000000000000000000",
            "difficulty": "0x20000",
            "extraData": "",
            "gasLimit": "0x2fefd8",
            "nonce": "0x0000000000000028", //cambiamos el nonce por recomendacion
            "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
            "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
            "timestamp": "0x00"
        }

![geth init](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/geth_init.png)

- Utilizamos el comando `geth account new` para crear una cuenta en el nodo.

![accountnew](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/accountnew.png)

- También podemos hacerlo, iniciando la consola con el comanto `geth console`

![console](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/console.png)

- y ejecutando el comando `personal.newAccount()` con el que generamos una nueva cuenta en la blockchain.

![personal.newAccount](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/personal_newaccount.png)

- Luego seteamos una de las cuentas como coinbase utilizando el comando `geth --etherbase '0xE841a546949D768234471dA3A38458238736F9D4'`

- Iniciamos la consola y validamos que la cuenta configurada es correcta usando el comando `eth.coinbase`

![eth.accounts](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/ethaccounts.png)

- Luego iniciamos el minado en el nodo con el comando `miner.start` desde la consola:

![miner.start](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/minerstart.png)

- y vemos como se minan los bloques:

![minado](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/minado_block1to5.png)


![minado](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/minado_block152to157.png)

- Finalmente paramos el minado con el comando `miner.stop` y comprobamos el saldo en la cuenta con el comando `eth.getBalance(eth.coinbase)`

![minado](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/ethgetbalance.png)

******











