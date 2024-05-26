`async` y `await` son dos palabras clave en JavaScript que facilitan el trabajo con operaciones asíncronas, como las promesas, haciendo que el código asíncrono se lea y se escriba de manera más similar al código síncrono. Aquí te explico cómo funcionan y cómo se usan.

### `async`

La palabra clave `async` se utiliza para declarar una función asíncrona. Una función asíncrona siempre devuelve una promesa. Si la función devuelve un valor, ese valor es automáticamente envuelto en una promesa resuelta. Si la función lanza una excepción, la promesa es rechazada con esa excepción.

**Ejemplo:**

```javascript
async function miFuncion() {
  return "Hola";
}

miFuncion().then((mensaje) => console.log(mensaje)); // "Hola"
```

En este ejemplo, `miFuncion` es una función asíncrona que devuelve una promesa que se resuelve con el valor `"Hola"`.

### `await`

La palabra clave `await` se utiliza dentro de una función asíncrona para pausar la ejecución de la función hasta que una promesa se resuelva o se rechace. `await` solo puede ser utilizado dentro de funciones declaradas con `async`.

**Ejemplo:**

```javascript
function esperar(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

async function miFuncion() {
  console.log("Esperando...");
  await esperar(2000); // Pausa la ejecución durante 2 segundos
  console.log("Listo!");
}

miFuncion();
```

En este ejemplo, la ejecución de `miFuncion` se pausa durante 2 segundos debido a `await esperar(2000)`. Después de la pausa, se imprime "Listo!".

### Ejemplo Completo con `async` y `await`

Supongamos que queremos obtener datos de una API. Podemos usar `async` y `await` para hacer que el código sea más legible.

**Sin `async` y `await`:**

```javascript
function obtenerDatos() {
  fetch('https://api.example.com/datos')
    .then(response => response.json())
    .then(data => {
      console.log(data);
    })
    .catch(error => {
      console.error('Error:', error);
    });
}

obtenerDatos();
```

**Con `async` y `await`:**

```javascript
async function obtenerDatos() {
  try {
    const response = await fetch('https://api.example.com/datos');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

obtenerDatos();
```

### Explicación del Ejemplo

1. **Declarar una Función Asíncrona**: `async function obtenerDatos()` declara la función `obtenerDatos` como asíncrona.
2. **Esperar una Promesa**: `const response = await fetch('https://api.example.com/datos');` espera a que la promesa devuelta por `fetch` se resuelva.
3. **Procesar la Respuesta**: `const data = await response.json();` espera a que la promesa devuelta por `response.json()` se resuelva, lo que permite trabajar con los datos de manera síncrona.
4. **Manejo de Errores**: `try...catch` se utiliza para capturar y manejar cualquier error que ocurra durante la operación asíncrona.

### Ventajas de `async` y `await`

- **Legibilidad**: Hace que el código asíncrono se vea y se comporte como código síncrono, mejorando la legibilidad.
- **Manejo de Errores**: Facilita el manejo de errores usando `try...catch` en lugar de encadenar múltiples `.catch()` en promesas.
- **Depuración**: Es más fácil de depurar porque las herramientas de desarrollo pueden seguir mejor el flujo de ejecución del código.

### Resumen

- **`async`**: Declara una función asíncrona que devuelve una promesa.
- **`await`**: Pausa la ejecución de una función asíncrona hasta que una promesa se resuelve o se rechaza.
- **Manejo de Errores**: Usa `try...catch` para manejar errores en funciones asíncronas.

`async` y `await` son herramientas poderosas que hacen que trabajar con operaciones asíncronas en JavaScript sea más fácil y más intuitivo.
