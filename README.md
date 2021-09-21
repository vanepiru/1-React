# React Introducción
> React se define como una librería Javascript focalizada en el desarrollo de interfaces de usuario.

## Historia
- Creado por Jordan Walke, un ingeniero en software de Facebook
- Implementado en las noticias de Facebook en 2011 y luego por instagram en 2012
- Fue de código abierto en JSConf US en mayo de 2013
- El 18 de abril de 2017, Facebook anunció React Fiber
- El 26 de septiembre de 2017, React 16.0 fue lanzado al público. El 16 de febrero de 2019, React 16.8 fue lanzado al público

## Caraterísticas Generales
- **Declarativo**: React hace que sea sencillo crear interfaces de usuario interactivas. Diseña vistas simples para cada estado de tu aplicación, y React actualizará y renderizará eficientemente los componentes correctos cuando cambien los datos. Las vistas declarativas hacen que el código sea más predecible, más sencillo de entender y más fácil de depurar.
- **Basado en componentes**: Crea componentes encapsulados que administran su propio estado y luego organizalos para crear interfaces de usuario complejas. Dado que la lógica de componentes está escrita en JavaScript y no sobre plantillas, puedes manejar fácilmente datos enriquecidos a través de la aplicación y mantener el estado fuera del DOM.
- **Aprende solamente una vez, escribe código donde sea**: Puedes desarrollar nuevas funciones en React sin reescribir el código existente. React también puede renderizarse sobre el servidor a través de Node JS y permite potenciar tus aplicaciones móviles usando React Native.

LInk https://es.reactjs.org/

## Create React App 

Necesitarás tener Node >= 14.0.0 y npm >= 5.6 instalados en tu máquina. Para crear un proyecto ejecuta:

```
npx create-react-app my-app
cd my-app
npm start 
```


## Qué es el Dom?


## Dom Virtual vs Dom Real


## JSX

React utiliza una sintaxis basada en XML (similar al HTML) para construir sus componentes usando el Virtual DOM


## Tips!


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
