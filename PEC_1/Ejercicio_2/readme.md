## Ejericio 2

### Enunciado

1. A partir del ejercicio anterior, cree una nueva cuenta en su blockchain. Realice mediante el propio cliente Geth una transferencia de 1 Ether entre dos cuentas de esta blockchain
2. Realice mediante la consola de Truffle y conectado a una blockchain desplegada con Ganache una transferencia de 1 Ether entre dos cuentas de esta blockchain. Puede aprovechar el entorno creado en la actividad primera del bloque1 (​TrufflePet Shop​).

# Resolucion Punto 1

- Al querer realizar la transferencia de Ether esto no fue posible por lo que despues de intentar resolver el problema de la blockchain iniciada, procedi a generar una nueva blockchain.
1. Generè un nuevo archivo genesis:

~~~
{
    "config": {
      "chainId": 2018,
      "homesteadBlock": 0,
      "eip155Block": 0,
      "eip158Block": 0
    },
  
    "alloc"      : {},
    "coinbase"   : "0x0000000000000000000000000000000000000000",
    "difficulty" : "0x400",
    "extraData"  : "",
    "gasLimit"   : "0x2fefd8",
    "nonce"      : "0x0000000000000042",
    "mixhash"    : "0x0000000000000000000000000000000000000000000000000000000000000000",
    "parentHash" : "0x0000000000000000000000000000000000000000000000000000000000000000",
    "timestamp"  : "0x00"
  }
~~~ 

2. Generé una nueva carpeta limpia para guardar la información de la blockchain y luego procedi a iniciarla con el comando `geth --datadir ./new_blockchain init genesis.json`

![newblockchain_init](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/newblockchain_init.png)

3. Luego generamos 2 cuentas con el comando `geth --datadir ./new_blockchain account new`. Por default la primera fue seteada como coinbase y luego iniciamos la consola con el comando `geth --datadir ./new_blockchain console`

![newblockchain_console](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/newblockchain_console.png)

4. Una vez iniciada la consola comprobamos la creación de las 2 cuentas con el comando `eth.accounts` e iniciamos el minado, con el comando `miner.start(1)`, para conseguir ethers para poder hacer la transferencia.

![newblockchain_accounts_miner](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/newblockchain_accounts_miner.png)

5. Detenemos el minado con el comando `miner.stop()` y validamos si ya tenemos saldo para realizar la transferencia con el comando `eth.getBalance(eth.accounts[0])`

![newblockchain_balance](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/newblockchain_balance.png)

6. Con el minado detenido, ejecutamos la transaccion y validamos el saldo, sin embargo no vemos ningun cambio debido a que el minado está detenido y no se ha agregado la transaccion a ningún bloque, por lo que tampoco fue ejecutado el comando en la EVM para efectuar la transaccion entre las cuentas. Previo a la transaccion debimos desbloquear la cuenta con el comando `personal.unlockAccount(eth.accounts[0],"password")`, siendo "password" la contraseña utilizada para crear la cuenta.

![newblockchain_transaccion](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/newblockchain_balance.png)

7. Finalmente reiniciamos el minado y volvemos a ejecutar una transaccion. Ahora al validar el salldo podemos ver que es de 2 ETH, lo cual corresponde a las 2 transacciones realizadas.

![neweblockchain_transaccion2](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/newblockchain_balance.png)


# Resolucion Punto 2

Ya con el entorno de truffle montado en el ejercicio del pet-shop iniciamos primero Ganache 

![ganache](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/ganache.png)

y luego iniciamos la consola de truffle con el comando `truffle console`

![truffle_console](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/truffle_console.png)

Luego revisamos la lista de las cuentas disponibles con el comando `web3.eth.getAccounts`

![web3_eth_getAccounts](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/web3_eth_getAccounts.png)

Elegimos 2 cuentas, revisamos su saldo con el comando `web3.eth.getBalance` y luego realizamos la transaccion con el comando `web3.eth.sendTransaction` con sus correspondientes paràmetros principales: desde que cuenta (from), hacia que cuenta (to) y cuanto se va a transferir (value)

Finalmente volvemos a comprobar el saldo de las cuentas para validar que la transferencia efectivamente fue realizada:

![transaction](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/transaction.png)


