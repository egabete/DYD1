# PEC 2
## EJERCICIO 4




### PASO 1
-   Primero debemos preparar el entorno para poder realizar el ejercicio. Para esto necesitamos:
    1.   Iniciar nodo Rinkeby. Para este punto vamos a usar el comando `geth --rinkeby`

    imagen

    2.   Iniciar consola Geth. Para este punto vamos a usar el comando `geth --rinkeby attach`. Además nos aseguramos que el nodo está sincronizado con el comando `eth.syncing` y luego chequeamos el address que está seteado en el nodo con el comando `eth.coinbase`

    imagen

    3.   Cargar el archivo `ensutils-testnet-rinkeby.js`. Para este punto usamos el comando `loadScript('/home/esteban/Downloads/ensutils-testnet-rinkeby.js')`. En este punto también chequeamos que esta correctamente conectado consultando el estado de un dominio registrado previamente en la PEC "estebanabete.test" con el comando `new Date(testRegistrar.expiryTimes(web3.sha3('estebanabete.test')).toNumber()*1000)`.
    
    imagen
    
    - También usamos el comando `ens.owner(namehash('estebanabete.test'))` para validar que el owner coincide con nuestro address.

    imagen


    4.   Iniciar demonio Swarm. Para esto vamos a usar el comando `swarm --datadir "/home/esteban/.ethereum/rinkeby/" --bzzaccount "0x4ddfc2578142b73d5990a2906c38a27858462931" --keystore "/home/esteban/.ethereum/rinkeby/keystore"`

    imagen


### PASO 2
-   Ahora que tenemos los elementos inicializados y preparados podemos comenzar a realizar la práctica. Primero subimos la carpeta con la DAPP. La misma carpeta que para el Ejericio_1.
Para esto vamos a usar el siguiente comando:
`swarm --recursive --defaultpath /home/esteban/Documents/Disenio-y-Desarrollo/PEC_2/Ejercicio_2/pet_shop_example/dist/src/index.html up --encrypt /home/esteban/Documents/Disenio-y-Desarrollo/PEC_2/Ejercicio_2/pet_shop_example/dist`

imagen

- Ahora validamos si la aplicacion subio correctamente y podemos interactuar. Para esto además hemos activado Ganache con la blockchain del ejercicio anterior.






  ![filename](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/filename.png)