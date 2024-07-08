**1-¿Qué tipo de bucles hay en JS?**
En JavaScript, nos encontramos con varios tipos de bucles tambien conocidos como ciclos que su funcionalidad principal es para repetir bloques de código de manera controlada. 

A continuacion explicare cada uno y pondré ejemplos:

 1-Bucles for: Este bucle es uno de los bucles más comunes en Javascript, este se utiliza cuando se sabe de antemano cuantas veces se debe repetir el bloque de código.
 Su sintaxis básica es la siguiente:
 ```for (inicialización; condición; incremento/decremento) {
  // código a repetir
 }```

A continuación pondre un ejemplo de como podriamos utilizar un bucle for para imprimir por pantalla los numeros del 1 al 5:
 ```for (let i = 1; i <= 5; i++) {
  console.log(i);
}```

 2-Bucles While: Se utiliza cuando no se sabe de antemano cuántas veces se debe repetir el bloque de código. Se ejecuta el bloque de código mientras la condición especificada en la expresión del bucle sea verdadera.
 Su sintaxis básica es la siguiente:
 ```
 while (condición) {
  // código a repetir
}
 ```

A continuación pondre un ejemplo de como podriamos utilizar un bucle while para para imprimir por pantalla los numeros del 1 al 10:
```
let i = 1;
while (i <= 10) {
  console.log(i);
  i++;
}
```
 3-Bucles do-while:es similar al bucle while, pero se ejecuta al menos una vez el bloque de código, incluso si la condición es falsa. 
 Su sintaxis básica es la siguiente:
 ```
 do {
  // código a repetir
} while (condición);
  ```
  A continuación pondre un ejemplo similar al anterior de como podriamos utilizar un bucle do-while para mostrar en pantalla los numeros del 1 al 10:
  ```
  let i = 1;
do {
  console.log(i);
  i++;
} while (i <= 10);
  ```
 4-Bucles for-in: Se utiliza para iterar sobre las propiedades de un objeto. 
 Su sintaxis básica es la siguiente:
 ´´´
 for (propiedad in objeto) {
  // código a repetir
}
 ´´´

 De hecho si tenemos el siguiente objeto:
 ```
 const persona = {
  nombre: 'Juan',
  edad: 25,
  ciudad: 'Madrid'
};
 ```

 Podemos utilizar este bucle para imprimir las propiedades del objeto de la siguiente forma:
 ```
 for (let propiedad in persona) {
  console.log(propiedad + ': ' + persona[propiedad]);
}
 ```

 Y lo que aparecera en pantalla sera lo siguiente:

 nombre: Juan
 edad: 25
 ciudad: Madrid

 Estos son los principales tipos de bucles en JavaScript. 
 Cada uno tiene su propósito y se utiliza en diferentes situaciones. 
 Es importante entender la sintaxis y cómo funcionan para poder utilizarlos de manera efectiva en nuestro código.

**2-¿Cuáles son las diferencias entre const, let y var?**
Las diferencias entre const, let y var en JavaScript de una manera clara y comprensible:
 1-var:
 var se utilizaba antes de la introducción de const y let en JavaScript.
 Se puede redeclarar y reasignar.
 Tiene un alcance de función, lo que significa que está disponible en toda la función en la que se declara.

 Ejemplo:
 ```var x = 10;
 var x = 20; // Re-declaración permitida
 x = 30; // Re-asignación permitida
```
 2-let:
 let se introdujo en ES6 y se utiliza para variables que pueden ser reasignadas pero no redeclaradas.
 Tiene un alcance de bloque, lo que significa que está disponible solo dentro del bloque en el que se declara.

 Ejemplo:
 let y = 10;
 // let y = 20; // Error: Re-declaración no permitida
 y = 30; // Re-asignación permitida

 3-const:
 const se utiliza para variables que no pueden ser reasignadas ni redeclaradas. Sin embargo, en el caso de objetos y arrays, el contenido puede ser modificado.
Tiene un alcance de bloque, al igual que let.
```
const z = 10;
// const z = 20; // Error: Re-declaración no permitida
// z = 30; // Error: Re-asignación no permitida
```

A modo de resumen:
-Utiliza var si necesitas variables con alcance de función y la posibilidad de redeclarar y reasignar.
-Utiliza let si necesitas variables con alcance de bloque y la posibilidad de reasignar pero no redeclarar.
-Utiliza const si necesitas variables inmutables (que no cambian) y con alcance de bloque.
**3-¿Qué es una función de flecha?**
Una función de flecha es una forma más concisa de definir funciones en JavaScript. Se introdujo en ES6 y se utiliza para crear funciones anónimas.

Sintaxis básica de una función de flecha:
```
(parámetros) => {
    // Código de la función
}
```
Un ejemplo:
```
const sumar = (a, b) => {
    return a + b;
};

console.log(sumar(2, 3)); // Imprime: 5
```

En este ejemplo, sumar es una función de flecha que toma dos parámetros a y b, y devuelve la suma de ambos.

Además de la sintaxis más concisa, las funciones de flecha también tienen algunas características adicionales:

 1-Sintaxis simplificada: Si la función tiene solo un parámetro, se pueden omitir los paréntesis alrededor del parámetro. Si la función tiene solo una línea de código, se pueden omitir las llaves y la palabra clave return. 

 Ejemplo:

 ```
 const cuadrado = x => x * x;
 console.log(cuadrado(5)); // Imprime: 25
 ```

 2-No tiene su propio this: Las funciones de flecha no tienen su propio this. El valor de this se hereda del ámbito en el que se define la función.

 Ejemplo:
 ```
 const objeto = {
    nombre: 'Juan',
    saludar() {
        const saludar = () => {
            console.log(`Hola, ${this.nombre}!`);
        };
        saludar();
    }
};

objeto.saludar(); // Imprime: Hola, Juan!
 ```

 En este ejemplo, la función de flecha saludar utiliza this.nombre para acceder a la propiedad nombre del objeto en el que se define.

 En resumen, las funciones de flecha son una forma más concisa de definir funciones en JavaScript. Se utilizan para crear funciones anónimas y ofrecen una sintaxis más clara y concisa. También tienen algunas características adicionales, como la simplificación de la sintaxis y la herencia del valor de this.

**4-¿Qué es la deconstrucción de variables?**
 La deconstrucción de variables, también conocida como destructuring, es una característica de JavaScript que permite extraer valores de arrays y objetos y asignarlos a variables de manera más concisa y legible.

 Sintaxis básica de la deconstrucción de variables:
 ```
 const [variable1, variable2, ..., variableN] = array;
 ```

 ```
 const { propiedad1, propiedad2, ..., propiedadN } = objeto;
 ```

 Ejemplo con arrays:
 ```
 const frutas = ['manzana', 'banana', 'cereza'];
 const [primeraFruta, segundaFruta, terceraFruta] = frutas;

 console.log(primeraFruta); // Imprime: manzana
 console.log(segundaFruta); // Imprime: banana
 console.log(terceraFruta); // Imprime: cereza
 ```
En este ejemplo, se utiliza la deconstrucción de variables para asignar los valores del array frutas a las variables primeraFruta, segundaFruta y terceraFruta.

Ejemplo con objetos:
```
const persona = {
    nombre: 'Juan',
    edad: 25,
    ciudad: 'Madrid'
};

const { nombre, edad, ciudad } = persona;

console.log(nombre); // Imprime: Juan
console.log(edad); // Imprime: 25
console.log(ciudad); // Imprime: Madrid
```
En este ejemplo, se utiliza la deconstrucción de variables para asignar los valores del objeto persona a las variables nombre, edad y ciudad.

Además de arrays y objetos, la deconstrucción de variables también se puede utilizar con otros tipos de datos, como strings y funciones.

En resumen, la deconstrucción de variables es una característica de JavaScript que permite extraer valores de arrays y objetos y asignarlos a variables de manera más concisa y legible. Se utiliza para mejorar la legibilidad y simplificar el acceso a los valores de estructuras de datos complejas.
**5-¿Qué hace el operador de extensión en JS?**
El operador de extensión, también conocido como el operador de propagación, es una característica de JavaScript que permite expandir elementos de un array o propiedades de un objeto en otros arrays o objetos.

Sintaxis básica del operador de extensión:
```
[...array]
```

```
{ ...objeto }
```

Ejemplo con arrays:

```
const array1 = [1, 2, 3];
const array2 = [...array1, 4, 5];

console.log(array2); // Imprime: [1, 2, 3, 4, 5]
```
En este ejemplo, se utiliza el operador de extensión para expandir el contenido del array array1 en el nuevo array array2. Se añaden los valores 4 y 5 al final del array resultante.

Ejemplo con objetos:
```
const objeto1 = { a: 1, b: 2 };
const objeto2 = { ...objeto1, c: 3 };

console.log(objeto2); // Imprime: { a: 1, b: 2, c: 3 }
```
En este ejemplo, se utiliza el operador de extensión para expandir las propiedades del objeto objeto1 en el nuevo objeto objeto2. Se añade la propiedad c con el valor 3 al objeto resultante.

Además de arrays y objetos, el operador de extensión también se puede utilizar con funciones para pasar argumentos de forma más concisa.

En resumen, el operador de extensión permite expandir elementos de un array o propiedades de un objeto en otros arrays o objetos. Se utiliza para combinar elementos, clonar arrays o objetos, o pasar argumentos a funciones de manera más concisa.

**6-¿Qué es la programación orientada a objetos?**
La programación orientada a objetos (OOP) es un paradigma de programación que organiza el código en torno a objetos, que son entidades que tienen propiedades y métodos. Los objetos representan entidades del mundo real o conceptos abstractos y se comunican entre sí a través de mensajes.

En JavaScript, la programación orientada a objetos se basa en la creación de objetos a partir de clases. Una clase define la estructura y comportamiento de un objeto, mientras que los objetos son instancias de una clase.

Sintaxis básica de la programación orientada a objetos en JavaScript:
```
class NombreClase {
    constructor(propiedad1, propiedad2, ...) {
        // Inicialización de propiedades
    }

    método1() {
        // Código del método 1
    }

    método2() {
        // Código del método 2
    }
}

const objeto = new NombreClase(valor1, valor2, ...);
```

Ejemplo de programación orientada a objetos en JavaScript:
```
class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    saludar() {
        console.log(`Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
    }

    getEdad() {
        return this.edad;
    }
}

const persona1 = new Persona('Juan', 25);
persona1.saludar(); // Imprime: Hola, mi nombre es Juan y tengo 25 años.
console.log(persona1.getEdad()); // Imprime: 25
```
En este ejemplo, se define la clase Persona con propiedades nombre y edad, y métodos saludar y getEdad. Luego, se crea un objeto persona1 a partir de la clase Persona y se utiliza para llamar a los métodos y acceder a las propiedades.

La programación orientada a objetos ofrece varias ventajas, como la reutilización de código, la modularidad, y la facilidad de mantenimiento. También permite modelar mejor el mundo real y la abstracción de conceptos.

**7-¿Qué es una promesa en JS?**

Una promesa (promise) es un objeto en JavaScript que representa la terminación o el fracaso de una operación asíncrona. Las promesas se utilizan para manejar y coordinar operaciones asíncronas, como solicitudes de red, operaciones de lectura o escritura de archivos, entre otras.

Sintaxis básica de una promesa en JavaScript:
```
const miPromesa = new Promise((resolve, reject) => {
    // Lógica asíncrona

    if (condiciónDeÉxito) {
        resolve(valorDeÉxito);
    } else {
        reject(valorDeError);
    }
});
```
Ejemplo de uso de una promesa en JavaScript:
```
const miPromesa = new Promise((resolve, reject) => {
    setTimeout(() => {
        if (Math.random() < 0.5) {
            resolve('Éxito');
        } else {
            reject('Error');
        }
    }, 2000);
});

miPromesa
    .then((resultado) => {
        console.log(resultado);
    })
    .catch((error) => {
        console.error(error);
    });
```
En este ejemplo, se crea una promesa miPromesa que se resuelve o rechaza después de un tiempo aleatorio. Si el número aleatorio es menor que 0.5, la promesa se resuelve con el valor "Éxito". De lo contrario, la promesa se rechaza con el valor "Error". Luego, se utiliza el método then para manejar el resultado exitoso y el método catch para manejar el error.

Las promesas ofrecen una forma más clara y legible de manejar operaciones asíncronas en JavaScript. Además, permiten encadenar varias operaciones asíncronas utilizando el método then y el método catch, lo que facilita la gestión de flujos de trabajo complejos.

**8-¿Qué hacen async y await por nosotros?**
async y await son palabras clave en JavaScript que se utilizan junto con promesas para simplificar el manejo de operaciones asíncronas.

async es una palabra clave que se utiliza antes de una función para indicar que la función es asíncrona y devuelve una promesa. Cuando se utiliza async, se puede utilizar la palabra clave await dentro de la función para esperar la resolución o rechazo de una promesa.

Sintaxis básica de async y await en JavaScript:
```
async function nombreFuncion() {
    // Lógica asíncrona

    const resultado = await promesa;

    // Más lógica después de la espera
}
```
Ejemplo de uso de async y await en JavaScript:
```
async function obtenerDatos() {
    const datos = await fetch('https://api.example.com/datos');
    const resultado = await datos.json();
    return resultado;
}

obtenerDatos()
    .then((resultado) => {
        console.log(resultado);
    })
    .catch((error) => {
        console.error(error);
    });
```

En este ejemplo, se define una función obtenerDatos que es asíncrona y utiliza await para esperar la resolución de la promesa fetch y la conversión de los datos en formato JSON. Luego, se retorna el resultado de la función.

La ventaja de utilizar async y await es que permite escribir código asíncrono de manera más sencilla y legible. En lugar de utilizar callbacks o métodos then/catch, se puede utilizar el flujo de control de manera más lineal y fácil de entender.

Además, async y await facilitan la gestión de errores y la composición de funciones asíncronas, ya que se pueden utilizar en combinación con otras funciones asíncronas.