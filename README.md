# RedSystem - Final Project 4GeeksAcademy

### Descripción
<p>Proyecto basado en una empresa ficticia de telecomunicaciones la cual se encargá de administrar sus contratos de trabajo, donde cada contrato tiene además órdenes específicas o actividades por hacer.</p>

### Características
- Sistema de usuarios.
- CRUD completo
- Encriptación con JWT
- Frontend creado con React
- Validación del RUN/RUT
- Responsive
- Manejo de tokens
- Formulario de contacto

### Instrucciones para ejecutar

Este repositorio debe ejecutarse en conjunto con el repositorio `4GA-RedSystem-Full-Stack-Final-Project-Frontend`
- Ejecutar el proyecto desde gitpod.
- Ejecutar los comandos
```
pipenv shell
pipenv install flask-jwt-extended
```
- Borrar la BD: Ejecutar el siguiente comando en la terminal
```
psql
```
- Entrará en un terminal diferente, que solo recibe peticiones SQL. Ejecutar los siguientes comandos, uno a la vez
```
UPDATE pg_database SET datallowconn = 'false' WHERE datname = 'example';
ALTER DATABASE example CONNECTION LIMIT 1;
SELECT pg_terminate_backend(pid) FROM pg_stat_activity WHERE datname = 'example';
DROP DATABASE example;
EXIT
```
- Luego eliminar TODA la carpeta migrations
- Luego hacer lo que dice el archivo gitpod.yml
```
psql -U gitpod -c 'CREATE DATABASE example;';
psql -U gitpod -c 'CREATE EXTENSION unaccent;' -d example;
pipenv run init;
pipenv run migrate;
pipenv run upgrade;
```
- Ejecutar el proyecto
```
pipenv run start
```
- Colocar los puertos como públicos

----------------------------------------------------------------------------------------------------------------------------

- Recomendaciones:

* Instalar la extensión de VisualStudio "database client"
* Crear la conexión con database client
* Crear un archivo REQUEST.http en la raíz del proyecto y cambiar el @host de ese archivo (ojo con el puerto en la URL)

----------------------------------------------------------------------------------------------------------------------------

# WebApp boilerplate with React JS
[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io#https://github.com/4GeeksAcademy/react-flask-hello.git)

<p align="center">
<a href="https://www.loom.com/share/f37c6838b3f1496c95111e515e83dd9b"><img src="https://github.com/4GeeksAcademy/flask-rest-hello/blob/main/docs/assets/how-to.png?raw=true?raw=true" /></a>
</p>

### Styles
You can update the `styles/index.scss` or create new `.scss` files inside `styles/` and import them into your current scss or js files depending on your needs.

### Components
Add more files into your `./src/js/components` or styles folder as you need them and import them into your current files as needed.

💡Note: There is an example using the Context API inside `views/demo.js`;

### Views (Components)
Add more files into your `./src/js/views` and import them in `./src/js/layout.jsx`.

### Context
This boilerplate comes with a centralized general Context API. The file `./src/js/store/flux.js` has a base structure for the store, we encourage you to change it and adapt it to your needs.

React Context [docs](https://reactjs.org/docs/context.html)
BreathCode Lesson [view](https://content.breatheco.de/lesson/react-hooks-explained)

The `Provider` is already set. You can consume from any component using the useContext hook to get the `store` and `actions` from the Context. Check `/views/demo.js` to see a demo.

```jsx
import { Context } from "../store/appContext";
const MyComponentSuper = () => {
  //here you use useContext to get store and actions
  const { store, actions } = useContext(Context);
  return <div>{/* you can use your actions or store inside the html */}</div>
}
```

### Back-End Manual Installation:

It is recomended to install the backend first, make sure you have Python 3.8, Pipenv and a database engine (Posgress recomended)

1. Install the python packages: `$ pipenv install`
2. Create a .env file based on the .env.example: `$ cp .env.example .env`
3. Install your database engine and create your database, depending on your database you have to create a DATABASE_URL variable with one of the possible values, make sure yo replace the valudes with your database information:

| Engine	| DATABASE_URL 						|
| ------------- | ----------------------------------------------------- |
| SQLite	| sqlite:////test.db	 				|
| MySQL		| mysql://username:password@localhost:port/example	|
| Postgress	| postgres://username:password@localhost:5432/example 	|

4. Migrate the migrations: `$ pipenv run migrate` (skip if you have not made changes to the models on the `./src/api/models.py`)
5. Run the migrations: `$ pipenv run upgrade`
6. Run the application: `$ pipenv run start


### Front-End Manual Installation:

- Make sure you are using node version 14+ and that you have already successfully installed and runned the backend.

1. Install the packages: `$ npm install`
2. Start coding! start the webpack dev server `$ npm run start`

## Publish your website!

This boilerplate it's 100% integrated with Herkou, just by pushing your changes to the heroku repository it will deploy: `$ git push heroku main`
