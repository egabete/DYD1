# PEC 2
## EJERCICIO 4

### PASO 1
-   Primero debemos preparar el entorno para poder realizar el ejercicio. Para esto necesitamos:
    1.   Iniciar nodo Rinkeby. Para este punto vamos a usar el comando `geth --rinkeby`

      ![geth_rinkeby_start](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/geth_rinkeby_start.png)

    2.   Iniciar consola Geth. Para este punto vamos a usar el comando `geth --rinkeby attach`. Además nos aseguramos que el nodo está sincronizado con el comando `eth.syncing` y luego chequeamos el address que está seteado en el nodo con el comando `eth.coinbase`

      ![geth_attach](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/geth_attach.png)

    3.   Cargar el archivo `ensutils-testnet-rinkeby.js`. Para este punto usamos el comando `loadScript('/home/esteban/Downloads/ensutils-testnet-rinkeby.js')`. En este punto también chequeamos que esta correctamente conectado consultando el estado de un dominio registrado previamente en la PEC "estebanabete.test" con el comando `new Date(testRegistrar.expiryTimes(web3.sha3('estebanabete.test')).toNumber()*1000)`.
    
    ![load_scrirpt](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/load_script.png)
    
    ![check_domain](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/check_domain.png)
    
    - También usamos el comando `ens.owner(namehash('estebanabete.test'))` para validar que el owner coincide con nuestro address.

    ![check_owner](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/check_owner.png)


    4.   Iniciar demonio Swarm. Para esto vamos a usar el comando `swarm --ens-api "test:0xe7410170f87102df0055eb195163a03b7f2bff4a@http://127.0.0.1:30303" --datadir /home/esteban/.ethereum/rinkeby/ --bzzaccount 0x4ddFC2578142b73d5990A2906c38a27858462931`
    -   Un par de comentarios sobre este comando:
        - la opcion `--ens-api` nos indica ...
        - la direccion `test:0xe7410170f87102df0055eb195163a03b7f2bff4a@http://127.0.0.1:30303` es la direccion del contrato de la testnet Rinkeby donde se encuentra el ens.

    ![swarm_ensapi_start](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/swarm_ensapi_start.png)

### PASO 2
-   Ahora que tenemos los elementos inicializados y preparados podemos comenzar a realizar la práctica. Primero subimos la carpeta con la DAPP. La misma carpeta que para el Ejericio_1.
Para esto vamos a usar el siguiente comando:
`swarm --recursive --defaultpath /home/esteban/Documents/Disenio-y-Desarrollo/PEC_2/Ejercicio_2/pet_shop_example/dist/index.html up --encrypt /home/esteban/Documents/Disenio-y-Desarrollo/PEC_2/Ejercicio_2/pet_shop_example/dist/`

  ![swarm   _folder_upload](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/swarm_folder_upload.png)

- Ahora validamos si la aplicacion subio correctamente y podemos interactuar. Para esto además hemos activado Ganache con la blockchain del ejercicio anterior. (NOTA: para que funcione fue necesario actualizar las rutas de los assets de los archivos `index.html`, `app.js` y `pets.json`)


  ![swarm_folder_web](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/swarm_folder_web.png)


- Por ultimo nos queda el paso de linkear la aplicacion subida en Swarm con el dominio registrado en el ejercicio 1: `estebanabete.test`
Para esto vamos a usar el comando `publicResolver.setContent()` desde la consola de geth.

  ![swarm_setcontent](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/swarm_setcontent.png)

A este método como vemos se le pasan 3 parámetros:
- el hash del nombre del dominio;
- el hash del contenido que queremos linkear al dominio
- la cuenta con la que vamos a ejecutar la trasaccion.

- A pesar de que no he recibido ningun en el proceso, al querer comprobar el funcionamiento del dominio el mismo arroja un error 404 "Manifest not found"

  ![error_ens](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_4/img/error_ens.png)

He investigado y lo que he encontrado no me ha llevado a ninguna solución.
Lamentablemnte esta parte del ejercicio no he podido completarla.
