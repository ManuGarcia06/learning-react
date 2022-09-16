
# ¿Que es REACT?
Es una "**libreria**" de javascript es de código abierto fue diseñada para crear interfaces de usuarios (open source).

# Ventajas de aprender REACT

- Fácil de aprender y usar
- Tiene componentes reutilizables
- Crear aplicaciones dinámicas.
- Buen desempeño.

# Conceptos básicos
- **Componente**: Es parte de la interfaz de usuario que es independiente y reusable (cada componente tiene un estado).
    - Estos se comportan como bloques
    - Se pueden definir en dos catergorias (principales)
        - Funcionales:
            - Simplemente es una funcion de javascript. Esta funcion retorna un elemento de react en (JSX). Por ejemplo:
            ```jsx
            function Saludo(props) { // <= Saludo es el nombre del componente
                return <h1> Hello, {props.name} </h1>
            }
            ```` 
            - Caracteristicas:
                - Debe retornar un elemento React JSX
                - Los componentes deben de comenzar con mayúscula.
                - Puede recibir valores si es necesario ya que usa javascript. Generalmente se usa props (propiedades).

        - De clase: Se usaban en versiones anteriores, pero es mejor usar los funcionales.
            - Es una clase de ES6 que retorna un elemento JSX (sintaxis más elaborada). Por ejemplo:
            ```jsx
            class Saludo extends React.Component {
                render() {
                    return <h1> Hello, {this.props.name} </h1>
                }
            }
            ```
            - Caracteristicas:
                - Debe extender **React.Component**. Es importante para no crear una clase normal de javascript si no que extiende la funcionalidad de React lo cual te permite usar todo lo de React
                - Debe tener un metodo **render()**. Este define que es lo que se va a mostrar en el front y puede recibir valores (props). Cuando se usa una clase de debe de usar **this.props**.
    - ¿Por qué Componentes de Clase? 
        - Antes se usaban **Componentes de Clase** para poder trabajar con "estados" de los componentes. En versiones anteriores a la 16.8 no se podía hacer con **Componentes Funcionales**.



- **Props**:
    - Son *argumentos* que se puede recibir en un componente de React. 
    - Se puede tener componente dentro de otros componentes.
    - Los props solo pueden ser enviados "padre e hijo".

- **Estado (state)**: Es la representación en JavaScript del conjunto de propuedades de un componente y sus valores actuales.
    - ***En este concepto, "propiedades" NO se refiere a los props, sino a informacion que se representa sobre el componente***

- **Hooks**: Permite agregar la funcionalidad de estados a los **Componentes Funcionales**. Con esto ya se puede asignar y actualizar el estado de un componente funcional.
    - Definicion: Es una funcion especial que permite trabajar con estados en componentes funcionaes y en otros aspectos de React, además, permite manejar más cosas dentro del componente funcional.

- Event Listener:
    - Es una función en JavaScript (event handler) que es ejecutada cuando ocurre un evento específico. 

# Node.js
Permite ejecutar código JavaScript fuera de un explorador 

# Introducción a JSX
Es una extension de React para esxribir javascript (jsx = javascript + xml)

- Nos permite describir en javascript como se verán los componentes usando una estructura similar a HTML (su estructura no necesariamente es su estilo).

- Ventajas:
    - Estructura más fácil de visualizar.
    - Errores y advertencias más útiles.

``` txt
NOTA: JSX es opcional
```

- Elementos: 
    - Son las unidades más pequeñas en React (mas pequeñas que un componente). Define lo que se ve en la pantalla.
    - Con JSX puedes crear y usar cualquier elemento HTML.
    ``` html
    <div>
    <img>
    <a>
    <header>
    <nav>
    <p>
    <h1>
    <button>
    <h2>
    .
    .
    .
    ```
    - ¿Como reconocer un Componente de un Elemento? Por medio de sus etiquetas. En JSX, los elementos se representan con letras minusculas (el editor que se use también ayuda ver la diferencia entre ambos).

- Elemento vs Componente:
    - Los componentes estan hechos de elementos (tags de html)

- DOM:
    - Document Object Model (Modelo de objeto del documento). Representa los elementos.

- React DOM: 
    - Pquete que facilita la itneraccion y actualización del DOM en aplicaiones React.

- Atributos de JSX
    - Se puede agregar atributos a los elementos de JSX para especificar ciertas caracteristicas.
    - Algunos atributos se escriben de forma distinta a HTML. Por ejemplo:
        - JSX (cammelCase):
        ``` jsx
        <h1 className="titulo-azul"></h1>
        <label htmlFor="css">CSS</label>
        ```
        - HTML:
        ``` html
        <h1 class="titulo-azul"></h1>
        <label for="css">CSS</label>
        ```
    - El atributo **style** acepta objeto JavaScript con propiedades CSS escritas en camelCase.
        - JSX (cammelCase):
        ``` jsx
        <h1 style="backgroundImage: red"></h1>
        // Tambien se puede definir por llaves
        const estiloDiv = {
            color: red,
            backgroundColor: white
        }
        // Para referenciar las propuedades del style debe ir eltre llaves '{}'
        const value = <div style={ estiloDiv }> Hello there!</div> 

        // Tenemos otra alternativa en la que no se tienen muchas propiedades
        // Las primeras llaves son parte de la sintaxis, y la segundas llaves hacen referencia al ejemplo previo
        const value = <div style={{ color: 'yellow' }}> Hello there!</div> 
        ```
        - HTML:
        ``` html
        <h1 style="background-image: red"></h1>
        ```
- Estructura de un Componente: 
    - Al igual que en HTML los elementos pueden estar anidados puedes tener elementos dentro de componentes y se puede tener elemntos dentro de elementos. Es importante **la indentación**
    - Renderizar componentes: Dentro del proyecto siempre existirá un 'div' que contendrá el id root. Dentro de este div se renderizará todo nuestro componente. Para eso en el archivo HTML deberá verse algo tal que:
    ``` html
    <div id='root'>
        <!-- Aquí se renderizará el codigo JSX de React -->
    </div>
    ```
    Y en nuestro archivo de JavaScript veremos algo así:
    ``` jsx
    import ReactDOM from 'react-dom'    // Se requiere importar esta librería para usar ReactDOM

    const element = <h1> Hello world </h1> // Elemento a renderizar

    ReactDOM.render(                    // Para utilizar ReactDom se requiere importar esta librería
        element,                        // Que se requiere renderizar
        document.getElementById('root') // En donde se requiere renderizar, en este caso en el que tenga el id=root
    )
    ```

- Self-Closing tags
    - Es un elemento que solo posee una etiqueta de apertura la cual no contiene contenido (texto u otros elementos).
        - HTML 
        ``` html
        <img src="logo.png" alt="Imagen">
        ```
        - JSX 
        ``` html
        <img src="logo.png" alt="Imagen" /> <!-- Note la barra que se cierra al final -->
        ```
- Código de JavaScript en JSX
    - Se escribe dentro de '{}' (llaves)
        - JSX 
            ``` jsx
            let adjetivo = "Interesante"

            <p>
                { adjetivo }
            </p>
            ```
    - Se puede escribir cualquier expresion:
        - JSX 
            ``` jsx
            <p>
                { 5*2*3 }
            </p>
            ```
    - Se puede llamar un metodo:
        - JSX 
            ``` jsx
            <p>
                Su nombre es: { nombre.upperCase() }
            </p>
            ```

# Crear una Aplicación de React
