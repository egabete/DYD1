# PEC 2
## EJERCICIO 1

- Primero procedemos a iniciar un nodo de Rinkeby en local con el comando `geth --rinkeby ` y a continuación en otra ventana de terminal utilizamos el comando `geth --rinkeby attach` para abrir la consola:

  ![geth_rinkeby_start](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_1/img/geth_rinkeby_start.png)

  ![geth_console](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_1/img/geth_console.png)


- Luego nos aseguramos que el nodo está en sync con la red ejecutando el comando `eth.syncing`

  ![eth_syncing](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_1/img/eth_syncing.png)

- Luego debemos descargar el archivo `ensutils-testnet.js`. Este archivo viene configuradon para la red Ropsten, por lo que para trabajar con la red Rinkeby, debemos modificar lo siguiente:

    ~~~
    contract address: 0xe7410170f87102df0055eb195163a03b7f2bff4a (line 220)
    publicResolver address: 0x5d20cf83cb385e06d2f2a892f9322cd4933eacdc (line 1314)
    ~~~

- Una vez incluimos estos cambios guardamos el archivo como `ensutils-testnet-rinkeby.js` para evitar inconvenientes.

  ![ensutils_file](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_1/img/ensutils_file.png)


- Lo siguiente que teneemos que hacer es cargar el archivo mediante la consola de geth con el comando `loadScript('/home/esteban/Downloads/ensutils-testnet-rinkeby.js')`.

- Obtenemos true como respuesta y a continuación probamos que funcione correctamente con 2 nombres de dominio `.test`: `estebanabete` y el otro `edentity`
Para esto utilizamos el comando `testRegistrar.expiryTimes()` al cual le pasamos como parámetro el SHA3 del nombre del dominio como vemos en la imagen:

  ![ensutils_load](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_1/img/ensutils_load.png)

- A continuación ya estamos preparados para realizar el registro. Para esto vamos a usar el comando `testRegistrar.register()`.


  ![ens_register](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_1/img/ens_register.png)


- Luego validamos el ownership del dominio con el comando `ens.owner()` y al resultado lo comparamos con la cuenta que habiamos pasado como parámetro anteriormente con el comando `eth.coinbase`

  ![ens_ownership](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_1/img/ens_ownership.png)

- Finalmente obtenemos el resolver, por medio del comando `ens.resolver`

  ![ens_resolver](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_1/img/ens_resolver.png)







