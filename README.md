# vue-3-CRUD

#### Descargando dependencias de Nodejs📚
```
npm install
```

#### Correr la aplicación en un entorno local
```
npm run serve
```

#### Construir la app🛠
```
npm run build
```
#### Modifica la configuración
See [Configuration Reference](https://cli.vuejs.org/config/).

#### Dependencia de ESlint para darle estilo Airbnb al código🤵
`npm install eslint --save-dev`

Comando para configurar eslint al estilo Airbnb
`npm init @eslint/config`

Nuestras reglas en el archivo `.eslintrc.js`
```
{
    "env": {
        "browser": true,
        "commonjs": true,
        "es2021": true
    },
    "extends": [
        "airbnb-base"
    ],
    "parserOptions": {
        "ecmaVersion": "latest"
    },
    "rules": {
        "indent": ["error", 4],
        "linebreak-style": ["error", "unix"],
        "quotes": ["error", "double"],
        "semi": ["error", "always"]
    }
}
```
Automatiza la ejecución de lint en el `package.json`
```
"scripts": {
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build --dest build",
    "lint": "vue-cli-service lint",
    "linter": "node ./node_modules/eslint/bin/eslint.js .",
    "linter-fix": "node ./node_modules/eslint/bin/eslint.js . --fix"
  }
```
Para ejecutarlo `npm run linter`, para corregir los detalles `npm run linter-fix`
#### Axios nos ayudara a hacer peticiones HTTP
`npm install axios`
#### Instalando CORS para consultar el API
```
npm install cors --save
```

Corre el proyecto anterior, la API de express que conectamos a una base de datos de postgresql [API: Express + DB](https://github.com/UlisesOrnelasR/PrismaDB)

```
node server.js
```

#### Corriendo el cliente

```
npm run serve
```
La url del cliente estará en `http://localhost:8081/`

La app estará lista para conectarse con la API que hicimos anteriormente.✅

#### Se acaba de crear una App CRUD con las funcionalidades
- Visualizacion de explorers y Mission Commanders
![a1](https://user-images.githubusercontent.com/99143567/170149086-1b98e29e-d2e2-43b4-838c-ec4770902fb9.png)
![a2](https://user-images.githubusercontent.com/99143567/170149110-84f60480-2076-447d-a405-12a33ae6fb82.png)
- Modificación de algún campo 
- Posibilidad de eliminar algun explorer o mission commander
![a3](https://user-images.githubusercontent.com/99143567/170149153-da62033f-98ae-4199-901d-a0502a899acd.png)
![a4](https://user-images.githubusercontent.com/99143567/170149167-6d8acfd8-dc66-4b7a-9524-9d8c157c764e.png)
- Agregar un nuevo explorer o mc
![a5](https://user-images.githubusercontent.com/99143567/170149186-3c3bf0d1-b52b-47b4-bc0d-0f07aab76b78.png)
![a6](https://user-images.githubusercontent.com/99143567/170149200-dd116bda-7ced-49bd-83ef-0da993d8fffa.png)

#### Comming soon
- Test
- Mejorar el front

