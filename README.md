# Reto swapi

<img src="./the-art-of-programming.webp" width="400" alt="Time to code">

Desde la siguiente __URL__ [https://swapi.dev/](https://swapi.dev/) obtendremos información de diversa índole sobre personajes, planetas y naves de Star Wars.

Interesa crear un acceso a un __end point__ para obtener información de un personaje de la guerra de las galaxias.


- [] Crear un nuevo proyecto en __Vite__ que podemos llamar __swapi-project__
- [] Crear un __mock__ donde poder mostrar la información sin tener que utilizar la __fetch API__.
  - Podemos mostrar la información en este punto por la consola del navegador
- [] Realizar el fetching de datos después de los puntos anteriores

## Suplementario

- [] La información anterior en vez de mostrarla por consola la debemos mostrar en una página web.
- [] Darle un diseño a la página para que esta se vea elegante. Se puede intalar librerías como:
  - bootstrap

## Para expertos

- [] Para evitar tener que hacer una llamada cada vez que se refresca la llamada cada vez que se refresca a pantalla es necesario que los datos se queden almacenados en el navegador

## Lo que necesitas saber JavaScript 

### import / export

1. Exportación: primitivos, no primitivos, funciones

```js
export let variable_name
export function function_name() {
  // Statements
}
export const USUARIO = { name: 'Xurxo', edad: 50 }
```

2. Exportación por defecto

```js
export default function app () {
    // Statements
}
```

3. Importaciones (nombradas y por defecto)

```js
import miApp, { variable_name, USUARIO, function_name } from 'path_to_file'
```
### fetch

[fetch](https://github.com/webferrol/react-session#fetch)

En el ejemplo que veremos a continuación el __input__ será un __string__ que representa la localización del recurso de red que deseamos obtener. En este caso un fichero plano __json__ que posteriormente lo convertiremos en un __objeto javascript__ con el método __json()__

```js
fetch('https://swapi.dev/api/people/1')
  .then((response) => { return response.json() })
  .then(data => { console.log(data) })
```
La forma resumida de lo anterior

```js
fetch('https://swapi.dev/api/people/1')
  .then(response => response.json()) // El return implícito funciona siempre y cuando no pongamos las llaves
  .then(data => console.log(data))
```

### localStorage

__LocalStorage__ es una __API__ de almacenamiento web que permite a los desarrolladores almacenar datos de forma local en el navegador del usuario. Los datos almacenados en LocalStorage persisten incluso después de que el usuario cierre la pestaña o el navegador.

LocalStorage se utiliza comúnmente para almacenar datos de usuario, como preferencias, configuraciones o datos de sesión. Por ejemplo, una aplicación web podría utilizar LocalStorage para almacenar el idioma preferido del usuario o el estado de inicio de sesión del usuario.

Recalcar que esta __API__ está pensado para almacenar strings, para almacenar objetos sigamos el siguiente ejemplo:

```js
const user = {
  name: "John Doe",
  age: 30,
  occupation: "Software Engineer",
}

localStorage.setItem("user", JSON.stringify(user))
```

Y pra leerlo

```js
const userJSON = localStorage.getItem("user") // Este código devolverá el objeto user codificado en formato JSON
const user = JSON.parse(userJSON) // Para decodificar el objeto, puedes utilizar la función JSON.parse()
