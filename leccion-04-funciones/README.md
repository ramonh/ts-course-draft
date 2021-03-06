# Unidad 1, Lecci贸n 4: Funciones

Ahora le agregaremos tipos a nuestras funciones en TypeScript!

Tal como podemos declarar variables con tipos, lo mismo se puede hacer con funciones.

## 馃惥 Primeros Pasos

C谩da parametro de una funci贸n puede definirse con un tipo. Por ejemplo:

```typescript
const publicarAdicion = (x: number, y: number) => {
    console.log(x + y);
};
```

No s贸lo eso, pero tambi茅n permiten definir un tipo de retorno, y con esto asegurar que la funci贸n nos da lo que dice:

```typescript
const adicion = (x: number, y: number): number => x + y;
```

Pero 驴qu茅 pasa cuando no definimos un tipo de retorno? En JavaScript, una funci贸n que no devuelve nada en realidad devuelve `undefined`. En TypeScript, es casi lo mismo:

```typescript
console.log(typeof publicarAdicion(1, 2))); // => undefined
```

Sin embargo, `undefined` es un valor, no un tipo! En este caso, podemos definir el tipo de retorno de una funci贸n que no devuelve nada como `void`:

```typescript
const publicarAdicion = (x: number, y: number): void => {
    console.log(x + y);
};
```

Esta definici贸n de `publicarAdicion` es equivalente a la anterior.

## 馃 Metas

En esta lecci贸n, vamos a:
- Definir nuestra primera funci贸n con TypeScript
- Agregar declaraciones de tipos a funciones

## 馃じ Ejercicios

### 1. Nueva funci贸n de utilidad

En `./src/components/PostList.tsx`, en la l铆nea 3, importamos la funci贸n `formatPostTimestamp`:

```typescript
import formatPostTimestamp from '../utils/formatters'
```

Y la usamos en la l铆nea 11:

```typescript
<p className="small right">{formatPostTimestamp(post)}</p>
```

Agreguemos en el nuevo archivo `./src/utils/formatters.ts`. Tendr谩 una funci贸n formatPostTimestamp:

- Toma como argumento un `post` de tipo `Post`
- Retorna un `Date` formatteado: `return new Date(post.timestamp).toLocaleString("es");`

### 3. Darle tipos a los argumentos de la funci贸n an贸nima

Volvamos a `./src/components/PostList.tsx`, donde encontraremos una funci贸n an贸nima en la linea 7:

```typescript
let rows = posts.map((post, index) => {
```

隆Introduzcamos tipos para los argumentos!

### Cr茅dito extra: Prop Types

En la l铆nea 5, definimos nuestro componente con propiedades como un objeto:

```typescript
function PostList({posts}) {
```

Extraigamos un interfaz local para los `Props` que tengan como propediad un arreglo de `posts`.

## 馃 Reflexiones

- 驴Qu茅 tipo de retorno tendr谩 `formatPostTimestamp`?
