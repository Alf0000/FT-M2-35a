# HW 13 - React-Hooks | Ejercicios

## Duración estimada 🕒

x minutos

---

## Intro

En esta homework trabajarás en una serie de ejercicios específcos para crear una página de Contact Us. En cada ejercicio practicarás un **Hook** de React o de Redux.

---

## Consigna de la homework

Lee atentamente este **README** y realiza cada uno de los ejercicios.

---

## Pasos básicos para realizar la homework

🔹 Para poder ejecutar los `test` de esta homework, es necesario que abramos la terminal ubicados dentro de la carpeta `01 - Exercises`.

-  Cuando te encuentres en esta carpeta, debes ejecutar el comando

```bash
npm install
```

-  Listo!! Ya puedes correr los test:

```bash
npm test
```

Si deseas correr por test, puedes utilizar:

```bash
npm run test:01
```

🔹 Para poder correr la aplicación de forma local, sólo debes ejecutar el comando

```bash
npm start
```

-  Ingresando a <http://localhost:3000> desde el navegador, podremos ir viendo en tiempo real el resultado de nuestro trabajo.

---

## Conociendo la estructura

🔹 Dentro de la carpeta `01 - Exercises`, vas a encontrar la siguiente estructura:

-  Una carpeta llamada **_mocks_**.
-  Una carpeta llamada **_public_**.
-  Una carpeta llamada **_tests_**
-  Un archivo **package.json**
-  Una carpeta llamada `src` (es la carpeta en donde trabajaremos)
-  Y el archivo `README.md` que ahora mismo estás leyendo. 🧐

Además:

🔹 Dentro de la carpeta `src` encontrarás el esqueleto del proyecto React, estructurado de la siguiente manera:

-  Una carpeta llamada `assets`
-  Una carpeta llamada `components`
   -  Una carpeta llamada `ContactUs`
   -  Una carpeta llamada `CopyData`
   -  Una carpeta llamada `InfoEnviada`
-  Una carpeta llamada `redux`
   -  Una carpeta llamada `actions`
   -  Una carpeta llamada `reducer`
   -  Una carpeta llamada `store`
-  Un archivo llamado `Home.js`
-  Un archivo llamado `home.css`
-  Un archivo llamado `index.js`

Estarás trabajando con algunos componentes y con las herramientas de Redux.

---

## 👩‍💻 Ejercicio 1

En este ejercicio crearemos un formulario para enviar un mail a la empresa.

### **USE STATE**

🔹 Dirígete al archivo **components/ContactUs/ContactUs.jsx**.

🔹 Lo que hay que hacer:

1. Importa `React` para luego poder usar su método `useState`.

2. Crea un estado local llamado "_form_" para guardar la información de todos los inputs: **nombre**, **email**, **asunto** y **mensaje**.

```js
const [state, setState] = React.useState({
   nombre: '',
   email: '',
   asunto: '',
   mensaje: '',
});
```

3. Crea una función "_handleInput_" para manejar estos inputs.

---

## 👩‍💻 Ejercicio 2

En este ejercicio crearás todo el flujo para enviar la información del formulario al estado global.

### **USE DISPATCH**

##### **ACTIONS**

🔹 Dirígete al archivo **redux/actions/actions.js**.

🔹 Lo que hay que hacer:

1. Crea y exporta una _**actionCreator**_ llamada "**enviarForm**".

2. Debe recibir por parámetro una varibla "_formulario_".

3. Debe retornar una acción con tipo "**FORM_DATA**", y en el payload el formulario recibido por parámetro.

</br>

##### **REDUCER**

🔹 Dirígete al archivo **redux/reducer/reducer.js**.

🔹 Lo que hay que hacer:

1. Crea un control de flujo tipo **switch** dentro de la función **rootReducer**. Este recibirá por parámetro la variable **type**.

2. Crea un caso llamado "**FORM_DATA**". Este caso debe retornar el estado global, pero guardando el payload recibido en la propiedad "_formulario_".

3. Crea un caso **default** en el que se retorne el estado global completo.

 </br>

##### **DISPATCH**

🔹 Dirígete al archivo **components/ContactUs/ContactUs.jsx**.

🔹 Lo que hay que hacer:

1. Importa el hook `useDispatch`. Instancialo dentro del componente de esta manera:

```javascript
const dispatch = useDispatch();
```

2. Importa la _actionCreator_ que declaraste hace unos momentos atrás.

3. Crea una función llamada "_handleSubmit_". Esta función debe:

   -  despachar esta _actionCreator_, la cual recibe por parámetro el estado local "**form**".
   -  limpiar el formulario una vez despachada la informacion

4. Pásale esta función a la etiqueta `button` de este componente, dentro de un evento "**onClick**.

---

## 👩‍💻 Ejercicio 3

En este ejercicio traerás la infromación del estado global a un componente.

### **USE SELECTOR**

##### **SELECTOR**

🔹 Dirígete al archivo **components/InfoEnviada/InfoEnviada.jsx**.

🔹 Lo que hay que hacer:

1. Importa el hook `useSelector`. Una vez importado, inicialízalo dentro del componente trayendo tu estado global "**formulario**" de la siguiente manera:

```javascript
const { formulario } = useSelector((state) => {
   return state;
});
```

 </br>

##### **GUARDAR LA INFORMACIÓN**

🔹 Dirígete al archivo **components/InfoEnviada/InfoEnviada.jsx**.

🔹 Lo que hay que hacer:

1. Importa el hook `React.useState`, y crea un estado local llamado "**informacion**". Este estado debe ser un objeto con las propiedades: **nombre**, **email**, **asunto** y **mensaje**.

---

## 👩‍💻 Ejercicio 4

En este ejercicio mostrarás la información de tu estado global en la pantalla.

En este ejercicio

### **USE EFFECT**

##### **EFFECT**

🔹 Dirígete al archivo **components/InfoEnviada/InfoEnviada.jsx**.

🔹 Lo que hay que hacer:

1. Importa el hook `useEffect`, y decláralo dentro del componente (debajo del selector). Tendrás que declararlo de la manera:

```javascript
React.useEffect();
```

2. Dentro de este hook debes crear una función _callback_ que tiene que settear en tu estado local "**informacion**" el formulario que estás trayéndote desde el reducer (gracias al selector).

3. Crea, en este hook, un arreglo de dependencia que tenga incluído dentro el formulario recibido.

</br>

##### **RENDER DE LA INFORMACIÓN**

🔹 Dirígete al archivo **components/InfoEnviada/InfoEnviada.jsx**.

🔹 Lo que hay que hacer:

1. Renderiza en este componente la información que tienes guardada en tu estado local "**informacion**".

2. Dale estilos a cada dato.

---

## 👩‍💻 Ejercicio 5

En este ejercicio crearás una funcionalidad de _**Copiado al Portapapeles**_ del número telefónico de la empresa.

### ...estamos llegando a la última parte de la homework ⭐

### **USE REF**

🔹 Dirígete al archivo **components/CopyData/CopyData.jsx**.

🔹 Lo que hay que hacer:

1. Importa los hooks `useState` y `useRef`.

2. Crea un estado local llamado "**number**" que sea un string y tenga un número cualquiera con la estructura:

   XXXX - XXX XXXX

3. Crea una constante llamada "**numberRef**" que será igual al hook `useRef()` ejecutado.

4. Dentro del componente crea:

   -  Una etiqueta `button` con el texto "**_Copy_**"
   -  Una etiqueta `div`. Esta debe tener una propiedad `ref` igual a la referencia que creamos anteriormente. Además, dentro de esta etiqueta debes escribir:

          TELÉFONO: {number}

> **NOTA:** es muy importante que el texto que escribas dentro de la etiqueta "div" sea literalmente el anterior.

5. Crea una función llamada **handleCopy**. En el cuerpo de la función tienes que copiar y pegar el siguiente código:

```javascript
let copyText = numberRef.current.lastChild.data;
const textArea = document.createElement('textarea');
textArea.textContent = copyText;
document.body.append(textArea);
textArea.select();
document.execCommand('copy');
textArea.remove();
```

> **NOTA:** este código sirve para que el número de télefono se copie en el portapapeles del usuario. No es importante que entiendas qué está sucediendo en ese código, pero te invitamos a que lo analices.

6. Pásale la función **handleCopy** a la etiqueta `button` que creaste anteriormente, mediante un evento **onClick**.

---

## 👩‍💻 Extra

##### **VALIDACIONES**

Te desafiamos a que crees las validaciones necesarias para cada uno de los inputs del formulario.

---

## Recordemos que...

-  El **useState** nos permite guardar información de manera local en un componente.
-  El **useDispatch** nos permite enviar acciones a nuestro reducer.
-  El **useSelector** nos permite traer información de nuestro estado global a un componente.
-  El **useEffect** nos permite manejar el ciclo de vida de un componente.
-  El **useRef** nos permite tener una referencia directa de un elemento del DOM en nuestro código.

---

## Recursos adicionales

-  Documentación [**HOOKS EN REACT**](https://reactjs.org/docs/hooks-intro.html)

---

¡Listo! Repasaste algunos de los hooks más importantes que nos brindan las librerías de React y Redux.

✨🚀 Dirígete a la carpeta 📂 [**"02 - Integration"**](../02%20-%20Integration/README.md) y continúa desarrollando la app de Rick & Morty 🤩 ---
