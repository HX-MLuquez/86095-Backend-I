# Base de datos No SQL - MongoDB RedSocial

MongoDB es una base de datos NoSQL orientada a documentos que almacena datos en formato BSON (Binary JSON). Es altamente escalable, flexible y fácil de usar, lo que la convierte en una opción popular para aplicaciones modernas. En esta sección, se describen los pasos para instalar MongoDB, realizar operaciones CRUD y desplegar una aplicación Node.js utilizando MongoDB.

### Entidades

- usuarios
  - id
  - nombre_completo
  - email
  - contraseña
  - fecha_de_nacimiento
  - amigos (array de ids de usuarios)
- publicaciones
  - id
  - descripcion
  - fecha_de_publicacion
  - id_usuario
- comentarios
  - id
  - mensaje
  - id_usuario
  - id_publicacion
- fotos
  - id
  - url
  - id_publicacion
  - fecha_de_subida

**Una publicación puede tener varias fotos, pero cada foto pertenece a una sola publicación. Una publicación pertenece a un usuario y un usuario puede tener varias publicaciones. Una publicación puede tener varios comentarios, pero cada comentario pertenece a una sola publicación y a un solo usuario. Y un usuario puede tener varios amigos.**

1. Crear una base de datos `red-social`:

```js
use red-social;
```

2. Crear las colecciones `usuarios`, `publicaciones`, `comentarios` y `fotos`:

```js
db.createCollection("usuarios");
db.createCollection("publicaciones");
db.createCollection("comentarios");
db.createCollection("fotos");
```

3. Crear 1 usuario:

```js
db.usuarios.insertOne({
  nombre_completo: "Juan Pérez",
  email: "juan.perez@example.com",
  contraseña: "password123",
  fecha_de_nacimiento: new Date("1990-01-01"),
  amigos: [],
});
```

* Consultar el usuario creado:

```js
db.usuarios.find();
```

4. Crear 3 usuarios:

```js
db.usuarios.insertMany([
  {
    nombre_completo: "Ana García",
    email: "ana.garcia@example.com",
    contraseña: "password123",
    fecha_de_nacimiento: new Date("1992-05-15"),
    amigos: [],
  },
  {
    nombre_completo: "Luis Martínez",
    email: "luis.martinez@example.com",
    contraseña: "password123",
    fecha_de_nacimiento: new Date("1988-09-20"),
    amigos: [],
  },
  {
    nombre_completo: "María López",
    email: "maria.lopez@example.com",
    contraseña: "password123",
    fecha_de_nacimiento: new Date("1995-12-10"),
    amigos: [],
  },
]);
```
