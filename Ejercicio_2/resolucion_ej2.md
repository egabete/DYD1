## Ejericio 2

#Enunciado

1. A partir del ejercicio anterior, cree una nueva cuenta en su blockchain. Realice mediante el propio cliente Geth una transferencia de 1 Ether entre dos cuentas de esta blockchain
2. Realice mediante la consola de Truffle y conectado a una blockchain desplegada con Ganache una transferencia de 1 Ether entre dos cuentas de esta blockchain. Puede aprovechar el entorno creado en la actividad primera del bloque1 (​TrufflePet Shop​).

#Resolucion

- Teniendo ya nuestra blockchain, procedemos a generar una nueva cuenta con el comando `geth account new`

![geth account new2](https://github.com/egabete/DYD1/blob/master/Ejercicio_2/img/gethaccountnew2.png)

Como podemos ver hemos generado una nueva cuenta, la cual tiene la siguiente direccion publica: 0x58aA86f0a91fA138F3deADbc854Fb3977269dF5c

Con el comando `geth account list` podemos ver todas las cuentas que se han creado:

![geth account list](https://github.com/egabete/DYD1/blob/master/Ejercicio_2/img/gethaccountlist.png)

Podemos tambien validar el saldo de cada una de las cuentas, iniciando la consola y utilizando el comando `eth.balance`:

![eth.balance](https://github.com/egabete/DYD1/blob/master/Ejercicio_2/img/ethbalance.png)

Podemos ver que la cuenta utilizada para minar tiene un saldo de 820 ETH

![eth.balance](https://github.com/egabete/DYD1/blob/master/Ejercicio_2/img/fromweitoether.png)

y el resto tienen 0.

Con está informaciión lo que nos planteamos es hacer una transferencia de 1 ETH desde la cuenta coinbase con saldo positivo `0xE841a546949D768234471dA3A38458238736F9D4`, hacia la cuenta creada en el ejercicio `0x58aA86f0a91fA138F3deADbc854Fb3977269dF5c`.
Para esto vamos a usar el comando `eth.sendTransaction`, pero primero necesitamos desbloquear la cuenta de emision con el comando `personal.unlockAccount`


eth.sendTransaction({from: '0xE841a546949D768234471dA3A38458238736F9D4', to: '0x58aA86f0a91fA138F3deADbc854Fb3977269dF5c', value: web3.toWei(1, "ether")})



- 









