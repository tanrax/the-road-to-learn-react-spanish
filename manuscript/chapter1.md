# Introducción a React

Este capítulo sirve como una introducción a React. Quizá te preguntas: ¿Por qué debería aprender React, en primer lugar? Aquí encontrarás la respuesta a esta interrogante. Y después, te sumergirás en el ecosistema al crear tu primera aplicación utilizando la librería React. En el camino además conocerás JSX y ReactDOM. Así que prepárate para darle vida a tu primer componente React.

## Hola, mi nombre es React.

**¿Por qué deberías aprender React?** En los últimos años las Single Page Applications o Aplicaciones de Página Única ([SPA por sus siglas en Inglés](https://es.wikipedia.org/wiki/Single-page_application)) se han vuelto populares. Frameworks como Angular, Ember y Backbone ayudaron a los desarrolladores JavaScript a construir aplicaciones web modernas más allá de lo que se podía lograr usando JavaScript puro (Vanilla JavaScript) y jQuery. Existe una amplia gama de frameworks SPA. De los que acabamos de mencionar, la mayoría pertenece a la primera generación de SPAs: Angular 2010, Backbone 2010, Ember 2011.

La versión inicial de React fue lanzada en 2013 por Facebook. React no es un framework SPA, pero sí una librería para la capa de vistas. Es la V en el Modelo Vista Controlador [(MVC por sus siglas en Inglés)](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador). Esta librería sólo permite renderizar componentes como elementos visibles en un navegador. Sin embargo, gracias a todo el ecosistema React, es posible crear aplicaciones de una sola página.

¿Pero, por qué deberías considerar usar React en vez de algún framework SPA de primera generación? Mientras que la primera generación de frameworks trató de resolver muchas cosas a la vez, React se enfoca en construir la capa de vista, React es una biblioteca y no un framework. Y se basa en que la capa Vista es una jerarquía de componentes ensamblables.

En React puedes centrarte en la capa de Vistas antes de agregar más aspectos a tu aplicación. Cada otro aspecto representará otro componente de la SPA. Pensar en bloques de construcción es esencial para construir una aplicación madura y tiene dos ventajas.

Primero, puedes aprender a usar los bloques de construcción paso a paso, sin preocuparte por entenderlos totalmente desde el principio. Esto es muy diferente a un Framework que incluye todo el set de bloques de construcción desde que inicias el proyecto.

Este libro presenta a React como el primer bloque de construcción. Más bloques de construcción vendrán luego.

En segundo lugar, todos los bloques de construcción son intercambiables. Lo que hace del ecosistema React algo innovador donde múltiples soluciones compiten entre sí para solucionar un problema, así que puedes elegir la solución más atractiva para ti y tu caso de uso.

La primera generación de Frameworks SPA suelen ser muy rígidos. React por su parte, permanece innovador y es adoptado por empresas líderes en tecnología cómo [Airbnb, Netflix y por supuesto Facebook](https://github.com/facebook/react/wiki/Sites-Using-React). Todas estas invierten en el crecimiento de React y su ecosistema.

Hoy en día, React es probablemente una de las mejores opciones para la construcción de aplicaciones de una sola página.

React sólo se encarga de la capa de vista, [pero gracias a su amplio ecosistema, representa un framework completo, flexible e intercambiable](https://www.robinwieruch.de/essential-react-libraries-framework/). Además, cuenta con una API ligera, un ecosistema impresionante y una gran comunidad. Puedes leer sobre [razones por las que me mudé de Angular a React](https://www.robinwieruch.de/reasons-why-i-moved-from-angular-to-react/). Recomiendo que tengas claro por qué elegirías React sobre otro framework o biblioteca. Después de todo, el mundo está ansioso por ver que rumbo toma React en los años próximos.

### Ejercicios

* lee acerca de [por qué me cambié de Angular a React](https://www.robinwieruch.de/reasons-why-i-moved-from-angular-to-react/)
* lee acerca de [el flexible ecosistema de React](https://www.robinwieruch.de/essential-react-libraries-framework/)
* lee acerca de [cómo aprender a usar un framework](https://www.robinwieruch.de/how-to-learn-framework/)

## Requerimientos

Antes de seguir avanzando debes estar familiarizado con los fundamentos del desarrollo web. Se espera que sepas trabajar con HTML, CSS y JavaScript, además de lo que significa el término [API](https://www.robinwieruch.de/what-is-an-api-javascript/), estarás usando esto durante todo el libro.

Te animo a que te unas al canal [Slack](https://slack-the-road-to-learn-react.wieruch.com/) oficial del libro para obtener ayuda o ayudar a otros.

### Editor y Terminal

¿Y acerca del entorno de desarrollo? Necesitarás un editor de texto plano o IDE y la terminal (línea de comandos). Puedes leer [mi guía de configuración](https://www.robinwieruch.de/developer-setup/) para ayudarte a organizar tus herramientas, esta guía está pensada para usuarios de Mac, sin embargo todas las herramientas que necesitarás están disponibles para varios sistemas operativos.

Opcionalmente, puedes utilizar Git y GitHub por tu cuenta mientras estés realizando los ejercicios del libro, para mantener tus proyectos en repositorios de GitHub. Aquí dispones de una [pequeña guía](https://www.robinwieruch.de/git-essential-commands/) sobre cómo usar estas herramientas. Sin embargo, no es obligatorio su uso, podría resultar extenuante intentar aprenderlo todo al mismo tiempo.

### Node y npm

Por último pero no menos importante, necesitarás instalar [Node y npm](https://nodejs.org/es/). Ambos se utilizan para administrar las bibliotecas que necesitarás en El Camino para aprender React. Instalarás paquetes externos Node a través del Gestor de Paquetes Node (npm, por sus siglas en Inglés). Estos paquetes pueden constituir bibliotecas o frameworks completos.

Puedes verificar la versiones instaladas Node y npm, respectivamente dentro de la terminal. Si no obtienes ninguna salida en la terminal, así que debes verificar tu instalación Node y npm. Estas son mis versiones al momento de escribir este libro:

{title="Command Line",lang="text"}
~~~~~~~~
node --version
*v8.9.4
npm --version
*v5.6.0
~~~~~~~~

## Node y npm

A continuación un pequeño curso intensivo Node y npm. No es exhaustivo, pero obtendrás todas las herramientas necesarias. Si ya estás familiarizado con estas puedes omitir este capítulo.

El gestor **npm** permite instalar **paquetes externos** desde la terminal. Estos paquetes pueden ser un conjunto de funciones de utilidad, bibliotecas o frameworks enteros. Estos representan dependencias de tu aplicación, y puedes instalarlos en tu carpeta global de paquetes Node o bien en la carpeta local de tu proyecto.

Los paquetes globales Node son accesibles desde cualquier lugar de la terminal y sólo hay que instalarlos una vez en el directorio global. Puedes instalar un paquete a nivel global escribiendo en la terminal:

{title="Command Line",lang="text"}
~~~~~~~~
npm install -g <paquete>
~~~~~~~~

La  etiqueta `-g` indica a npm que debe instalar el paquete a nivel global. Los paquetes locales son utilizados en tu aplicación. Por ejemplo, React como una librería será un paquete local, y puede ser requerido en tu aplicación para su uso. Puedes instalarlo a través de la terminal escribiendo:

{title="Command Line",lang="text"}
~~~~~~~~
npm install <paquete>
~~~~~~~~

En el caso de React, sería:

{title="Command Line",lang="text"}
~~~~~~~~
npm install react
~~~~~~~~

El paquete instalado aparecerá automáticamente en una carpeta llamada *node_modules/* y será agregado al archivo *package.json* junto a las otras dependencias de tu aplicación.

Ahora, ¿cómo inicializar la carpeta *node_modules/* y el archivo *package.json* en tu proyecto? Para ello existe un comando que inicia un proyecto npm que incluye automáticamente un archivo *package.json*. Sólo cuando tu proyecto posee este archivo, puedes instalar nuevos paquetes locales vía npm.

{title="Command Line",lang="text"}
~~~~~~~~
npm init -y
~~~~~~~~

La etiqueta `-y` es un acceso directo para inicializar todos los valores predeterminados en el archivo *package.json* correspondiente. De no utilizarla, tienes que decidir cómo configurar el archivo.

Inmediatamente, con npm inicializado en tu carpeta de proyecto, estás listo para instalar nuevos paquetes vía `npm install <paquete>`.

Un dato extra sobre el archivo *package.json*. Este archivo permite que compartas tu proyecto con otros desarrolladores sin compartir todos los paquetes Node. Contiene todas las referencias de los paquetes Node utilizados en tu proyecto. Y estos paquetes son llamados dependencias. Cualquiera puede copiar tu proyecto sin las dependencias, pues, estas son referenciadas en el archivo *package.json*. Así, cuando alguien copia tu proyecto, puede instalar todos las dependencias usando `npm install` en la terminal.

Hay otro comando npm que quiero mencionar, para prevenir confusiones:

{title="Command Line",lang="text"}
~~~~~~~~
npm install --save-dev <paquete>
~~~~~~~~

La etiqueta `--save-dev` indica que el paquete Node es sólo usado en el entorno de desarrollo. No será usado en producción cuando cuelgues tu aplicación en un servidor. 

¿Qué tipo de paquete sería ese? Imagina que quieres probar tu aplicación con la ayuda de un paquete Node. Necesitas instalar este paquete a través npm, pero quieres excluirlo de tu entorno de producción.

Las pruebas sólo se realizan durante el proceso de desarrollo, mas no cuando tu aplicación está ya funcionando en producción. En ese nivel debería estar ya probada y funcionando para todos los usuarios.

Esto representa un caso de uso donde querrías usar la etiqueta `--save-dev`. 

Por ahora estos son todos los comandos que necesitas, pero en el camino encontrarás más de ellos.

### Ejercicios:

* configura un proyecto npm
  * crea una nueva carpeta con `mkdir <nombre_de_la_carpeta>`
  * navega hasta la carpeta con `cd <nombre_de_la_carpeta>`
  * ejecuta `npm init -y`
  * instala un paquete local, como React, con `npm install --save react`
  * échale un vistazo al archivo *package.json* y a la carpeta *node_modules/*
  * descubre como desinstalar el paquete Node *react*
* lee más sobre [npm](https://docs.npmjs.com/)

## Instalación

Existen varias maneras de comenzar una aplicación React.

La primera es utilizar una [Content Delivery Network](https://es.wikipedia.org/wiki/Red_de_entrega_de_contenidos), o Red de Entrega de Contenidos (CDN por sus siglas en Inglés).

Esto puede sonar complicado, pero no lo es. Muchas compañías tienen CDNs que almacenan públicamente archivos para sus usuarios. Archivos que pueden ser una librería como React, (una librería puede ser sólo un archivo JavaScript) se alojan en algún lugar y puedes luego requerirlos en tu aplicación.

¿Cómo usar una CDN en React? Puedes hacerlo insertando la etiqueta `<script>` en tu código HTML, con la URL de la CDN que desees utilizar. Para React necesitas dos archivos (librerías): *react* y *react-dom*.

{title="Code Playground",lang="javascript"}
~~~~~~~~
<script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
~~~~~~~~

¿Pero, por qué usar una CDN cuando tienes npm para instalar paquetes Node como React?

Cuando tu aplicación tiene un archivo *package.json* es posible instalar *react* y *react-dom* desde la terminal. El único requisito es que la carpeta esté inicializada como  un proyecto npm, lo puedes hacer utilizando `npm init -y` tal como se mostró anteriormente. Es posible instalar múltiples paquetes en una misma línea a la vez con npm.

{title="Command Line",lang="text"}
~~~~~~~~
npm install react react-dom
~~~~~~~~

El enfoque anterior se utiliza a menudo para añadir React a una aplicación existente administrada con npm.

Desafortunadamente, aquí no termina el asunto. También hay que lidiar con [Babel](http://babeljs.io/) para hacer tu aplicación compatible con JSX (la sintáxis de React) y JavaScript ES6. Babel transpila tu código para que los navegadores puedan interpretar ES6 y JSX. No todos los navegadores son capaces de interpretar la sintaxis.

Este enfoque es poco practico, se deben incluir muchas herramientas y configuraciones de forma manual. Puede resultar abrumador realizar manualmente toda la configuración de React.

Para facilitar esta tarea, Facebook desarrolló *create-react-app*, como una solución que ahorra tiempo y esfuerzo al usuario, encargándose esta de la mayor parte del proceso de configuración.

El siguiente capítulo muestra cómo iniciar con el desarrollo de tu aplicación con esta herramienta.

### Ejercicios:

* lee más acerca de [cómo instalar React](https://facebook.github.io/react/docs/installation.html)

## Cero Configuraciones

En El Camino para aprender React usarás [create-react-app](https://github.com/facebookincubator/create-react-app) para iniciar el desarrollo tu aplicación. Este kit lanzado por Facebook en 2016, permite rápidamente empezar a trabajar en tu aplicación sin preocuparte por configuraciones. La gente [lo recomienda a principiantes en un 96%](https://twitter.com/dan_abramov/status/806985854099062785). Cuando utilizas *create-react-app* las herramientas y configuración evolucionan en segundo plano, mientras que el foco se mantiene en la implementación de la aplicación.

Para empezar, deberás agregar el *create-react-app* a tus paquetes globales Node. A partir de ahora estará disponible en la terminal para inicializar nuevas aplicaciones React.

{title="Command Line",lang="text"}
~~~~~~~~
npm install -g create-react-app
~~~~~~~~

En la terminal puedes comprobar la versión de *create-react-app* para verificar que la instalación fue exitosa:

{title="Command Line",lang="text"}
~~~~~~~~
create-react-app --version
*v1.5.1
~~~~~~~~

Ahora, puedes comenzar con el desarrollo de tu primera aplicación React. La llamaremos *hackernews*, puedes escoger un nombre distinto. Iniciar tu aplicación tomará unos pocos segundos. Después de esto, simplemente navega hasta el nuevo directorio con tu terminal:

{title="Command Line",lang="text"}
~~~~~~~~
create-react-app hackernews
cd hackernews
~~~~~~~~

Ya puedes abrir la aplicación en tu editor de texto. La siguiente estructura de carpetas o variación de esta depende de la versión de *create-react-app* que tengas instalada, deberías poder ver algo cómo esto:

{title="Folder Structure",lang="text"}
~~~~~~~~
hackernews/
  README.md
  node_modules/
  package.json
  .gitignore
  public/
    favicon.ico
    index.html
    manifest.json
  src/
    App.css
    App.js
    App.test.js
    index.css
    index.js
    logo.svg
    registerServiceWorker.js
~~~~~~~~

A continuación, una pequeña descripción de cada una de las carpetas y archivos que encontrarás dentro del directorio recién creado. Está bien si no entiendes todo al principio.

* **README.md:** La extensión .md indica que el archivo está en formato "markdown". Markdown es un lenguaje de marcado ligero con sintaxis de texto plano. Muchos códigos fuente de proyectos incluyen un archivo *README.md* con instrucciones acerca del proyecto. Cuando estés subiendo tu proyecto a una plataforma cómo GitHub, eventualmente el archivo *README.md* mostrará promisoriamente su contenido cuando alguien acceda al repositorio. Como utilizaste *create-react-app*, tu archivo *README.md* debería ser igual al que se puede observar en el [repositorio GitHub de create-react-app](https://github.com/facebookincubator/create-react-app) oficial.

* **node_modules/:** Contiene todos los paquetes Node que han sido instalados vía npm. Como utilizaste *create-react-app* para inicializar tu aplicación, debes de poder ver un par de módulos Node ya instalados. Usualmente nunca tocarás esta carpeta, pues, con npm puedes instalar y desinstalar paquetes Node desde la terminal.

* **package.json:** Muestra una lista de las dependencias de paquetes Node y un conjunto de otras configuraciones referentes al proyecto.

* **.gitignore:** Especifíca los archivos y carpetas que no serán añadidos a tu repositorio de git. Archivos que sólo vivirán en el proyecto local.

* **public/:** Almacena todos los archivos raíz de desarrollo, como por ejemplo *public/index.html*, este índice es el que se muestra en la dirección localhost:3000 cuando estás desarrollando tu aplicación. *create-react-app* viene ya configurado para relacionar este archivo índice con todos los scripts en la carpeta *src/*.

* **build/:** Esta carpeta será creada cuando el proyecto se esté preparando para la etapa de producción y contendrá todos los archivos relacionados a esta etapa de desarrollo. Todo el código escrito en las carpetas *src/* y *public/* serán empaquetados en un par de archivos y posicionados en la carpeta *build/* cuando el proyecto se esté compilando.

* **manifest.json** y **registerServiceWorker.js:** Por el momento no te preocupes acerca de lo que estos archivos hacen, no los necesitaremos en este proyecto. 

No necesitas tocar los archivos que acabamos de mencionar. Por ahora todo lo que necesitas está localizado en la carpeta *src/* y la mayor atención recae sobre el archivo *src/App.js*, que utilizaremos para implementar componentes React.

Más adelante, podrás dividir los componentes React en múltiples archivos, con uno o más componentes dentro de cada archivo.

Adicionalmente, encontrarás un archivo *src/App.test.js* para pruebas y uno *src/index.js* como punto de entrada al mundo React. Explorarás ambos archivos en capítulos próximos. También existe un archivo *src/index.css* y un archivo *src/App.css* que sirven para darle estilos a tu aplicación y sus componentes. Estos ya incluyen algunos estilos por defecto.

La aplicación *create-react-app*  es un proyecto npm, puedes utilizar npm para instalar y desinstalar paquetes Node en tu proyecto, adicionalmente, incluye algunos scripts que puedes ejecutar desde la terminal:

{title="Command Line",lang="text"}
~~~~~~~~
# Ejecuta la aplicación en http://localhost:3000
npm start

# Ejecuta las pruebas
npm test

# Prepara la aplicación para la etapa de construcción
npm run build
~~~~~~~~

Estos scripts se encuentran definidos en el archivo *package.json*. Tu aplicación React se encuentra ya inicializadoa, y lo mejor está por venir, cuándo ejecutes tu aplicación en el navegador.

### Ejercicios:

* ejecuta en la terminal, el comando `npm start` y visita la aplicación en tu navegador (puedes cancelar la ejecución de este comando presionando Control + C)
* ejecuta el comando interactivo `npm test`
* ejecuta el comando `npm run build` y verifica que la carpeta *build/* sea añadida a tu proyecto (puedes removerla después; nota que la carpeta build puede ser usada más tarde para [colocar tu aplicación en línea](https://www.robinwieruch.de/deploy-applications-digital-ocean/))
* familiarízate con la estructura de carpetas
* familiarízate con el contenido de los archivos
* lee más sobre [los comandos npm y create-react-app](https://github.com/facebookincubator/create-react-app)

## Introducción a JSX

Ahora conocerás JSX, la sintaxis empleada por React. Como fue mencionado antes, *create-react-app* ya ha iniciado una aplicación estándar. Todos los archivos incluyen implementaciones predeterminadas. Es tiempo de sumergirnos en el código fuente.

El único archivo que manipularás por ahora es: *src/App.js*.

{title="src/App.js",lang=javascript}
~~~~~~~~
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
}

export default App;
~~~~~~~~

No te dejes intimidar por las instrucciones import/export y la declaración de clases. Estas características pertenecen a JavaScript ES6, volveremos a ellas más adelante.

Dentro del archivo *src/App.js* se encuentra un **React ES6 class component o componente de clase React ES6** con el nombre `App`. Esto es una declaración de componente.

Básicamente, después de haber declarado un componente puedes utilizarlo como elemento en cualquier parte de tu aplicación produciendo una **instancia** de tu **componente**, o mejor dicho: Instanciando el componente.

El **elemento** que es devuelto se especifica dentro del método `render()`. Los elementos son de lo que están hechos los componentes. Es útil que entiendas las diferencias entre los términos "componente", "instancia" y "elemento".

En un momento verás donde se instancia el componente `App` y cómo se renderiza en el navegador.

El componente `App` es sólo la declaración y por si solo no hará nada. Para utilizar dicho componente podrías instanciarlo en algún lugar de tu JSX con la etiqueta `<App />`.

El contenido dentro del bloque de código perteneciente al método `render()` parece ser HTML, pero en realidad es JSX, y te permite mezclar HTML y JavaScript. Es potente, pero confuso cuando estás acostumbrado a HTML simple. Por eso que un buen punto de partida es comenzar utilizando HTML básico en tu JSX. Las expresiones JavaScript las puedes utilizar insertándolas entre corchetes.

Primero, vamos a eliminar todo el contenido por defecto que es retornado por `render` y agregar nuestro propio HTML.

{title="src/App.js",lang=javascript}
~~~~~~~~
import React, { Component } from 'react';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <h2>Bienvenido al Camino para aprender React</h2>
      </div>
    );
  }
}

export default App;
~~~~~~~~

Ahora, el método `render()` sólo devuelve HTML sin JavaScript. Vamos a definir "Bienvenido al Camino para aprender React" como el valor de una variable, que puede ser utilizad en JSX usando corchetes.

{title="src/App.js",lang=javascript}
~~~~~~~~
import React, { Component } from 'react';
import './App.css';

class App extends Component {
  render() {
# leanpub-start-insert
    var helloWorld = 'Bienvenido al Camino para aprender React';
# leanpub-end-insert
    return (
      <div className="App">
# leanpub-start-insert
        <h2>{helloWorld}</h2>
# leanpub-end-insert
      </div>
    );
  }
}

export default App;
~~~~~~~~

Cuando inicies tu aplicación desde la terminal con `npm start` todo debería funcionar.

Además, probablemente notaste el atributo `className`. Este es similar al atributo estándar `class` en HTML. Debido a razones técnicas, JSX tuvo que reemplazar varios atributos internos de HTML. Puedes ver todos los [atributos HTML compatibles con JSX en la documentación de React](https://facebook.github.io/react/docs/dom-elements.html) aquí. Más adelante conoceremos nuevos atributos JSX.

### Ejercicios:

* define más variables y renderízalas en tu JSX
  * utiliza un complex object u objeto complejo en español, para representar a un usuario con nombre y apellido
  * renderiza las propiedades del usuario utilizando JSX
* lee más sobre [JSX](https://facebook.github.io/react/docs/introducing-jsx.html)
* lee más sobre [componentes, elementos e instancias en React](https://facebook.github.io/react/blog/2015/12/18/react-components-elements-and-instances.html)

## ES6 const y let

Probablemente notaste que declaramos la variable `helloWorld` con `var`. JavaScript ES6 incluye otras dos formas de declarar variables: `const` y `let`. En JavaScript ES6 rara vez utilizarás `var`.

Ahora, una explicación sobre `const` y `let`:

Una variable declarada con `const` no se puede volver a asignar o volver a declarar. No puede ser mutada (cambiada o modificada), es decir, la estructura de datos se vuelve inmutable. Una vez que se define la estructura de datos, no se puede cambiar.

{title="Code Playground",lang="javascript"}
~~~~~~~~
// no permitido
const helloWorld = 'Bienvenido al Camino para aprender React';
helloWorld = 'Bye Bye React';
~~~~~~~~

Por otra parte, una variable declarada con `let` puede mutar.

{title="Code Playground",lang="javascript"}
~~~~~~~~
// permitido
let helloWorld = 'Bienvenido al Camino para aprender React';
helloWorld = 'Hasta luego, React';
~~~~~~~~

Se puede utilizar `let` cuando el valor de una variable debe ser reasignado.

Sin embargo, hay que tener cuidado con `const`. Una variable declarada con `const` no se puede modificar. Pero cuando el valor de la variable es un arreglo o un objeto, sus valores pueden ser alterados. Es decir, los valores dentro del objeto o arreglo no son inmutables.

{title="Code Playground",lang="javascript"}
~~~~~~~~
// permitido
const helloWorld = {
  text: 'Bienvenido al Camino para aprender React'
};
helloWorld.text = 'Hasta luego, React';
~~~~~~~~

Pero ¿cuándo usar una u otra opción? Hay diferentes opiniones respecto a esto. Sugiero usar `const` siempre que sea posible, indicando así que se desea mantener la estructura de datos inmutable aunque los valores en objetos y arreglos se puedan modificar.

Si se quiere que el valor de la variable sea modificable, se puede utilizar `let`.

La inmutabilidad es ampliamente adoptada en React y su ecosistema. Es por eso que `const` debe ser la opción por defecto cuando se define una variable. Sin embargo, en objetos complejos, los valores internos pueden ser modificados. Ten cuidado con este comportamiento.

En tu aplicación utiliza `const` en vez de `var`.

{title="src/App.js",lang=javascript}
~~~~~~~~
import React, { Component } from 'react';
import './App.css';

class App extends Component {
  render() {
# leanpub-start-insert
    const helloWorld = 'Bienvenido al Camino para aprender React';
# leanpub-end-insert
    return (
      <div className="App">
        <h2>{helloWorld}</h2>
      </div>
    );
  }
}

export default App;
~~~~~~~~

### Ejercicios:

* lee más sobre [ES6 const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)
* lee más sobre [ES6 let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
* investiga más acerca de las estructuras de datos inmutables
  * ¿Por qué se utilizan en la programación en general?
  * ¿Por qué se utilizan en React?

## ReactDOM

Antes de volver a trabajar en el componente `App` es posible que quieras ver dónde es utilizado. Este se encuentra declarado dentro del archivo *src/index.js*.

{title="src/index.js",lang=javascript}
~~~~~~~~
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import './index.css';

ReactDOM.render(
  <App />,
  document.getElementById('root')
);
~~~~~~~~

Básicamente `ReactDOM.render()` selecciona un nodo DOM perteneciente al HTML de tu aplicación para reemplazarlo con JSX. Así es como puedes integrar fácilmente React a cualquier aplicación externa. No está prohibido utilizar `ReactDOM.render()` varias veces en una aplicación. Puedes utilizarlo en varios lugares para iniciar la sintaxis JSX simple, un componente React, múltiples componentes React o una aplicación completa.

`ReactDOM.render()` por defecto requiere dos argumentos:

El primero es JSX que será renderizado.

Y el segundo especifíca el lugar en el que la aplicación React será insertada dentro del código HTML de tu aplicación. En este ejemplo, se selecciona un elemento con `id='root'`. Puedes abrir el archivo *public/index.html* y encontrar allí dicho elemento.

En el ejercicio, `ReactDOM.render()` ya incluye el componente `App` como primer parámetro. Sin embargo, en el siguiente ejemplo utilizaremos código JSX simple y no la instancia de un componente. Todo esto para demostrar que al utilizar JSX simple no tienes es necesario instanciar un componente.

{title="Code Playground",lang=javascript}
~~~~~~~~
ReactDOM.render(
  <h1>Hola Mundo de React</h1>,
  document.getElementById('root')
);
~~~~~~~~

### Ejercicios:

* abre *public/index.html* para ver dónde se conectan las aplicaciones React con el HTML de tu aplicación
* lee más sobre cómo [renderizar elementos](https://facebook.github.io/react/docs/rendering-elements.html)

## Reemplazo de Módulos en Caliente

Hot Module Replacement o Reemplazo de Módulos en Caliente (HMR por sus siglas en Inglés) es una iteresante característica que puedes implementar en el archivo *src/index.js* para mejorar tu experiencia como desarrollador. Pero es opcional y puede que resulte abrumador al principio.

En *create-react-app* ya es una ventaja que el navegador recargue automáticamente la página tan pronto el código fuente cambia. Inténtalo, cambia la variable `helloWorld` en tu archivo *src/App.js*. El navegador debe recargar la página automáticamente. Sin embargo, esto puede hacerse de una mejor manera.

El Reemplazo de Módulo Caliente es una herramienta para actualizar tu aplicación dentro del navegador. Es decir, el navegador no actualiza la página entera. En *create-react-app* esta herramienta puede ser fácilmente activada, sólo necesitas agregar unas pocas líneas de código en tu *src/index.js* - tu punto de entrada de React -.

{title="src/index.js",lang=javascript}
~~~~~~~~
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import './index.css';

ReactDOM.render(
  <App />,
  document.getElementById('root')
);

# leanpub-start-insert
if (module.hot) {
  module.hot.accept();
}
# leanpub-end-insert
~~~~~~~~

Eso es todo. Ahora, intenta cambiar de nuevo la variable `hellowWorld` en tu archivo *src/App.js*. El navegador no recargará la página, sin embargo, notarás que la aplicación vuelve a cargar y muestra la salida correcta.

HMR ofrece múltiples ventajas:

Imagina que estás depurando tu código con declaraciones `console.log()`. Estas declaraciones permanecerán en la consola de desarrolladores, incluso si el código cambia, pues el navegador ya no actualiza la página. Lo que puede resultar conveniente al momento de depurar.

En una aplicación en crecimiento, una actualización de página retrasa la productividad. Tienes que esperar hasta que la página se cargue, y una recarga de página puede tardar varios segundos en una aplicación grande. HMR soluciona este inconveniente.

Sin embargo, el mayor beneficio que ofrece HMR es que puede mantener el estado de la aplicación. Imagina que tienes un diálogo en tu aplicación que consta de varios pasos y estás en el paso 3. Sin HMR el código fuente cambiaría y el navegador actualizaría la página, después tendrías que abrir el cuadro de diálogo nuevamente y navegar desde el paso 1 hasta el paso 3. 

Con HMR el diálogo permanece abierto en el paso 3. Es decir, mantiene el estado de la aplicación, aunque el código fuente cambie. La aplicación misma vuelve a cargar, más no la página.

### Ejercicios:

* cambia el código fuente de *src/App.js* varias veces para ver a HMR en acción
* mira los primeros 10 minutos de [Live React: Hot Reloading with Time Travel](https://www.youtube.com/watch?v=xsSnOQynTHs) por Dan Abramov

## JavaScript avanzado en JSX

Volvamos a trabajar en el componente `App`. Hasta ahora logramos renderizar algunas variables primitivas con JSX. Ahora, comenzarás a renderizar una lista de artículos. La lista en principio contendrá datos artificiales, pero más adelante recibirá los datos desde una API externa, lo que será mucho más emocionante.

Primero, define la lista de elementos.

{title="src/App.js",lang=javascript}
~~~~~~~~
import React, { Component } from 'react';
import './App.css';

# leanpub-start-insert
const list = [
  {
    title: 'React',
    url: 'https://facebook.github.io/react/',
    author: 'Jordan Walke',
    num_comments: 3,
    points: 4,
    objectID: 0,
  },
  {
    title: 'Redux',
    url: 'https://github.com/reactjs/redux',
    author: 'Dan Abramov, Andrew Clark',
    num_comments: 2,
    points: 5,
    objectID: 1,
  },
];
# leanpub-end-insert

class App extends Component {
  ...
}
~~~~~~~~

Los datos artificiales representan los datos que más adelante serán extraídos de la API. Cada elemento dentro de la lista (`const list`) tiene un título, una URL y un autor. Además incluye un identificador, puntos (que indican la popularidad de un artículo) y un recuento de comentarios.

Ahora, puedes utilizar el método `map` de JavaScript incorporándolo dentro del código JSX.

El método `map` permite iterar sobre la lista de elementos para poder mostrarlos. Recuerda que dentro del código JSX debes encerrar entre corchetes la expresión JavaScript. 

{title="src/App.js",lang=javascript}
~~~~~~~~
class App extends Component {
  render() {
    return (
      <div className="App">
# leanpub-start-insert
        {list.map(function(item) {
          return <div>{item.title}</div>;
        })}
# leanpub-end-insert
      </div>
    );
  }
}

export default App;
~~~~~~~~

Esto resulta muy al momento de trabajar con JSX. Es posible que antes hayas utilizado el método `map` para convertir una lista de elementos a otra lista de elementos, pero esta vez lo utilizas para convertir una lista de elementos a elementos HTML.

Por ahora sólo se muestra el valor de la propiedad `title` correspondiente a cada elemento de la lista. A continuación, vamos a mostrar otras propiedades del artículo.

{title="src/App.js",lang=javascript}
~~~~~~~~
class App extends Component {
  render() {
    return (
      <div className="App">
# leanpub-start-insert
        {list.map(function(item) {
          return (
            <div>
              <span>
                <a href={item.url}>{item.title}</a>
              </span>
              <span>{item.author}</span>
              <span>{item.num_comments}</span>
              <span>{item.points}</span>
            </div>
          );
        })}
# leanpub-end-insert
      </div>
    );
  }
}

export default App;
~~~~~~~~

Puedes ver como el método `map` está indentado dentro del código JSX. Cada propiedad de elemento se muestra en una etiqueta `<span>`. Además, la propiedad URL del elemento se utiliza en el atributo `href` de la etiqueta de anclaje.

React hará todo el trabajo por ti y mostrará cada elemento. Aunque es necesario agregar un helper o ayudante para que React alcance su máximo potencial y tenga un mejor rendimiento.

Debes asignar un atributo clave a cada elemento de lista. Así, React será capaz de identificar los elementos añadidos, cambiados y eliminados cuando la lista cambie. Los elementos artificiales dentro de la lista creada anteriormente ya incluyen un identificador por defecto (`objectID`).

{title="src/App.js",lang=javascript}
~~~~~~~~
{list.map(function(item) {
  return (
# leanpub-start-insert
    <div key={item.objectID}>
# leanpub-end-insert
      <span>
        <a href={item.url}>{item.title}</a>
      </span>
      <span>{item.author}</span>
      <span>{item.num_comments}</span>
      <span>{item.points}</span>
    </div>
  );
})}
~~~~~~~~

Asegúrate de que el atributo clave tiene un valor estable. No cometas el error de usar el índice asignado para el elemento dentro del arreglo. El índice del arreglo no es del todo estable. Por ejemplo, cuando el orden de la lista cambie, React tendrá dificultades para identificar los elementos correctamente, pues cada elemento dentro de la lista tendrá ahora un orden y un índice distinto.

{title="src/App.js",lang=javascript}
~~~~~~~~
// No hagas esto
{list.map(function(item, key) {
  return (
    <div key={key}>
      ...
    </div>
  );
})}
~~~~~~~~

Ahora puedes iniciar tu aplicación desde la terminal, abrir tu navegador y ver los dos elementos desplegados correspondientes a la lista que acabas de agregar al código de tu componente.

### Ejercicios:

* lee más sobre [llaves y listas de elementos en React](https://facebook.github.io/react/docs/lists-and-keys.html)
* repasar [funcionalidades estándar para Arreglos en JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
* utiliza más expresiones JavaScript por tu cuenta en JSX

## Funciones Flecha en ES6 (Arrow Functions)

JavaScript ES6 incluye funciones flecha. Las expresiones de función flecha resultan más cortas que expresiones de función tradicionales.

```js

function () { ... }


() => { ... }
```

{title="Code Playground",lang="javascript"}
~~~~~~~~
// expresión de función
function () { ... }

// expresión de función flecha
() => { ... }
~~~~~~~~

Claro, tienes que ser consciente de sus funcionalidades. Una de ellas es su comportamiento especial con el objeto `this`. Una expresión de función siempre define su propio objeto `this`. Las expresiones de función flecha aún tienen el objeto `this` en el contexto cerrado. No te confundas al usar `this` en una función flecha.

Con respecto a los paréntesis en las funciones flecha ES6, puedes quitarlos cuando la función sólo recibe un argumento, pero tienes que conservarlos cuando hay múltiples argumentos.

{title="Code Playground",lang="javascript"}
~~~~~~~~
// permitido
item => { ... }

// permitido
(item) => { ... }

// no permitido
item, key => { ... }

// permitido
(item, key) => { ... }
~~~~~~~~

Ahora, revisemos nuevamente el método `map`. Puedes declararlo de manera más concisa con una función flecha ES6.

{title="src/App.js",lang=javascript}
~~~~~~~~
# leanpub-start-insert
{list.map(item => {
# leanpub-end-insert
  return (
    <div key={item.objectID}>
      <span>
        <a href={item.url}>{item.title}</a>
      </span>
      <span>{item.author}</span>
      <span>{item.num_comments}</span>
      <span>{item.points}</span>
    </div>
  );
})}
~~~~~~~~

Además, es válido eliminar el *cuerpo del bloque* de la función flecha ES6. En un *cuerpo conciso* un `return` implícito se adjunta, de modo que se puede quitar la declaración `return`. Esto sucederá a menudo en el libro, así que asegúrate de entender la diferencia entre un cuerpo de bloque y un cuerpo conciso dentro de las funciones flecha ES6.

{title="src/App.js",lang=javascript}
~~~~~~~~
# leanpub-start-insert
{list.map(item =>
# leanpub-end-insert
  <div key={item.objectID}>
    <span>
      <a href={item.url}>{item.title}</a>
    </span>
    <span>{item.author}</span>
    <span>{item.num_comments}</span>
    <span>{item.points}</span>
  </div>
# leanpub-start-insert
)}
# leanpub-end-insert
~~~~~~~~

Ahora tu código JSX es más conciso y legible. Al declarar `map` de esta manera, se omite la sentencia "function", los corchetes y la declaración `return`.

### Ejercicios:

* lee más sobre [funciones flecha ES6](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

## Clases ES6 (ES6 Classes)

JavaScript ES6 incluye clases. Comunmente una clase se utiliza en lenguajes de programación orientados a objetos. JavaScript fue y sigue siendo muy flexible en sus paradigmas de programación. Funciona bien tanto con programación funcional como con programación orientada a objetos, lado a lado, para sus casos de uso particulares.

 React adopta el paradigma programación funcional, sin embargo, al crear estructuras de datos inmutables las clases se utilizan para declarar componentes y se les llama componentes de clase ES6. React aprovecha las mejores cualidades de ambos paradigmas de programación.

Considera la siguiente clase llamada `Developer` para examinar una clase de JavaScript ES6 sin pensar en componentes React.

{title="Code Playground",lang="javascript"}
~~~~~~~~
class Developer {
  constructor(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
  }

  getName() {
    return this.firstname + ' ' + this.lastname;
  }
}
~~~~~~~~

Una clase tiene un constructor que permite instanciarla. Este constructor puede tomar argumentos y asignarlos a la instancia de la clase. Además, una clase puede definir funciones, y dado que la función está asociada a una clase, se le llama método de clase.

En el ejemplo aterior, `class Developer` es sólo la declaración de la clase. Es posible crear varias instancias de una clase por medio de la invocación. Lo que resulta similar al componente de clase ES6, que tiene una declaración pero debe ser usado en otro lugar para instanciarlo.

Veámos cómo puedes instanciar una clase y utilizar sus métodos.

{title="Code Playground",lang="javascript"}
~~~~~~~~
const robin = new Developer('Robin', 'Wieruch');
console.log(robin.getName());
// output: Robin Wieruch
~~~~~~~~

React utiliza clases JavaScript ES6 en los componentes de clase ES6. Ya utilizaste un componente de clase ES6 anteriormente.


{title="src/App.js",lang=javascript}
~~~~~~~~
import React, { Component } from 'react';

...

class App extends Component {
  render() {
    ...
  }
}
~~~~~~~~

La clase `App` se extiende desde `Component`. Básicamente, se declara el componente `App`, pero este se extiende desde otro componente.

¿Qué significa extender? En la programación orientada a objetos se emplea el principio de herencia, que hace posible pasar funcionalidades de una clase a otra clase.

La clase `App` extiende la funcionalidad de la clase `Component`. Para ser más específicos, `App` hereda funcionalidades de la clase Component. Este componente se utiliza para extender una clase ES6 básica a una clase de componente ES6. Tiene todas las funcionalidades que un componente necesita tener. Y una de estas funcionalidades es un método que ya conoces, el método `render()` del que conocerás más funcionalidades más adelante.

La clase `Component` encapsula todas las funcionalidades de React que un desarrollador no necesita ver. Permite a los desarrolladores utilizar las clases como componentes en React.

Los métodos encapsulados dentro de la clase `Component` representan la interfaz pública. Uno de estos métodos debe ser sobreescrito, para los demás no es necesario. Aprenderás acerca de estos últimos cuando el libro llegue a los métodos del ciclo de vida en un capítulo próximo. El método `render()` tiene que ser sobreescrito, porque define la salida de React `Component`.

Ahora que ya conoces los conceptos básicos de las clases JavaScript ES6 y cómo se utilizan en React para extenderlas a componentes, aprenderás más sobre los métodos de Componente cuando el libro describa los Métodos de Ciclo de Vida de React.

### Ejercicios:

* lee más sobre [Clases en ES6](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes)


¡Ahora sabes cómo arrancar tu propia aplicación React! Repasemos brevemente los visto en los últimos capítulos:

* React
  * *create-react-app* arranca una aplicación React
  * JSX mezcla HTML y JavaScript para definir los componentes React
  * componentes, instancias y elementos son cosas diferentes
  * `ReactDOM.render()` es un punto de entrada para renderizar componentes React en el DOM
  * funciones JavaScript incorporadas pueden ser utilizadas en JSX
    * El método `map` puede utilizarse para renderizar una lista de elementos como elementos HTML
* ES6
  * Declaraciones de variables con `const` y `let` pueden ser utilizadas en casos de uso particulares
  * las funciones flecha pueden utilizarse para acortar las declaraciones de funciones
  * las clases se utilizan para definir componentes en React

Es recomendable que te detengas en este punto. Internaliza lo aprendido y aplícalo por cuenta propia. Puedes experimentar con el código fuente que has escrito hasta ahora.

El código fuente está disponible en el [repositorio oficial](https://github.com/rwieruch/hackernews-client/tree/0c5a701170dcc72fe68bdd594df3a6522f58fbb3).
