Obtenga sin utilizar el compilador de Solidity el identificador de cada una de las
siguientes funciones y justifique cómo los ha obtenido. Muestre mediante un pantallazo la
obtención de los identificadores.
- function sumValues (uint _a, uint _b) public view returns (uint _c) {}
- function getGasDetails() public payable{}
- function __callback(bytes32 id, string memory result) public{}
- function abr(uint8 _a, address _address) internal{}

Debe modificar “abr” por sus iniciales (nombre y apellidos).
*La resolución del ejercicio se debe realizar aplicando un procedimiento manual, es decir,
sin utilizar herramientas que obtengan automáticamente los identificadores.

==============

### Resolucion

El proceso para obtener los identificadores de una funcion manualmente, está definido en la documentación de solidity indica que el ID del metodo está dado por los primeros 4 bytes del hash Keccak del la forma ASCII de la firma de la funcion, la cual esta definida por: nombredelafuncion(tipoParametro,tipoParametro)

- Siguiendo esta definición para nuestro primer caso tenemos la siguiente funcion:
~~~
function sumValues (uint _a, uint _b) public view returns (uint _c) {}
~~~

- La forma ASCCI de la firma de la funcion sería la siguiente:

~~~
sumValues(uint256,uint256)
~~~

Nota: Aqui tuvimos que cambiar el tipo dado que en la documentación se establece que el tipo uint es equivalente al uint256.

- Luego a este resultado ahora aplicamos el hash Keccak 256 y obtenemos el siguiente hash:

`27b57fcc13dafc8e83ae46798da0c4c32ac0b86c1f24ef37538b0fc8b50875f8`

![Keccak_sumvalues](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_5/img/Keccak_sumvalues.png)

- Finalmente obtenemos los primeros 4 bytes del hash, lo que nos deja con el siguiente numero como el identificador de la funcion:

`27b57fcc`

A continuación repetimos el procedimiento para cada uno de los casos solicitados, mostramos en la imagen como quedaría la funcion reducida y el hash correspondiente:

- function getGasDetails() public payable{}

![Keccak_getGasDetails](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_5/img/Keccak_getGasDetails.png)

** Identificador: 3d86f4af

- function __callback(bytes32 id, string memory result) public{}

![Keccak_callback](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_5/img/Keccak_callback.png)

** Identificador: 27dc297e

- function abr(uint8 _a, address _address) internal{}
Se renombra con iniciales a "ega" (Esteban Gabrriel Abete)

![Keccak_ega](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_5/img/Keccak_ega.png)

** Identificador: 4dd43b4e

## Verificación:

Para verificar los resultados obtenidos, se ha generado un smart contract con las funciones solicitadas para validar los resultados con el método automático del compilador de solidity. (Se adjunta archivo `comprobacio_identificadores.sol`)

~~~
pragma solidity ^0.5.0;

contract comprobaciones {
  
    address public minter;

    constructor() public {
        minter = msg.sender;
    }

    function sumValues (uint _a, uint _b) public view returns (uint _c) {}
    function getGasDetails() public payable{}
    function __callback(bytes32 id, string memory result) public{}
    function ega(uint8 _a, address _address) internal{}
}
~~~

![comprobaciones](https://github.com/egabete/Disenio-y-Desarrollo/blob/master/PEC_1/Ejercicio_5/img/comprobaciones.png)
