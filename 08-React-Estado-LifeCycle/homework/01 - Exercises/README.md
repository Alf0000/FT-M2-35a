# HW 02 - React-Estado-Life Cycle | Ejercicios

## Duración estimada 🕒

x minutos

---

## Consigna de la homework

En esta homework, aprenderemos a crear componentes de estado, teniendo en cuenta también su ciclo de vida.

* Para el componente **Bienvenido.jsx** generaremos un estado en el nombre del alumno utilizando los hooks useState y useEffect.
* Para el componente **Botones.jsx** también generaremos un estado utilizando el this.state y los ciclos de vida componentDidMount, componentDidUpdate y componentWillUnmount.

---

## Pasos básicos para realizar la homework

🔹 Para poder ejecutar los `test` de esta homework, es necesario que abramos la terminal ubicados dentro de la carpeta `01 - Exercises`.

* Cuando te encuentres en esta carpeta, debes ejecutar el comando

```bash
npm install
```

* Listo!! Ya puedes correr los test:

```bash
npm test
```

Los dos primeros test pasarán sin que hagas nada, simplemente están para que te ayuden a verificar que estás realizando correctamente los pasos y que no tienes errores.

🔹 Para poder correr la aplicación de forma local, sólo debes ejecutar el comando

```bash
npm start
```

* Ingresando a <http://localhost:3000> desde el navegador, podremos ir viendo en tiempo real el resultado de nuestro trabajo.

---

## Conociendo la estructura

🔹 Dentro de la carpeta `01 - Exercises`, vas a encontrar la siguiente estructura:

* Una carpeta llamada **public**
* Una carpeta llamada `src` (Es la carpeta en donde trabajaremos)
* Una carpeta llamada **tests**
* Un archivo **package.json**
* Y el archivo `README.md` que ahora mismo estás leyendo. 🧐

Además:

🔹 Dentro de la carpeta `src` encontrarás el esqueleto del proyecto React, estructurado de la siguiente manera:

* Una carpeta llamada **assets**
* Una carpeta llamada `components`
* Un archivo llamado **App.js**
* Un archivo **index.css**
* Un archivo **index.js**

🔹 Para estos ejercicios, trabajaremos sólo dentro la carpeta `components`. Dentro de esta carpeta encontrarás:

* Una carpeta llamada **Bienvenido**, la cual a su vez contiene:
  * El componente `Bienvenido.jsx`
  * La hoja de estilos **Bienvenido.module.css**
* Una carpeta llamada **Botones**, la cual a su vez contiene:
  * El componente `Botones.jsx`

---

## 👩‍💻 Ejercicio 1

### Creando un estado a nuestro componente funcional

🔹 Abre el archivo `Bienvenido.jsx`, dentro de él encontrarás:

* El import de la librería **React**, los archivos en formato de imagen y el archivo `Bienvenido.module.css`.

* Las constantes `studentName` y `alerts`.

* La función Bienvenido que renderiza:

1. Un div.
2. Dentro de este div, se renderiza:
   * Una etiqueta h1
   * Una etiqueta h3
   * Una etiqueta ul (lista desordenada)
   * El componente `Botones`

🔹 El componente funcional `Bienvenido.jsx`, es actualmente un componente sin estado. 

🔹 Lo que hay que hacer:

1. Mueve nuestra constante **studentName** dentro del componente **Bienvenido**.

2. Cambia nuestra constante studentName por una constante de estado, y asígnale el hook React.useState que inicialice en un string vacío. Por ejemplo: 

```bash
const [example, setExample] = React.useState('');
```

> **Nota**: Para que corran los test, los hooks deben ser utilizados de esta manera: **React.useState()**. No deben utilizarse como **useState()**. 💡

3. Renderiza una etiqueta label debajo de la etiqueta h1.

4. Renderiza una etiqueta input debajo de la etiqueta label y encima de la etiqueta h3.

5. A la etiqueta input asígnale los atributos `value` y `onChange`.

6. Al atributo **value** de la etiqueta input asígnale la constante `studentName`.

7. Crea una función llamada `handleInputChange`, que reciba un **evento** como parámetro.

8. Dentro de la función `handleInputChange`, setea el estado studentName, capturando el valor del input.

9. Al atributo **onChange** asígnale la función `handleInputChange`.

🔹 Resultado esperado:




---

## 👩‍💻 Ejercicio 2

### Continuamos con la carpeta Botones

Ya sabemos cómo funciona y se conectan los archivos module.css a nuestros componentes, ahora vamos a estilar desde cero en nuestro componente Botones, pero esta vez será aplicando `Styled Components`, para ello debes seguir los siguientes pasos:

1. En el componente `Botones.jsx`, importa `styled` desde "styled-components"`
2. Encontrarás una constante llamada `DivButtons`, la cual debe contener mínimamente los siguientes estilos para el div:
    * `display: flex`
    * `flex-direction: row`

 Por ejemplo:

```jsx
const DivExample = styled.div`
    width: 100vw; 
    height: 100 hw`
```

3. Encontrarás una constante llamada `Buttons`, la cual debe contener mínimamente los estilos para los botones:
    * `border-radius: 5px`
    * `margin: 10px`
    * `padding: 5px`

4. Cambia las etiquetas por las constantes mencionadas anteriormente. Por ejemplo:

```html
<div></div> 

//cambiaría por: 

<DivExample></DivExample>
```

🔹 Resultado esperado:

<p align="center"><img src="./img/01.png" height="300px"></p>

> **Nota**: Para los estilos puedes guiarte del ejercicio anterior. 💡

**...Estamos llegando a la última parte de la homework** ⭐

---

## 👩‍💻 Ejercicio Extra

🔹 Aplica estilo al h1 utilizando `inline styling`.

El componente debe verse en el navegador similar a esta imagen:

<p align="center"><img src="./img/exercise.gif" height="300px"></p>

---

## Recordemos que...

* Puedes utilizar cualquiera de los métodos enseñados en clase y practicados en este ejercicio para aplicar estilos en React.
* Si vas a utilizar `styled components`, el nombre de las variables `const` deben comenzar con mayúscula.
* Para utilizar estilos en línea o `inline styling`, debes usar el atributo `style`, estableciendo su valor **como un objeto de javascript**.
* Si utilizas `CSS Modules`, el alcance de tus estilos será local para cada componente y evitarás conflictos como pisar estilos en tu proyecto.
* Aplicar estilos es como pintar un cuadro, no hay límites en la imaginación y creatividad, sin olvidarnos de dar a los usuarios la mejor experiencia. 😃

---

## Recursos adicionales

* Documentación **"Styled Components"** <https://styled-components.com/docs/basics>
* Documentación **"CSS"** <https://www.w3schools.com/css/default.asp>

---

Listo!! Ahora estás preparado para estilar tu app!! 👨‍🎨👩‍🎨✨🚀

Dirígete a la carpeta 📂 [**"02 - Integration"**](../02%20-%20Integration/README.md) y diviértete estilando la app de Rick & Morty 🤩
