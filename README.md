
<br/>

|Sl.No|   Questions                                              |                                                
|-----|----------------------------------------------------------|
| 01. |[React Introduccion](#q-what-is-reactjs) |
| 02. |[Historia](#3-historia) |
| 03. |[Caraterísticas Generales](#3-caraterísticas-generales) |
| 04. |[Create React App]|


<br/>

## 1. ***React Introducción***
React se define como una librería Javascript focalizada en el desarrollo de interfaces de usuario.
El principal objetivo de ReactJS es desarrollar interfaces de usuario (UI) que mejoren la velocidad de las aplicaciones. Utiliza DOM virtual (objeto JavaScript), que mejora el rendimiento de la aplicación. El DOM virtual de JavaScript es más rápido que el DOM real.


<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>


## 2. ***Historia***
- Creado por Jordan Walke, un ingeniero en software de Facebook
- Implementado en las noticias de Facebook en 2011 y luego por instagram en 2012
- Fue de código abierto en JSConf US en mayo de 2013
- El 18 de abril de 2017, Facebook anunció React Fiber
- El 26 de septiembre de 2017, React 16.0 fue lanzado al público. El 16 de febrero de 2019, React 16.8 fue lanzado al público


<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>


## 3. ***Caraterísticas Generales***
- **Declarativo**: React hace que sea sencillo crear interfaces de usuario interactivas. Diseña vistas simples para cada estado de tu aplicación, y React actualizará y renderizará eficientemente los componentes correctos cuando cambien los datos. Las vistas declarativas hacen que el código sea más predecible, más sencillo de entender y más fácil de depurar.
- **Basado en componentes**: Crea componentes encapsulados que administran su propio estado y luego organizalos para crear interfaces de usuario complejas. Dado que la lógica de componentes está escrita en JavaScript y no sobre plantillas, puedes manejar fácilmente datos enriquecidos a través de la aplicación y mantener el estado fuera del DOM.
- **Aprende solamente una vez, escribe código donde sea**: Puedes desarrollar nuevas funciones en React sin reescribir el código existente. React también puede renderizarse sobre el servidor a través de Node JS y permite potenciar tus aplicaciones móviles usando React Native.

Lin https://es.reactjs.org/

<div align="right">
    <b><a href="#">↥ back to top</a></b>
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
    <b><a href="#">↥ back to top</a></b>
</div>


## 5. ***Qué es el Dom?***

**Document Object Model** 
EL DOM posee una estructura en forma de árbol:

![image](https://user-images.githubusercontent.com/6796155/134211026-31e3c56f-f7dc-4946-8b42-44486ea9e99a.png)


Esto provoca que cada vez que modificamos un elemento dentro de él, todos sus hijos tengan que ser pintados de nuevo (hayan o no cambiado). Y justo este proceso es el que provoca los problemas de rendimiento. Por tanto, cuantos más elementos queden por debajo de nuestro elemento modificado en la estructura del DOM más elementos tendrán que ser vueltos a pintar en la interfaz gráfica.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## 6. ***Dom Virtual vs Dom Real***


## 7. ***Qué es un componente?***

Los componentes son bloques de construcción. Un componente es una clase o función de JavaScript que opcionalmente acepta entradas, es decir, propiedades (accesorios) y devuelve un elemento React que describe cómo debería aparecer una sección de la interfaz de usuario (interfaz de usuario).

Una aplicación de React está formada por varios componentes, cada uno de los cuales es responsable de generar un fragmento de HTML pequeño y reutilizable. Los componentes se pueden anidar dentro de otros componentes para permitir la construcción de aplicaciones complejas a partir de bloques de construcción simples.

**Ejemplo:** Class Component

```js
class Welcome extends React.Component {
  render() {
    return <h1>Hello, World!</h1>
  }
}
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## JSX

React utiliza una sintaxis basada en XML (similar al HTML) para construir sus componentes usando el Virtual DOM


## Tips!
- Solo puede haber un element padre
- La etiqueta class se llama className porque es una palabra reservada para react (class)
- Los Elementos se deben cerrar
- Los estilos deben colocarse con un objeto javascript
- Lo eventos deben también estar con camelCase

## Props

Las propiedades de un componente se pueden definir como los atributos de configuración para dicho componente. Son recibidos desde un nivel superior (normalmente al instanciar el componente) y por definición son inmutables, es decir, un componente no puede cambiar sus propias props.

Ejemplo de uso de los props pasandole las propiedades cuando se van a renderizar el DOM

```
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

```
import React from 'react';
import ReactDOM from 'react-dom';
import MyComponent from "./components/ejemplo_props";

const app = document.getElementById('app');
ReactDOM.render(<MyComponent name = "jose" anos = "22" /> , app);
Otra forma de hacerlo sería pasando las propiedades por defecto

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

## Conceptos Adicionales

- **Un gestor de paquetes como Yarn o npm**. Este te permite aprovechar el vasto ecosistema de paquetes de terceros, e instalarlos o actualizarlos de una manera fácil.
-	**Un empaquetador como webpack o Parcel**. Este te permite escribir código modular y empaquetarlo junto en paquetes más pequeños que optimizan el tiempo de carga.
- **Un compilador como Babel**. Este te permite escribir Javascript moderno que aún así funciona en navegadores más antiguos.
