## Ejericio 2

### Enunciado

1. A partir del ejercicio anterior, cree una nueva cuenta en su blockchain. Realice mediante el propio cliente Geth una transferencia de 1 Ether entre dos cuentas de esta blockchain
2. Realice mediante la consola de Truffle y conectado a una blockchain desplegada con Ganache una transferencia de 1 Ether entre dos cuentas de esta blockchain. Puede aprovechar el entorno creado en la actividad primera del bloque1 (​TrufflePet Shop​).

# Resolucion Punto 1

- Teniendo ya nuestra blockchain, procedemos a generar una nueva cuenta con el comando `geth account new`

![geth account new2](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/gethaccountnew2.png)

Como podemos ver hemos generado una nueva cuenta, la cual tiene la siguiente direccion publica: 0x58aA86f0a91fA138F3deADbc854Fb3977269dF5c

Con el comando `geth account list` podemos ver todas las cuentas que se han creado:

![geth account list](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/gethaccountlist.png)

Podemos tambien validar el saldo de cada una de las cuentas, iniciando la consola y utilizando el comando `eth.balance`:

![eth.balance](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/ethbalance.png)

Podemos ver que la cuenta utilizada para minar tiene un saldo de 820 ETH

![eth.balance](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/fromweitoether.png)

y el resto tienen 0.

Con está informaciión lo que nos planteamos es hacer una transferencia de 1 ETH desde la cuenta coinbase con saldo positivo `0xE841a546949D768234471dA3A38458238736F9D4`, hacia la cuenta creada en el ejercicio `0x58aA86f0a91fA138F3deADbc854Fb3977269dF5c`.
Para esto vamos a usar el comando `eth.sendTransaction`, pero primero necesitamos desbloquear la cuenta de emision con el comando `personal.unlockAccount`


eth.sendTransaction({from: '0xE841a546949D768234471dA3A38458238736F9D4', to: '0x58aA86f0a91fA138F3deADbc854Fb3977269dF5c', value: web3.toWei(1, "ether")})

Punto incompleto !!

# Resolucion Punto2

Ya con el entorno de truffle montado en el ejercicio del pet-shop iniciamos primero Ganache 

![ganache](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/ganache.png)

y luego iniciamos la consola de truffle con el comando `truffle console`

![truffle_console](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/truffle_console.png)

Luego revisamos la lista de las cuentas disponibles con el comando `web3.eth.getAccounts`

![web3_eth_getAccounts](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/web3_eth_getAccounts.png)

Elegimos 2 cuentas, revisamos su saldo con el comando `web3.eth.getBalance` y luego realizamos la transaccion con el comando `web3.eth.sendTransaction` con sus correspondientes paràmetros principales: desde que cuenta (from), hacia que cuenta (to) y cuanto se va a transferir (value)

Finalmente volvemos a comprobar el saldo de las cuentas para validar que la transferencia efectivamente fue realizada:

![transaction](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_2/img/transaction.png)


