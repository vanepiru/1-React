
<br/>![react](https://user-images.githubusercontent.com/6796155/135780131-ac6731b8-4149-46d6-bc6c-75a832f03dba.gif)


| |  Contenido                                           |                                                
|-----|----------------------------------------------------------|
| 01. |[React Introducción](#1-react-introducción) |
| 02. |[Historia](#3-historia) |
| 03. |[Caraterísticas Generales](#3-caraterísticas-generales) |
| 04. |[Create React App](#4-create-react-app) |
| 05. |[Dom](#5-dom) |
| 06. |[Dom Virtual vs Dom Real](#6-dom-virtual-vs-dom-real) |
| 07. |[Qué es un componente?](#7-qué-es-un-componente) |
| 08. |[Jsx](#8-jsx) |
| 09. |[Tips](#9-tips) |
| 10. |[Props](#10-props) |
| 11. |[Comentarios en react y jsx](https://github.com/vanepiru/react/blob/main/README.md#11-comentarios-en-react-y-jsx) |
| 12. |[¿Qué diferencia existe entre elemento y componente?](https://github.com/vanepiru/react/blob/main/README.md#12-qu%C3%A9-diferencia-existe-entre-elemento-y-componente) |
| 13. |[¿Qué es state en React?](https://github.com/vanepiru/react/blob/main/README.md#13-qu%C3%A9-es-state-en-react) |
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

Realizaremos una explicación de forma gráfica. Imaginemonos que disponemos de una tabla con datos en una página HTML.

![image](https://user-images.githubusercontent.com/6796155/135717521-36d33a40-27e3-4bf9-8e82-7d7e16441f68.png)


La tabla dispone de en cada fila de un botón de edición. Este botón permite cambiar de forma rápida los datos de la tabla. Por ejemplo podemos pulsar en la última fila y cambiar el dato9 por dato10.


![image](https://user-images.githubusercontent.com/6796155/135717536-f1291d45-8db5-4cff-9086-dda8546ef13b.png)


Cambios sin VirtualDOM
¿Como realizamos este operación? . En la mayor parte de las situaciones los desarrolladores optan por una solución similar a lo siguiente. La tabla se crea a partir de un array de objetos , este array de objetos es actualizado cuando editamos. Finalizada la edición la tabla se vuelve a generar.

![image](https://user-images.githubusercontent.com/6796155/135717673-90c70942-af7f-4916-9249-20957f9f61d7.png)


Nos encontramos ante un código que funciona correctamente pero que tiene un problema importante. ¿Era necesario volver a generar la tabla entera?. Se trata de una pregunta interesante ya que solo hemos cambiado un dato puntual. La respuesta  es NO. Acabamos de forzar al navegador a redibujar todo el bloque cuando solo un mínimo de información cambiaba.

El concepto de Virtual DOM

Cambiar los nodos de un árbol DOM tiene un coste , cuantos más nodos cambiemos mayor será el coste para el navegador. En situaciones sencillas los problemas de rendimiento no se notan pero cuanto más compleja y grande sea nuestra web estas cosas serán importantes. En este caso nos encontramos con una tabla de datos que define una parte del árbol DOM

 
![image](https://user-images.githubusercontent.com/6796155/135717934-927f689a-2df0-451a-949a-a7bfd7f1288b.png)

Lamentablemente cuando volvemos a dibujar la tabla estamos cambiando todos los nodos del árbol DOM y volviéndola a renderizar por completo. ¿Cómo funciona un enfoque de virtual DOM? . En este caso el framework o librería que corresponda se encarga de tener una copia de nuestro árbol DOM simplificado en memoria a la cual se denomina VirtualDOM.

![image](https://user-images.githubusercontent.com/6796155/135717965-5529faf6-743e-487f-bd79-c86eac8f5420.png)

Una vez que dispone de esta versión del árbol el framework se encarga de estar pendiente de los cambios que se generan sobre él. Siendo capaz de ver las diferencias entre un estado A y un estado B cuando nosotros actualizamos información.

![image](https://user-images.githubusercontent.com/6796155/135717806-4643df79-6aea-4c94-ad04-f2c4f7049321.png)

En este caso solo hemos cambiado un nodo del árbol:

![image](https://user-images.githubusercontent.com/6796155/135717792-8b55a404-5167-435d-8e39-7c93fb6683f6.png)

Con estos cambios mínimos el framework o librería se encargará de actualizar el árbol DOM original sin tenerlo que redibujar completo.

![image](https://user-images.githubusercontent.com/6796155/135717752-484d8692-2eda-4110-832c-24aa8d399b50.png)

Con este tipo de técnicas se reduce al mínimo las renderizados a nivel de navegador. El rendimiento se incrementará de forma considerable.

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## 7. ***Qué es un componente?***

Los componentes son bloques de construcción. Un componente es una clase o función de JavaScript que opcionalmente acepta entradas, es decir, propiedades (prop) y devuelve un elemento React que describe cómo debería aparecer una sección de la interfaz de usuario (interfaz de usuario).

Una aplicación de React está formada por varios componentes, cada uno de los cuales es responsable de generar un fragmento de HTML pequeño y reutilizable. Los componentes se pueden anidar dentro de otros componentes para permitir la construcción de aplicaciones complejas a partir de bloques de construcción simples.

Class Component

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
>

## 8. ***JSX***

JSX nos permite escribir elementos HTML en JavaScript y colocarlos en el DOM sin ningún método createElement () o appendChild (). JSX convierte etiquetas HTML en elementos de reacción. React usa JSX para crear plantillas en lugar de JavaScript normal. No es necesario usarlo, sin embargo, a continuación se presentan algunas ventajas que lo acompañan.

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

## 9. ***Tips***
- Solo puede haber un element padre
- La etiqueta class se llama className porque es una palabra reservada para react (class)
- Los Elementos se deben cerrar
- Los estilos deben colocarse con un objeto javascript
- Lo eventos deben también estar con camelCase

<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>

## 10. ***Props***

Las propiedades de un componente se pueden definir como los atributos de configuración para dicho componente. Son recibidos desde un nivel superior (normalmente al instanciar el componente) y por definición son inmutables, es decir, un componente no puede cambiar sus propias props.

Ejemplo de uso de los props pasandole las propiedades cuando se van a renderizar el DOM

```js
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponent extends React.Component{
  render(){
    return <div>Me llamo {this.props.name} y tengo {this.props.edad}</div>
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


## 11. ***Comentarios en react y jsx***

React comentarios:

```js
function App() {

  // Single line Comment

  /*
  * multi
  * line
  * comment
  **/

  return (
    <h1>My Application</h1>
  );
}
```

JSX comentarios:

```js
export default function App() {
  return (
    <div>
      {/* A JSX comment */}
      <h1>My Application</h1>
    </div>
  );
}
```

## 12. ***¿Qué diferencia existe entre elemento y componente?***

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

## 13. ***¿Qué es state en React?*** 

Son datos que se mantienen dentro de un componente, los cuales son locales o pertenece a ese componente específico.
un almacén de datos mutable de componentes y que además son autónomos. O sea, el estado pertenece una clase autónoma que cualquiera pueda importar y usar en su aplicación.
El propio componente actualizará el estado usando la función `setState ()`.
La típica utilización de los estados sería en tu componente de reloj, en que necesitas actualizar periódicamente la vista con los segundos.

```js
class TodoApp extends React.Component {

    this.state = {items: []}
};
```


<div align="right">
    <b><a href="#">↥  Volver al inicio</a></b>
</div>



## Conceptos Adicionales

-**Un gestor de paquetes como Yarn o npm**. Permite aprovechar un vasto ecosistema de paquetes de terceros, e instalarlos o actualizarlos de una manera fácil.
-**Un empaquetador como webpack o Parcel**. Permite escribir código modular y empaquetarlo junto en paquetes más pequeños que optimizan el tiempo de carga.
-**Un compilador como Babel**. Permite escribir Javascript moderno que aún así funciona en navegadores más antiguos.
