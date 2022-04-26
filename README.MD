# Guia de JS (y otros lenguajes) para Tammy

El siguiente documento contiene la estructura basica que se puede encontrar en cualquier lenguaje de programacion.

Como ejemplo, este tutorial usará la notacion de Javascript

## Variables

Una variable es donde se guarda (y se recupera) datos que se utilizan en un programa.
La estructura se compone de una palabra que indica que _tipo de variable_ es + el _nombre de la variable_ (sin espacios) + el _signo de igualdad_ + el _valor_ que va a tomar.

```js
var miVariable = 100;
```

Las variables pueden cambiar su contenido a lo largo del tiempo de ejecucion.
Este tipo de variables usan las palabras `var` o `let` al momento de declararlas.

```js
var miVariable = 100;
miVariable = 200;
```

Posterior a ello, ya no se requiere usar de nuevom `var` o `let` para cambiar su valor.

Existen variables que una ves asignadas, estas siempre mantendran su valor. Estas variables se llaman _constantes_ y se caracterizan por usar la palabra `const`

```js
const miVariableConstante = 200;
```

En este caso `miVariableConstante` siempre tendra el valor de 200.

Como se puede notar, para nombrar una variable cuyo nombre se componga de muchas palabras, al no poder utilizar espacios, se pueden optar por varias opciones para nombrarlas; esto a juicio del desarrollador.
Los tipos de nombramiento de variables mas utilizados son:

- camel case: `miNombreDeVariable` - se empieza por minuscula, y cambia a mayuscula con la primera letra de la siguiente palabra
- snake case: `mi_nombre_de_variable` - se usa un guion bajo para separar palabras

## Tipos de variables

En los lenguajes de programacion, una variable puede contener diferentes tipos de datos. Estos son los mas comunes

```js
let miValor= 10 //Numericas
let miTexto= "Hola Mundo" //Cadenas de texto o "Strings"
let miBooleano = true // Booleanos (false/true)
let miListado = [1,2,3] // Listado de valores o "arrays"
let miListadoMixto = [1,"Hola Mundo", false] // Los listados pueden contener cualquier tipo de variable
let miObjeto = { // Objetos. Estos pueden almacenar cualquier tipo de dato
  nombre: "Tammy", //Texto
  edad: "26", // Numerico
  mascotas: ["Alpha", "Larry"], // Listado
  soltera: true, // Booleanos
  gustos: {
    musica: "Kpop",
    helado: "Chicle"
  } // Objetos
  familia: // Listado de objetos
  [
    {
      nombre: "Nancy",
      parentesco: "Madre"
    },
    {
      nombre: "Ines",
      parentesco: "Abuelita"
    }
  ]
}
```

### Listados

Como se puede observar, la variable `miListado` contiene 3 elementos.
Si nosotros quisieramos imprimer el valor de esa variable usando `console.log(miListado)`, se mostraria todo el contenido.

Si lo que nosotros queremos es trabajar con un determinado elemento del listaod, tenemos que especificar la posicion del mismo.

Por ejemplo, para trabajar con el tercer elemento de la lista, usamos `miListado[2]`

Dentro de la logica de programacion, se comienza a contar desde el **0**, es por eso que en este ejemplo la posicion 0 le corresponde al valor `1`, la posicion 1 le corresponde al valor `"Hola Mundo"` y la segunda posicion al valor `false`

## Comentarios

Como puedes notar, cuando en el codigo escribimos `//` significa que es un comentario. Es un fragmento dentro del codigo que no será tratado como tal y que al momento de ejecutar el programa será ignorado.
Se usan para agregar notas al codigo que ayuda a los desarrolladoras a entender partes del codigo

```js
// La siguiente variable representa las calificaciones de Tammy
let calificacion = 10;
```

## Condicionales

Son estructuras de control que se usan para determinar cuando una accion se ejecuta o no.
Se componen de la palabra reservada `ìf` y posteriormente la condicional a evaluar

```js
if (diaDeHoy === 'Lunes') {
  console.log('Que tengas un buen lunes');
}
```

El ejemplo anterior se interpreta como

> Sí la variable diaDeHoy es igual a Lunes, entonces imprime en pantalla el mensaje

Si queremos que la condicional realize una accion cuando esta no se cumple, añadimos la palabra `else`

```js
if (calificacion > 6) {
  console.log('Aprobado');
} else {
  console.log('Reprobado');
}
```

Lo anterior se lee como

> Si la variable calificacion es mayor que 6, imprime Aprobado. En caso contrario imprime Reprobado

**Nota**: Todo lo que esta dentro de las llaves `{}` se le considera un bloque de codigo que pertenece a la instruccion anterior

```js
if (calificacion > 6) {
  // Bloque te codigo a ejecutar si es verdadero
} else {
  // Bloque de codigo a ejecutar si es falso
}
```

### Comparadores

Los comparadores que se usan en las condicionales son las siguientes

```js
x == y; // x es igual que y
x != y; // x no es igual que y
x > y; // x mayor que y
x >= y; // x mayor o igual que y
x < y; // x menor que y
x <= y; // x menor o igual que y
!x; // negativo de x
```

## Ciclos

Los ciclos son estructuras repetitivas que ejecutaran una instruccion un determinado numero de veces.
Se componen por _variable_ de control, _condicional_ que determina cuando terminar en base a la variable de control, y _actualizacion_ de la variable de control.

### Operadores de actualizacion de variable

Existen ocasiones en las que queremos actualizar el valor de una variable, por ejemplo, sumandole una unidad.
Existe una notacion para escribir de manera rapida la actualizacion de una variable, por ejemplo

```js
//Aumentar el valor en una unidad
//Manera larga
x = x + 1;
// Manera corta
x++;

//Disminuir el valor en una unidad
//Manera larga
x = x - 1;
// Manera corta
x--;

//Aumentar el valor en N canditad de unidades
//Manera larga
x = x + 10;
// Manera corta
x += 10;

//Disminuir el valor en N canditad de unidades
//Manera larga
x = x - 10;
// Manera corta
x -= 10;

//Multiplicar el valor entre una cantidad
//Manera larga
x = x * 10;
// Manera corta
x *= 10;

//Dividir el valor entre una cantidad
//Manera larga
x = x / 10;
// Manera corta
x /= 10;
```

### Ciclo for

Son ciclos que se repiten una cantidad fija de veces.

```js
for (let i = 0; i < 5; i++) {
  console.log('Hola');
}
```

El codigo anterior se interpreta como

1. Inicia la variable `i` en 0.
2. Mientras `i` sea menor que 5, ejecuta las instrucciones en el bloque de codigo
3. Despues de cada vuelta, el valor de `i` aumentara en una unidad

En este caso, _i_ es nuestra variable de control, ya que se utiliza dentro de la _condicional_ `i<5` y posteriormente es actualizada de valor cuando se ejecuta `i++`
El codigo anterior imprimirá 5 veces la palabra "Hola"

### Ciclo While

A diferencia del ciclo `for`, en el ciclo while no se sabe con exactitud cuantas veces se tiene que ejecutar una accion.

En el ciclo for, nosotros actualizamos la variable de control usando, por ejemplo, `i++`, al finalizar cada vuelta.
En el ciclo While, esta actualizacion se puede llevar a cabo en cualquier momento

```js
let horaDeSalida = 6;
let horarioDeTrabajo = true;

while (horarioDeTrabajo == true) {
  cosole.log('Trabajando');
  horarioDeTrabajo = horaActual < horaDeSalida;
}

console.log('Hora de salida');
```

El codigo anterior se lee como

1. Inicia las variables `horaDeSalida` y `horarioDeTrabajo`
2. Mientras `horarioDeTrabajo` sea verdadero, ejecuta el bloque de codigo del while

   2.1 Imprime el mensaje Trabajando

   2.2 Revisa si aun es hora de salir. Comprueba que la `horaActual` sea menor que `horaDeSalida`

3. Al salir del ciclo, imprime "Hora de salida"

Aqui lo que le indica al ciclo while cuando terminar, es cuando el contenido de `horarioDeTrabajo` deja de ser verdadero. Al ya no ser verdadero, el programa abandona el bloque de codigo del While y ejecuta lo que esta afuera.
Como no sabemos cuantas veces se ejecurara esto, usamos el ciclo while.

## Funciones

Las funciones son bloques de codigo que pueden ser reutilizados mas de una vez.

Supongamos que queremos calcular el area de un rectangulo

```js
const base = 10;
const altura = 20;
const area = base * altura;

console.log(`El area del rectangulo es ${area}`);
```

Esto funciona bien para un evento. Pero que pasa si queremos calcular e imprimir el resultado de 3 rectangulos?

```js
const base = 10;
const altura = 20;
const area = base * altura;

console.log(`El area del rectangulo es ${area}`);

const base2 = 12;
const altura2 = 43;
const area2 = base2 * altura2;

console.log(`El area del rectangulo es ${area2}`);

const base3 = 4;
const altura3 = 16;
const area3 = base3 * altura3;

console.log(`El area del rectangulo es ${area}`);
```

Lo anterior, aunque funciona, no es lo mas optimo. Para ello es mejor crea una funcion y llamarla las veces que nosotros lo necesitemos.

Las funciones se componen de la palabra `function` + `nombreDeLaFuncion` + `Parametros` + `Bloque de codigo`
Los `parametros` son los valores de entrada que una funcion necesita para realizar su trabajo

```js
function calculaArea(base, altura) {
  const area = base * altura;
  console.log(`El area del rectangulo es ${area}`);
}
```

En este caso, nuestra funcion `calculaArea` necesita dos parametros de entrada para poder funcionar, los cuales son `base`y `altura`.

Al tener encapsulado este bloque de codigo dentro de una funcion, es facil para nosotros invocarlo las veces que nosotros necesitemos

```js
calculaArea(10, 12);

calculaArea(12, 43);

calculaArea(4, 16);
```

El ejemplo anterior se trata de una funcion que recibe parametros pero no regresa una respuesta. En el caso de que nosotros querramos utilizar el valor calculado dentro de una funcion y guardarla en una variable usamos la palabra `return`

Por ejemplo, supongamos que queremos una funcion para calcular el area de un rectangulo y posteriomente ese valor multiplicarlo por 100. La funcion quedaria de la siguiente manera:

```js
function calculaArea(base, altura) {
  const area = base * altura;
  return area; //Regresamos el valor del area
}

let miArea = calculaArea(5, 15); //Ahora miArea tiene el valor que calculaArea regreso con el return
miArea = miArea * 100;
console.log(`El area del rectangulo multiplicado por 100 es ${area}`);
```

Las funciones solo pueden regresar un valor. En caso de que necesitemos regresar mas valores, podemos crear un objeto con los valores de nuestro interés

```js
function calculaArea(base, altura) {
  const area = base * altura;
  return { area, base, altura }; //Regresamos los valores que necesitemos
}

let misValores = calculaArea(10, 10);
console.log(misValores.area);
console.log(misValores.base);
console.log(misValores.altura);
```

Las funciones pueden o no requerir parametros de entrada, asi como pueden o no regresar un valor.

```js
// Funcion sin parametros de entrada y sin regresar valor
function miFuncion() {
  console.log('Esta funcion no requiere parametros de entrada');
}

// Funcion que recibe un parametro y regresa un valor
function miOtraFuncion(parametro) {
  const resultado = parametro * 2;
  return resultadop;
}

miFunction();
const resultado = miOtraFuncion(2);
```

### Funciones flecha

Existe una manera de crear funciones y guardarlas dentro de variables. Estas reciben el nombre de funciones flecha o arrow functions. Se llama asi por que su estructura se asemeja a una flecha y no requiere que se escriba la palabra `function`

```js
const miFuncionFlecha = (parametro) => {
  console.log('Hola');
};
```

## Objetos

Los objetos son tipos de datos que pueden contener cualquier tipo de dato, o incluso funciones

```js
let miObjeto = {
  nombre: 'Tammy', //Texto
  edad: '26', // Numerico
  mascotas: ['Alpha', 'Larry'], // Listado
  soltera: true, // Booleanos
  gustos: {
    musica: 'Kpop',
    helado: 'Chicle',
  }, // Objetos
  // Listado de objetos
  familia: [
    {
      nombre: 'Nancy',
      parentesco: 'Madre',
    },
    {
      nombre: 'Ines',
      parentesco: 'Abuelita',
    },
  ],
  saludar: function () {
    //Funcion
    console.log('Hola a todos');
  },
};
```

Para acceder a un valor en especifico dentro del objeto podemos usar dos tipos de notaciones

```js
//Usando puntos
console.log(miObjeto.nombre);

//Usando corchetes
console.log(miObjeto['nombre']);
```

Si quisieramos acceder al valor de `musica` que esta dentro del objeto `gustos`, usariamos lo siguiente

```js
console.log(miObjeto.gustos.musica);
// Otra version
console.log(miObjeto['gustos']['musica']);
```

Si quisieramos acceder al nombre de `Ines` que esta dentro del listado familia en la segunda posicion, usamos

```js
console.log(miObjeto.familia[1].nombre);
// Otra version
console.log(miObjeto['familia'][1]['nombre']);
```

Si quisieramos ejecutar la funcion `saludar` usariamos

```js
miObjeto.saludar();
// Otra version
miObjeto['saludar']();
```

## Clases

Los objetos como ya vimos, se crean a partir de datos definidos.
Si nosotros quisieramos crear varios objetos y cada uno asignarle valores en especifico, es cuando usamos clases.

Las clases son un tipo de objeto compuestos por atributos (variables) y metodos (funciones) que modelan un objeto.

Por ejemplo, modelemos la clase Gato

Cuales son las caracteriticas de un gato?

- Raza
- Color
- Peso

Cuales son las acciones que realiza un gato?

- Dormir
- Comer
- Maullar

Con esto, podemos crear una clase gato, en donde las caracteristicas seran los atributos y las acciones seran los metodos

```js
class Gato {
  // En el constructor tomamos los parametros de entrada y los guardamos dentro de variables
  constructor(raza, color, peso) {
    this.raza = raza;
    this.color = color;
    this.peso = peso;

    // Usamos la palabra this para indicarle que estas variables le pertencen a la clase
  }

  dormir() {
    console.log('ZZZ');
  }

  comer() {
    console.log('Nom nom nom');
  }

  maullar() {
    console.log('Miau');
  }
}
```

Teniendo nuestra clase Gato, ahora podremos crear instancias de la clase, que no es nada mas que variables que contienen los atributos y metodos de la clase a la que hacemos referencia

```js
// Creamos un nuevo Gato y le asignamos esos valores
const Larry = new Gato('Mestizo', 'Gris', 10);
const Garfield = new Gato('Exotico', 'Naranja', 15);
```

Teniendo ya creado nuestra variable con la instancia de la clase Gato, podemos acceder a sus atributos y metodos de forma similar a los objetos

```js
console.log(Larry.raza);
Larry.dormir();
```
