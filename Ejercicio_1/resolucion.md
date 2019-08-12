## Ejericio 1

- Instalar el cliente GETH y sus dependencias siguiendo las instrucciones del siguiente link:
https://github.com/ethereum/go-ethereum/wiki/Installation-Instructions-for-Ubuntu

- Una vez instalemos todo podremos ver la version instalada ejecutando el comando
geth --help

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

![geth version](https://github.com/egabete/DYD1/blob/master/Ejercicio_1/img/geth_init.png)

