Instale el ​ compilador de Solidity​ (si aún no lo tiene instalado).

Obtenga un contrato inteligente que haya utilizado anteriormente o desarrolle uno tan
simple como pueda.
A partir del compilador de Solidity y habilitando siempre la optimización (​ --optimize​ ).
Obtenga:
- Códigos de operación del contrato inteligente.
- Identificadores de las funciones que existan dentro del contrato inteligente.
- Estimación del gas utilizado por cada función.


==================
Previo a iniciar los ejercicios necesitamos instalar el compilador de solidity, como se indica en la referencia.
Para esto usamos los siguientes comandos para usar el gestor de paquetes de ubuntu:

~~~
sudo add-apt-repository ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install solc
~~~

Una vez con el compilador instalado podemos comenzar
Se agrega en la carpeta el archivo `contrato_ejemplo_storedata.sol`

### Punto 1

Para obtenere los operation codes del contrato, revisamos la ayuda del compilador con la opcion `--help` y encontramos la opcion `--opcodes`.

Ahora para ejecutar el compilador nos posicionamos en la carpeta donde tenemos el archivo del contrato para poder ejecutarlo. 

![help_y_carpeta](https://github.com/egabete/DYD1/blob/master/Ejercicio_4/img/help_y_carpeta.png)


Una vez en la posisión correcta, procedemos a ejecutar el comando, sin embargo nos devuelve un error por la versión del compilador.
Para esto cambiamos la versión en el archivo del contrato para que pueda ser ejecutada por el compilador.
Finalmentee, volvemos a ejeecutar el comando y esta vez si obtenemos la información correspondiente:

![ejecucion_compilador](https://github.com/egabete/DYD1/blob/master/Ejercicio_4/img/ejecucion_compilado.png)


### Punto 2

Para obtener el identificador de las funciones vamos a utilizar otra opcion del compilador: `--hashes`

![help_hashes](https://github.com/egabete/DYD1/blob/master/Ejercicio_4/img/help_hashes.png)

Lo ejecutamos y obtenemos eel siguiente resultado:

![hashes_ejecucion](https://github.com/egabete/DYD1/blob/master/Ejercicio_4/img/hashes_ejecucion.png)


### Punto 3

Para obtener la estimación de Gas, nuevamente vamos usar una opcion del compilador: `--gas`

![help_gas](https://github.com/egabete/DYD1/blob/master/Ejercicio_4/img/help_hashes.png)

Lo ejecutamos y obtenemos eel siguiente resultado:

![gas_ejecucion](https://github.com/egabete/DYD1/blob/master/Ejercicio_4/img/hashes_ejecucion.png)

