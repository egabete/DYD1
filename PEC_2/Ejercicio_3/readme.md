# PEC 3
## EJERCICIO 2

### PASO 1 - Instalar Swarm

- Instalamos *SWARM* con el comando `sudo apt-get install ethereum-swarm`

![swarm_install](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/swarm_install.png)

- Creamos una nueva cuenta en Rinkeby y luego iniciamos SWARM, pasandole la cuenta geneerada:

![geth_account_new](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/geth_account_new.png)


![new_account_rinkeby](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/new_account_rinkeby.png)

- Ahora confirmamos que SWARM está arriba accediendo a `localhot:8500` a través del browser.

 ![swarm_web](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/swarm_web.png)


### PASO 2

- Generamos los assets que queremos subir y los ponemos dentro de un folder (ver carpeta `swarm_folder`):

 ![swarm_folder](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/swarm_folder.png)


- Para subir la carpeta vamos a utilizar las siguientes opciones:
    - `up` --> para hacer el upload
    - `--recursive` --> para hacer el upload de manera recursiva del contenido del directorio
    - `--defaultpath` --> indicamos cual queremos que sea lo que se referencie cuando llamemos al hash que se va a generar de la carpeta.
    - `--encrypt` --> para hacer el upload de manera encryptada

 ![swarm_upload](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/swarm_upload.png)

 - Una vez hacemos el upload podemos ver el contenido en el browser, y al navegar a los links, vemos que el hash no cambia en la URL.

  ![swarm_web_local](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/swarm_web_local.png)

  ![swarm_web_link1](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/swarm_link1.png)

  ![swarm_web_link2](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/swarm_link2.png)

    - También podemos ver el archivo subido en el SWARM Gateway:

  ![swarm_web_uploaded](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_2/Ejercicio_2/img/swarm_uploaded.png)

