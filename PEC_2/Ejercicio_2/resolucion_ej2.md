# PEC 2
## EJERCICIO 2

### INSTALACION IPFS
- Para poder realizar el ejercicio primero debemos instalar IPFS siguiendo las indicaciones del siguiente link:
https://docs.ipfs.io/guides/guides/install/

1. Descargamos el archivo para la instalación:
![download](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/download.png)

2. Luego lo descomprimimos:
![descompresion](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/descompresion.png)

3. Luego realizamos instalación:
![installation](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/installation.png)

4. Una vez que realizamos la instalación procedemos a iniciar la carpeta para la syncronización de archivos:
![init](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/init.png)

5. Finalizamos inicializando el daemon de IPFS:
![daemon](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/daemon_initialization.png)

6. Como ultimo paso tenemos la validación de que la inicialización fue correcta, ya que visitamos la web local creada por la instalación e inicialización del daemon:
![web_local](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/ipfs_web_local.png)


### Preparacion ejemplo truffle box

- Elejí el truffle box "webpapck" que viene con la Dapp de ejemplo llamada Metacoin.
- Para esto iniciamos en un directorio el truffle box con el comoando `truffle unbox webpack`

![unbox_webpack](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/unbox_webpack.png)

- Luego compile y migre los smart contracts a la blockchain, que ya tenia funcionando en Ganache, con los comandos `truffle compile` y `truffle migrate`

![compile_migrate](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/compile_migrate.png)

- Luego probe la aplicaciòn ejecutando el servidor local web con el comando `npm run dev`
![npm_run_dev](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/npm_run_dev.png)

![running_dapp](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/running_dapp.png)

====
- Ya con la aplicacion funcionando, ele próximo paso sería subir rla carpeta de la Dapp a IPFS. Para que solo subir una carpeta a IPFS movi el archivo `MetaCoin.json` a la carpera `app/src` y cambiar el path desde el cual se lo importa, en el archivo `index.js`.

Aqui mostramos el arbol final de la carpeta general y en particular la de la carpera src que es la que vamos a publicar en IPFS:

![final_folder_trie](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/final_folder_trie.png)


- Una vez tenemos la carpeta lista, pasamos al paso de subirla a IPFS. Para esto necesitamos primero iniciar el demonio de IPFS y luego agregar la carpeta a ipfs de manera recursiva para que agregue todos los archivos y carpetas dentro. Esto lo hacemos con los comandos `ipfs daemon` en una terminal, y mientras se ejecuta el demonio navegamos hasta la carpeta que queremos subir y utilizamos el comando `ipfs add -r`

