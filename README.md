
<br/>

| |  Contenido                                           |                                                
|-----|----------------------------------------------------------|
| 01. |[React Introduccion](#1-react-introducción) |
| 02. |[Historia](#3-historia) |
| 03. |[Caraterísticas Generales](#3-caraterísticas-generales) |
| 04. |[Create React App](#4-create-react-app) |
| 05. |[Dom](#5-dom) |
| 06. |[Dom Virtual vs Dom Real](#6-dom-virtual-vs-dom-real) |
| 07. |[Qué es un componente?](#7-qué-es-un-componente) |
| 08. |[¿Cuál es la diferencia entre componente y contenedor en React?](#8-cuál-es-la-diferencia-entre-componente-y-contenedor-en-react) |
| 09. |[Jsx](#9-jsx) |
| 10. |[Tips](#10-tips) |
| 11. |[Props](#11-props) |
| 12. |[Cómo importar y exportar componentes usando React.js](#12-cómo-importar-y-exportar-componentes-usando-reactjs) |
| 13. |[](#13-cuál-es-la-diferencia-entre-componente-y-contenedor-en-react) |
| 14. |[¿Qué diferencia existe entre elemento y componente?](#14-qué-diferencia-existe-entre-elemento-y-componente) |
| 15. |[Enumere algunas de las principales ventajas y limitaciones de React](#15-enumere-algunas-de-las-principales-ventajas-y-limitaciones-de-react) |
| 16. |[](#12-cuál-es-la-diferencia-entre-componente-y-contenedor-en-react) |
| 17. |[](#13-cuál-es-la-diferencia-entre-componente-y-contenedor-en-react) |
<br/>

## 1. ***React Introducción***
React se define como una librería Javascript focalizada en el desarrollo de interfaces de usuario.
El principal objetivo de ReactJS es desarrollar interfaces de usuario (UI) que mejoren la velocidad de las aplicaciones. Utiliza DOM virtual (objeto JavaScript), que mejora el rendimiento de la aplicación. El DOM virtual de JavaScript es más rápido que el DOM real.


<div align="right">
    <b><a href="#">↥ Volver al inicio</a></b>
</div>


## 2. ***Historia***
- Creado por Jordan Walke, un ingeniero en software de Facebook
- Implementado en las noticias de Facebook en 2011 y luego por instagram en 2012
- Fue de código abierto en JSConf US en mayo de 2013
- El 26 de septiembre de 2017 fue lanzado al público React 16.0 y El 16 de febrero de 2019,  React 16.8.


<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>


## 3. ***Caraterísticas Principales***

- **Declarativo**: React hace que sea sencillo crear interfaces de usuario interactivas. Diseña vistas simples para cada estado de tu aplicación, y React actualizará y renderizará eficientemente los componentes correctos cuando cambien los datos. Las vistas declarativas hacen que el código sea más predecible, más sencillo de entender y más fácil de depurar.
- **Basado en componentes**: Crea componentes encapsulados que administran su propio estado y luego organizalos para crear interfaces de usuario complejas. Dado que la lógica de componentes está escrita en JavaScript y no sobre plantillas, puedes manejar fácilmente datos enriquecidos a través de la aplicación y mantener el estado fuera del DOM.

Lin https://es.reactjs.org/

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>


## 4. ***Create React App***

Necesitarás tener Node >= 14.0.0 y npm >= 5.6 instalados en tu máquina. Para crear un proyecto ejecuta:

```js
npx create-react-app my-app
cd my-app
npm start 
```
Create React App no se encarga de la lógica de backend o de bases de datos; tan solo crea un flujo de construcción para frontend, de manera que lo puedes usar con cualquier backend. Para ello internamente usa Babel y webpack, pero no necesitas saber nada de estas herramientas para usar Create React App.

Cuando estés listo para desplegar a producción, ejecuta

```js
npm run build 
```
lo cual crea una compilación optimizada de tu aplicación en el directorio build

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>


## 5. ***Dom***

**Document Object Model** 

El DOM, acrónimo de Document Object Model, es la herramienta base para manipular cualquier página web. El DOM es generado por el navegador que uses (Chrome, Firefox, etc) en el momento en que el documento HTML de una web se carga.
Ese documento HTML de una web se carga en un navegador, el navegador crea un objeto (un Document Object) basado en dicho documento HTML. Este Document Object contiene múltiples propiedades y métodos que nos permiten interactuar con esa web usando nuestro código JS.

A ese objeto creado por el navegador, con todas sus propiedades y métodos, se le llama el ​Document Object Model.

![image](https://user-images.githubusercontent.com/6796155/135715642-cbed0acb-bcc2-468f-8754-4324921cee8f.png)

El DOM estructura nuestra web en HTML nodes (nodos), donde cada etiqueta de HTML sería un node que podría tener etiquetas "hijas", formando así una estructura de árbol, o jerarquía de nodos. 

Nodes tree

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## 6. ***Dom Virtual vs Dom Real***


<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>
## 7. ***Qué es un componente?***

Los componentes son bloques de construcción. Un componente es una clase o función de JavaScript que opcionalmente acepta entradas, es decir, propiedades (accesorios) y devuelve un elemento React que describe cómo debería aparecer una sección de la interfaz de usuario (interfaz de usuario).

Una aplicación de React está formada por varios componentes, cada uno de los cuales es responsable de generar un fragmento de HTML pequeño y reutilizable. Los componentes se pueden anidar dentro de otros componentes para permitir la construcción de aplicaciones complejas a partir de bloques de construcción simples.

**Ejemplo:** Class Component

```js
class Welcome extends React.Component {
  render() {
    return <h1>Hola, Mundo!</h1>
  }
}
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## 8. ***¿Cuál es la diferencia entre componente y contenedor en React?***

Los componentes de presentación están relacionados con la apariencia, los componentes del contenedor están relacionados con hacer que las cosas funcionen.

Por ejemplo, este es un componente de presentación. Obtiene datos de sus accesorios y solo se enfoca en mostrar un elemento.

```js
const Users = props => (
  <ul>
    {props.users.map(user => (
      <li>{user}</li>
    ))}
  </ul>
)
```

Por otro lado, este es un componente contenedor. Gestiona y almacena sus propios datos y utiliza el componente de presentación para mostrarlos.

```js
class UsersContainer extends React.Component {
  constructor() {
    this.state = {
      users: []
    }
  }

  componentDidMount() {
    axios.get('/users').then(users =>
      this.setState({ users: users }))
    )
  }

  render() {
    return <Users users={this.state.users} />
  }
}
```
<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## 9. ***JSX***

SX nos permite escribir elementos HTML en JavaScript y colocarlos en el DOM sin ningún método createElement () o appendChild (). JSX convierte etiquetas HTML en elementos de reacción. React usa JSX para crear plantillas en lugar de JavaScript normal. No es necesario usarlo, sin embargo, a continuación se presentan algunas ventajas que lo acompañan.

Es más rápido porque realiza la optimización al compilar código en JavaScript.
También es de tipo seguro y la mayoría de los errores se pueden detectar durante la compilación.
Hace que escribir plantillas sea más fácil y rápido.
Ejemplo:

'''js
import React from 'react'

class App extends React.Component {

   render() {
      return (
         <div>
            Hello World!
         </div>
      )
   }
}
export default App
'''

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## 10. ***Tips***
- Solo puede haber un element padre
- La etiqueta class se llama className porque es una palabra reservada para react (class)
- Los Elementos se deben cerrar
- Los estilos deben colocarse con un objeto javascript
- Lo eventos deben también estar con camelCase

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## 11. ***Props***

Las propiedades de un componente se pueden definir como los atributos de configuración para dicho componente. Son recibidos desde un nivel superior (normalmente al instanciar el componente) y por definición son inmutables, es decir, un componente no puede cambiar sus propias props.

Ejemplo de uso de los props pasandole las propiedades cuando se van a renderizar el DOM

```js
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponent extends React.Component{
  render(){
    return <div>Me llamo {this.props.name} y tengo {this.props.anos}</div>
  }
}

export default MyComponent;
```
Aqui es donde se le pasan las propiedades name y edad en el app.js

```js
import React from 'react';
import ReactDOM from 'react-dom';
import MyComponent from "./components/ejemplo_props";

const app = document.getElementById('app');
ReactDOM.render(<MyComponent name = "jose" anos = "22" /> , app);

```
Otra forma de hacerlo sería pasando las propiedades por defecto

```js
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponent extends React.Component{
  render(){
    return (<div>Me llamo {this.props.name} y tengo {this.props.edad}</div>)
  }
}

MyComponent.defaultProps = {
  name:'Jose',
  edad:'22'
};

ReactDOM.render(
  <MyComponent />,
  document.getElementById('app')
);
```
<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## 12. ***Cómo importar y exportar componentes usando React.js***

```js
//Importar combinaciones
import React, { Component } from 'react';
import ReactDOM from 'react-dom';

// Envolver componentes con llaves si no hay exportaciones predeterminadas
import { Button }  from './Button';

// Default exports ( recommended )
import  Button  from './Button';
 
class DangerButton extends Component {
    render()
    {
        return <Button color="red" />;
    }
}

export default DangerButton; 
// o export DangerButton;
```
<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>
## 13. ***Cómo crear una tabla dinámica en react***

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## 14. ***¿Qué diferencia existe entre elemento y componente?***

**React Element**

Es un objeto simple que describe un nodo DOM y sus atributos o propiedades. Es un objeto de descripción inmutable y no se le puede aplicar ningún método.

```js
const element = <h1>React Element Example!</h1>;
ReactDOM.render(element, document.getElementById('app'));
```

**&#9885; [Try this example on CodeSandbox](https://codepen.io/learning-zone/pen/poPrJLb?editors=1010)**

**React Componente**

Es una función o clase que acepta una entrada y devuelve un elemento React. Tiene que mantener referencias a sus nodos DOM y a las instancias de los componentes secundarios.

```js
function Message() {
  return <h2>React Component Example!</h2>;
}
ReactDOM.render(<Message />, document.getElementById('app'));
```

**&#9885; [Try this example on CodeSandbox](https://codepen.io/learning-zone/pen/dyWzoqg?editors=0010)**

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

### 15. ***Enumere algunas de las principales ventajas y limitaciones de React***

** Ventajas: **

* Se basa en un dom virtual para saber lo que realmente está cambiando en la interfaz de usuario y volverá a renderizar solo lo que realmente ha cambiado, por lo tanto, un mejor rendimiento.
* JSX hace que el código de componentes / bloques sea legible. Muestra cómo se conectan o combinan los componentes.
* El enlace de datos de React establece las condiciones para la creación de aplicaciones dinámicas.
* Representación rápida. El uso de métodos comprende para minimizar el número de operaciones DOM ayuda a optimizar el proceso de actualización y acelerarlo.
Comprobable. Las herramientas nativas de React se ofrecen para probar y depurar código.
* Compatible con SEO. React presenta la experiencia de primera carga mediante la representación del lado del servidor y la conexión de los controladores de eventos del lado del usuario:
    * Se llama a React.renderComponentToString en el servidor.
    * React.renderComponent () se llama en el lado del cliente.
    * React conserva el marcado renderizado en el lado del servidor, adjunta controladores de eventos.

** Limitaciones: **

* Curva de aprendizaje. Al no ser un marco con todas las funciones, se requiere un conocimiento profundo para la integración de la biblioteca gratuita de la interfaz de usuario en el marco MVC.
* La orientación visual es una de las desventajas de ReactJS. Se debe encontrar 'Modelo' y 'Controlador' para resolver el problema de 'Vista'.
* No utilizar un enfoque isomórfico para explotar la aplicación conduce a problemas de indexación en los motores de búsqueda.

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

### 15. ***¿Por qué React enfatiza el flujo de datos unidireccional?***

También se conoce como flujo de datos unidireccional, lo que significa que los datos tienen una y solo una forma de transferirse a otras partes de la aplicación. En esencia, esto significa que los componentes secundarios no pueden actualizar los datos que provienen del componente principal. En React, los datos que provienen de un padre se denominan ** props **.

En React, esto significa que:

* el estado se pasa a la vista y a los componentes secundarios
* las acciones son activadas por la vista
* las acciones pueden actualizar el estado
* el cambio de estado se pasa a la vista y a los componentes secundarios

La vista es el resultado del estado de la aplicación. El estado solo puede cambiar cuando ocurren acciones. Cuando ocurren acciones, el estado se actualiza. El enlace de datos unidireccional nos proporciona algunas ventajas clave

* Más fácil de depurar, ya que sabemos qué datos provienen de dónde.
* Menos propenso a errores, ya que tenemos más control sobre nuestros datos.
* Más eficiente, ya que la biblioteca sabe cuáles son los límites de cada parte del sistema.

En React, un estado siempre es propiedad de un componente. Cualquier cambio realizado por este estado solo puede afectar a los componentes debajo de él, es decir, sus "hijos". Cambiar el estado de un componente nunca afectará a su padre ni a sus hermanos, solo los hijos se verán afectados. Esta es la razón principal por la que el estado a menudo se mueve hacia arriba en el árbol de componentes para que se pueda compartir entre los componentes que necesitan acceder a él.

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

### 16. ***¿Cuáles son las diferencias entre un componente de clase y un componente funcional?***
### **Functional Components**  

** Componentes funcionales **

* Los componentes funcionales son funciones básicas de JavaScript. Por lo general, estas son funciones de flecha, pero también se pueden crear con la palabra clave de función normal.
* A veces se los denomina componentes "sin estado", ya que simplemente aceptan datos y los muestran de alguna forma; es decir, son los principales responsables de renderizar la interfaz de usuario.
* Los métodos del ciclo de vida de React (por ejemplo, `componentDidMount ()`) no se pueden usar en componentes funcionales.
* No se utiliza ningún método de renderizado en componentes funcionales.
* Son los principales responsables de la interfaz de usuario y suelen ser solo de presentación (por ejemplo, un componente de botón).
* Los componentes funcionales pueden aceptar y utilizar accesorios.
* Deben favorecerse los componentes funcionales si no necesita hacer uso del estado React.

**Ejemplo:**

```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="World!" />;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

**&#9885; [Try this example on CodeSandbox](https://codepen.io/learning-zone/pen/MWmEmRj?editors=0010)**

### ** Componentes de clase **

* Los componentes de la clase hacen uso de la clase ES6 y amplían la clase Component en React.
* A veces se denominan componentes "con estado", ya que tienden a implementar lógica y estado.
* Los métodos del ciclo de vida de React se pueden usar dentro de los componentes de la clase (por ejemplo, `componentDidMount ()`).
* Pasamos `props` a los componentes de la clase y accedemos a ellos con` this.props`.
* Los componentes basados ​​en clases pueden tener "referencias" a los nodos DOM subyacentes.
* Los componentes basados ​​en clases pueden utilizar técnicas de optimización del rendimiento `shouldComponentUpdate ()` y `PureComponent ()`.

**Ejemplo:**

```js
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

const element = <Welcome name="World!" />;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

**&#9885; [Try this example on CodeSandbox](https://codepen.io/learning-zone/pen/BaRwZyB)**


<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## Conceptos Adicionales

- **Un gestor de paquetes como Yarn o npm**. Este te permite aprovechar el vasto ecosistema de paquetes de terceros, e instalarlos o actualizarlos de una manera fácil.
-	**Un empaquetador como webpack o Parcel**. Este te permite escribir código modular y empaquetarlo junto en paquetes más pequeños que optimizan el tiempo de carga.
- **Un compilador como Babel**. Este te permite escribir Javascript moderno que aún así funciona en navegadores más antiguos.
