




Inicie la sincronización de la red Rinkeby en su dispositivo (se recomienda ésta frente a Ropsten debido al tamaño de la misma y la velocidad de sincronización).

Para la realización de este ejercicio no necesita una sincronización completa del nodo.

1. Obtenga el address correspondiente al bloque génesis de la red Rinkeby mediante
la consola del cliente Geth y demuestre cómo lo ha obtenido. No use la función
getBlock(...)​ .
2. Obtenga sólo la cantidad de peers a los que está conectado. Demuestre cómo lo
ha obtenido.
3. Obtenga información acerca de los peers a los que está conectado e indique el
hash del bloque actual de éstos.
4. Añada manualmente mediante la consola de Geth un ​ bootnode ​ de la red Rinkeby.


=================

Antes de comenzar debemos conectarnos a la red Rinkeby, para eso usamos el comando `geth --rinkeby`

![geth rinkeby](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_3/img/geth_rinkeby.png)

Segundo debemos conectarnos a la consola de geth, pero no al a que habiamos generado originalmente, sino a la que nos conecta con la blockchain de Rinkeby, para eso debemos explorar donde se esta guardando la blockchain de manera local y buscar el archivo `geth.ipc` correspondiente en mi caso en la ruta que se muestra en la imagen:

![geth rinkeby](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_3/img/geth_ipc.png)

Una vez ya listos con acceso a la red, comenzamos a trabajar:

### Punto 1

PAra obtener el address correspondiente al bloque genesis, sin usar la funcion `getBlock()` podemos usar la funciona `admin.nodeInfo`, donde podemos ver en el campo "Genesis" del JSON que nos devuelve, la address correspondiente al bloque genesis.

![admin_nodeIndo](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_3/img/admin_nodeInfo.png)

Referencia: https://github.com/ethereum/go-ethereum/wiki/Management-APIs#admin_nodeinfo

#### Punto 2

Para obtener la cantidad de peers a los que actualmente estoy conectado lo puedo obtenere utilizando el comando `web3.net.peerCount`, en nuestro caso solo 2 al momento del ejercicio: 

![web3_net_peer_count](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_3/img/web3_net_peerCount.png)

Rerencia: https://github.com/ethereum/wiki/wiki/JavaScript-API#web3netpeercount

#### Punto 3

Para obtener los datos de los peers a los que nos encontramos conectados utilizamos el comando `admin.peers` y nos devuelve un JSON con los datos de cada uno de los nodos:

![admin_peers](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_3/img/admin_peers.png)

Referencia: https://github.com/ethereum/go-ethereum/wiki/Management-APIs#admin_peers

#### Punto 4
Para agregar un bootnode tenemos que usar la funcion `admin.addPeer` pero para esto necesitamos la referencia a un bootnode, en formato enode.
Para eso encontramos un enode de la red rinkeby en la siguiente referencia (https://github.com/ethereum/go-ethereum/blob/master/params/bootnodes.go) que aùn no tenemos registrada: `"enode://a24ac7c5484ef4ed0c5eb2d36620ba4e4aa13b8c84684e1b4aab0cebea2ae45cb4d375b77eab56516d34bfbd3c1a833fc51296ff084b770b94fb9028c4d25ccf@52.169.42.101:30303" `

Una vez con esta información procedemos a agregar el bootnode:

![admin_addPeer](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_3/img/admin_addPeer.png)

Una vez lo agregamos nos devuelve `true` y a continuación validamos con los comandos anteriormente utilizados que se haya agregado correctamente:

![new_ammount_peers](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_3/img/new_ammount_peers.png)

![details_of_peers](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_3/img/details_of_peers.png)


Referencias: 
- https://github.com/ethereum/go-ethereum/wiki/Connecting-to-the-network
- https://github.com/ethereum/go-ethereum/blob/master/params/bootnodes.go (for list of bootnodes)



