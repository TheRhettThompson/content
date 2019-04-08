---
subtitle: "Las funciones no son opcionales - Es probable que sean la característica más utilizada en cualquier lenguaje de programación. Te permiten separar tu código en miniprogramas más pequeños, donde cada uno se ocupa de lo suyo. ¡Divide y conquistaras!"
title: "Trabajando con Funciones"
cover: "https://ucarecdn.com/4cc6fa0b-2530-4052-aa7e-8dac03788ac3/"
textColor: "white"
date: "2018-12-03"
tags: ["reactjs"]

---


## ¿Qué son las Funciones?

Básicamente, una función es un montón de código envuelto entre paréntesis que puedes ejecutar en cualquier momento cada vez que juegues en dados. Por ejemplo:

```javascript 
//el nombre de la función es "multiply" y recibe 2 param: a y b
function multiply(a, b) {
    //la función devuelve la multiplicación 
   return a * b;
}
```

+ **Cada función debe tener un propósito.** (un objetivo) (como nuestra función "multiplicar"). El propósito de la función es calcular la multiplicación entre dos números dados.
+ **Debe tener un nombre único.**  En este caso particular, nuestra función se llama "multiplicar", que es un gran nombre porque sabes exactamente de qué se tratan las funciones, es explícita.
+ **Debe devolver algo.**  De forma predeterminada, en javascript, todas las funciones devuelven "indefinido", pero debe reemplazar y siempre devolver algo útil. En este ejemplo, queremos devolver el resultado de una multiplicación de a & b.
+ **Las funciones pueden tener parámetros.**  Un "parámetro" es una variable que la función puede recibir al principio de su código (como a y b en nuestro ejemplo).

La idea es tener una libreria de cientos de funciones y usarlas como nos plazca, declaras todas tus funciones y luego empiezas a usarlas y reutilizarlas todo el tiempo.

```
let resultOfMultiplication = multiply(2,4);
// resultOfMultiplication will be 2
```

## Pero, ¿por qué usar Funciones en lugar de simplemente hacer todo en una gran porción de código?

La codificación es muy abstracta y sucede mucho que no tienes idea de lo que escribiste ayer. Antes de que existieran las funciones, los algoritmos eran esta enorme serie interminable de líneas de código donde los desarrolladores tendrían dificultades y se perderían. Es difícil para tu cerebro seguir un procedimiento / algoritmo de gran longitud; Cuantas más líneas de código, más abstracto se vuelve.

Al utilizar funciones tienes las siguientes ventajas:

+ Dividir y conquistar: divide tu algoritmo en sub-algoritmos más pequeños y concéntrate en un problema a la vez.
+ Reutiliza tu código llamando a la función varias veces, reduciendo drásticamente la longitud de tu código.
+ Organiza tu código: los nombres de las funciones le dirán qué hace esa parte del código, puede tener todas las funciones en un archivo separado y reutilizarlo en todos sus desarrollos futuros.

Si lo piensas bien, las funciones son equivalentes a los libros. El conocimiento de la tienda y las formas de hacer las cosas y en futuros desarrollos simplemente los reutiliza en lugar de tener que resolver todo de nuevo.

## El Alcance de la Función

Todas las funciones deben comenzar y terminar en algún lugar, esto es llamado **el alcance de la función**. Puedes delimitar los límites usando llaves como esta:

```javascript{numberLines: true} 

//esta parte del código está FUERA de la función 'multiply'

function multiply(a, b) {

    //esta parte del código está DENTRO de mi función pero nunca lo hará 
   
   return a * b;

    //esta parte del código está DENTRO de mi función pero nunca lo hará
    //Se ejecutará porque se encuentra DESPUÉS de la declaración de retorno.
}

//esta parte del código está FUERA de la función 'multiply'
```

Cualquier variable que declare dentro de la función no estará disponible fuera de ella.

```javascript{numberLines: true}
function multiply(a, b) {

   let myVariable = 'hello';
   
   return a * b;
}

// este console.log no funcionará, generará un error, porque myVariable fue 
// declarado dentro de la función multiplicar, por lo tanto no está disponible fuera.
console.log(myVariable);
```


[[warning]]
| :point_up: Es muy importante recordar que una vez que use la instrucción `return`, la función dejará de ejecutarse, si hay algún código después de esa instrucción, nunca se ejecutará.

## Funciones Anónimas

Puedes declarar funciones sin nombres, pero solo si las almacenas en variables como esta:

```javascript
var multiply = function(a, b) {
   return a * b;
}
```

## Funciones de Llamada

La única forma de usar (una función de llamada) es usar paréntesis como este:

```javascript
//Así es como se llama a una función sin parámetros.
multiply();

//Así es como llamas a una función con parámetros.
multiply(<first param>,<second param>);

//por ejemplo, para multiplicar 3 por 9
multiply(3,9);
```

Recuerda asignar la función a los parámetros que deba recibir. En nuestro ejemplo, la función de multiplicación fue declarada pidiendo que se multipliquen dos números. Juega con el siguiente ejemplo como quieras:

<iframe height="400px" width="100%" src="https://repl.it/@4GeeksAcademy/Calling-Functions-Example?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

## Llamada Anidada

Puedes combinar funciones como quieras y tener llamadas encadenadas como esta:

```javascript{numberLines: true} 
function sum(a,b){
   return a+b;
}
function multiply(a,b){
   return a*b;
}


console.log(multiply(sum(3,5),sum(1,1)));


// Las ejecuciones van de adentro hacia afuera. 
// Primero, se calculará la suma de 3 + 5 y 1 + 1. 
// A continuación, se multiplicarán sus respectivos resultados. 
let firstSum = sum(3,5);
let secondSum = sum(1,1);
console.log(multiply(firstSum, secondSum));
```

[[demo]]
| :point_up: [Ver este ejemplo en vivo en replit](https://repl.it/@4GeeksAcademy/Nested-Function-Calling)

## Veamos un ejemplo:

El siguiente código tiene 3 funciones declaradas:

*function <span style="color:purple">getAverage</span>(**array: ages**){*
     ...
*}*

*function <span style="color:purple"> getYoungest</span>(**array: ages**)*
     ...
*}*
*function <span style="color:purple"> getPersonInfoByName</span>(**string: name**)*
     ...
*}*

Como puedes ver, los nombres de las funciones son bastante específicos sobre lo que hacen las funciones, así como los parámetros asignados a ellas.

La función recibe una matriz de

<iframe height="400px" width="100%" src="https://repl.it/@4GeeksAcademy/FunctionsExample?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Otras cosas importantes a tener en cuenta:

+ Estamos llamando a la función getPersonInfoByName dos veces, sin usar funciones tendríamos que usar más código porque no tendríamos ninguna opción para reutilizar la función.
+ La función getAverage es obtener el valor promedio en una matriz dada. No sabe nada más y eso es genial! Al separar su código en pequeñas funciones, puede concentrarse en una cosa a la vez.