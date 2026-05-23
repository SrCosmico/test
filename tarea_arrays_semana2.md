# Programación II — Tarea Semana 2
## Métodos de arrays con los datos de tu MVP

**Profesor:** Ing. Jesús Galvis  
**Ejecutar con:** `ts-node tarea_arrays.ts`  
**Entrega:** Carpeta `semana2/` de tu repositorio · commit: `feat: tarea arrays semana 2`

---

## Instrucciones

Esta tarea tiene **dos partes**:

1. **Parte A** — Ejercicios con datos de ejemplo (igual para todos)
2. **Parte B** — Los mismos ejercicios pero con **los datos de TU propio MVP**

En la Parte B debes reemplazar la interface y los datos por los de tu app. Si tu MVP es una red social, tus objetos son posts. Si es una tienda, son productos. Si es un sistema de transporte, son rutas. Los métodos son los mismos — solo cambian los datos.

---

## Parte A — Datos de ejemplo

Copia este código en `tarea_arrays.ts` y completa los ejercicios.

```typescript
// tarea_arrays.ts — Parte A

// Interface base
interface Producto {
  id:         string
  nombre:     string
  precio:     number
  categoria:  string
  disponible: boolean
  tags:       string[]
}

// Datos de prueba — NO modificar en la Parte A
const productos: Producto[] = [
  { id: "p1", nombre: "Café negro",     precio: 2.5,  categoria: "bebidas",  disponible: true,  tags: ["caliente", "popular"]      },
  { id: "p2", nombre: "Jugo de naranja",precio: 3.0,  categoria: "bebidas",  disponible: true,  tags: ["frío", "natural"]          },
  { id: "p3", nombre: "Empanada queso", precio: 1.5,  categoria: "comidas",  disponible: false, tags: ["salado", "popular"]        },
  { id: "p4", nombre: "Agua mineral",   precio: 1.0,  categoria: "bebidas",  disponible: true,  tags: ["frío"]                     },
  { id: "p5", nombre: "Arepa reina",    precio: 4.0,  categoria: "comidas",  disponible: true,  tags: ["salado", "popular", "hot"] },
  { id: "p6", nombre: "Tequeño",        precio: 0.75, categoria: "snacks",   disponible: true,  tags: ["salado", "popular"]        },
  { id: "p7", nombre: "Brownie",        precio: 2.0,  categoria: "snacks",   disponible: false, tags: ["dulce"]                    },
  { id: "p8", nombre: "Smoothie mango", precio: 3.5,  categoria: "bebidas",  disponible: true,  tags: ["frío", "natural", "hot"]   },
]


// ══════════════════════════════════════════════════
// EJERCICIO 1 — filter()
// ══════════════════════════════════════════════════

// 1a. Filtra solo los productos que están disponibles
const disponibles: Producto[] = // TU CÓDIGO AQUÍ
console.log("1a. Disponibles:", disponibles.length) // debe ser 6

// 1b. Filtra los productos de la categoría "bebidas"
const bebidas: Producto[] = // TU CÓDIGO AQUÍ
console.log("1b. Bebidas:", bebidas.map(p => p.nombre))

// 1c. Filtra los productos que cuestan menos de 2 dólares Y están disponibles
const economicos: Producto[] = // TU CÓDIGO AQUÍ
console.log("1c. Económicos y disponibles:", economicos.map(p => p.nombre))
// resultado esperado: ["Agua mineral", "Tequeño"]


// ══════════════════════════════════════════════════
// EJERCICIO 2 — map()
// ══════════════════════════════════════════════════

// 2a. Crea un array con solo los nombres de todos los productos
const nombres: string[] = // TU CÓDIGO AQUÍ
console.log("2a. Nombres:", nombres)

// 2b. Crea un array de objetos con solo { id, nombre, precio }
//     (sin categoría, tags ni disponible)
const resumen = // TU CÓDIGO AQUÍ
console.log("2b. Resumen[0]:", resumen[0])
// resultado esperado: { id: "p1", nombre: "Café negro", precio: 2.5 }

// 2c. Crea un array con los precios aumentados un 10%
//     Usa toFixed(2) para redondear a 2 decimales
const preciosNuevos = // TU CÓDIGO AQUÍ
console.log("2c. Precios con 10% aumento:", preciosNuevos)
// resultado esperado: [2.75, 3.30, 1.65, 1.10, 4.40, 0.83, 2.20, 3.85]


// ══════════════════════════════════════════════════
// EJERCICIO 3 — find()
// ══════════════════════════════════════════════════

// 3a. Encuentra el producto con id "p5"
const producto = // TU CÓDIGO AQUÍ
console.log("3a. Producto p5:", producto?.nombre) // "Arepa reina"

// 3b. Encuentra el primer producto de la categoría "snacks"
const primerSnack = // TU CÓDIGO AQUÍ
console.log("3b. Primer snack:", primerSnack?.nombre) // "Tequeño"

// 3c. Busca un producto que no existe (id "p99")
//     Imprime un mensaje si no se encuentra
const noExiste = // TU CÓDIGO AQUÍ
if (noExiste) {
  console.log("3c. Encontrado:", noExiste.nombre)
} else {
  console.log("3c. Producto no encontrado") // debe imprimir esto
}


// ══════════════════════════════════════════════════
// EJERCICIO 4 — includes()
// ══════════════════════════════════════════════════

// 4a. Verifica si el producto p1 tiene el tag "popular"
const tienePopular: boolean = // TU CÓDIGO AQUÍ
console.log("4a. p1 tiene tag 'popular':", tienePopular) // true

// 4b. Crea un array con los nombres de los productos que tienen el tag "natural"
//     Pista: usa filter() + includes() juntos
const naturales: string[] = // TU CÓDIGO AQUÍ
console.log("4b. Productos naturales:", naturales)
// resultado esperado: ["Jugo de naranja", "Smoothie mango"]

// 4c. Un usuario tiene estos productos en su carrito:
const carrito: string[] = ["p2", "p6", "p8"]
// Verifica si el producto "p3" está en el carrito
const estaEnCarrito: boolean = // TU CÓDIGO AQUÍ
console.log("4c. p3 en carrito:", estaEnCarrito) // false


// ══════════════════════════════════════════════════
// EJERCICIO 5 — COMBINADOS (el más importante)
// ══════════════════════════════════════════════════

// 5a. Obtén los nombres de los productos disponibles de la categoría "bebidas"
//     Pista: filter() + map() encadenados
const bebidasDisponibles: string[] = // TU CÓDIGO AQUÍ
console.log("5a. Bebidas disponibles:", bebidasDisponibles)
// resultado esperado: ["Café negro", "Jugo de naranja", "Agua mineral", "Smoothie mango"]

// 5b. Encuentra el producto MÁS CARO que esté disponible
//     Pista: filter() primero, luego find() o reduce()
const masCaro: Producto | undefined = // TU CÓDIGO AQUÍ
console.log("5b. Más caro disponible:", masCaro?.nombre, "$" + masCaro?.precio)
// resultado esperado: "Arepa reina" $4

// 5c. ¿Hay algún producto disponible en la categoría "snacks" con el tag "popular"?
//     Pista: filter() + includes() + algunos().
//     Devuelve boolean
const haySnackPopular: boolean = // TU CÓDIGO AQUÍ
console.log("5c. Snack popular disponible:", haySnackPopular) // true
```

---

## Parte B — Tu propio MVP ⭐

Esta es la parte más importante. Crea un archivo `tarea_arrays_mvp.ts` con los datos de tu app.

**Instrucciones:**

1. Define una `interface` que represente el objeto principal de tu MVP
2. Crea un array con **mínimo 6 objetos** de prueba con datos realistas
3. Resuelve los 5 ejercicios de abajo usando TUS datos

```typescript
// tarea_arrays_mvp.ts — Parte B

// PASO 1: Define tu interface
// Reemplaza esto con la interface de tu app
// Ejemplos:
//   - App de posts:    interface Post   { id, titulo, autor, likes, publicado }
//   - App de rutas:    interface Ruta   { id, origen, destino, precio, activa }
//   - App de eventos:  interface Evento { id, nombre, lugar, fecha, gratuito }
//   - App de usuarios: interface Perfil { id, nombre, carrera, activo, tags }

interface TuEntidad {
  // TU CÓDIGO AQUÍ — mínimo 5 campos, incluyendo:
  // - un id: string
  // - un campo de texto descriptivo
  // - un número (precio, likes, rating, etc.)
  // - un boolean (activo, disponible, publicado, etc.)
  // - un array de strings (tags, categorías, etc.)
}

// PASO 2: Crea tu array de datos de prueba
const tusDatos: TuEntidad[] = [
  // mínimo 6 objetos con datos reales de tu app
]


// PASO 3: Resuelve estos 5 ejercicios con TUS datos

// B1. filter() — filtra por el campo boolean de tu interface
const activos = tusDatos.filter(/* TU CONDICIÓN */)
console.log("B1. Activos:", activos.length)

// B2. map() — extrae solo los nombres o títulos
const nombres = tusDatos.map(/* TU TRANSFORMACIÓN */)
console.log("B2. Nombres:", nombres)

// B3. find() — busca un elemento por su id
const elemento = tusDatos.find(/* TU BÚSQUEDA */)
console.log("B3. Encontrado:", elemento)

// B4. includes() — verifica si un tag o valor existe en un elemento
const tieneTag = tusDatos[0].tags.includes(/* UN TAG DE TU APP */)
console.log("B4. Tiene tag:", tieneTag)

// B5. filter() + map() encadenados
//     Filtra los activos y extrae sus nombres
const nombresActivos = tusDatos
  .filter(/* TU FILTRO */)
  .map(/* TU MAP */)
console.log("B5. Nombres activos:", nombresActivos)
```

---

## Checklist de entrega

- [ ] `tarea_arrays.ts` con todos los ejercicios de la Parte A resueltos
- [ ] `tarea_arrays_mvp.ts` con la interface y datos de tu MVP
- [ ] Ambos archivos corren sin errores con `ts-node`
- [ ] Carpeta `semana2/` con ambos archivos en el repositorio
- [ ] Commit con mensaje: `feat: tarea arrays semana 2`
- [ ] Issue del Milestone 2 movido a "Listo"

---

## Referencia rápida

| Método | Devuelve | Úsalo cuando... |
|--------|----------|-----------------|
| `filter(condición)` | array filtrado | quieres un subconjunto |
| `map(transformación)` | array transformado | quieres cambiar cada elemento |
| `find(condición)` | elemento o undefined | buscas uno por id o condición |
| `includes(valor)` | boolean | verificas si algo está en una lista |
| `filter() + map()` | array filtrado y transformado | combinas ambas necesidades |

**Truco pro:** Cuando `find()` puede devolver `undefined`, usa `?.` para acceder a sus propiedades:
```typescript
const p = productos.find(p => p.id === "p99")
console.log(p?.nombre)  // no explota si p es undefined
```
