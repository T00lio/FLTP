#### Ejemplo de uso de `Object`:

```javascript
const persona = {
  nombre: "Tulio",
  edad: 39,
  ciudad: "Chicago"
};

// Acceder a una propiedad
console.log(persona.nombre);  // Output: Tulio

// Añadir una nueva propiedad
persona.profesion = "Desarrollador Web";

// Iterar sobre las propiedades del objeto
for (const key in persona) {
  console.log(`${key}: ${persona[key]}`);
}
```

### Mapas (`Map`)

Un `Map` es una colección de pares clave/valor donde las claves pueden ser de cualquier tipo (objetos, funciones, primitivas). `Map` conserva el orden de inserción de los elementos, lo que significa que cuando iteras sobre un `Map`, los elementos se devuelven en el orden en que se insertaron.

#### Ejemplo de uso de `Map`:

```javascript
const mapa = new Map();

// Añadir pares clave/valor
mapa.set('nombre', 'Tulio');
mapa.set('edad', 39);
mapa.set('ciudad', 'Chicago');

// Acceder a un valor por su clave
console.log(mapa.get('nombre'));  // Output: Tulio

// Verificar si una clave existe en el mapa
console.log(mapa.has('edad'));  // Output: true

// Iterar sobre las entradas del mapa
mapa.forEach((valor, clave) => {
  console.log(`${clave}: ${valor}`);
});

// Eliminar una entrada por su clave
mapa.delete('ciudad');

// Obtener el número de entradas en el mapa
console.log(mapa.size);  // Output: 2

// Limpiar todas las entradas del mapa
mapa.clear();
```

### Diferencias Clave entre `Object` y `Map`

1. **Tipo de Clave**: En `Object`, las claves son cadenas de texto o símbolos. En `Map`, las claves pueden ser de cualquier tipo.
2. **Orden de Inserción**: `Map` mantiene el orden de inserción de las claves, mientras que `Object` no garantiza el orden.
3. **Métodos y Propiedades**: `Map` tiene métodos integrados específicos como `.set()`, `.get()`, `.has()`, `.delete()`, `.size()`, y `.clear()`, mientras que `Object` no tiene estos métodos por defecto.
4. **Iteración**: Iterar sobre un `Map` es más fácil y directo con métodos como `.forEach()`, `.keys()`, `.values()`, y `.entries()`. Para iterar sobre las propiedades de un `Object`, necesitas usar `for...in` o métodos como `Object.keys()`, `Object.values()`, y `Object.entries()`.

Ambas estructuras tienen sus usos y ventajas dependiendo del contexto y de las necesidades específicas de tu aplicación.

