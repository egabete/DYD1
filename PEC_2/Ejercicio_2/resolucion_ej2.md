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

![running_dapp](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/running_dapp.png)