# App con websockets - SSR -> HTTP + WebSockets

## CLIENT - FRONTEND

- Código JS (script) que se ejecuta en el navegador (conectado al servidor a través de WebSockets):
  - public/js/app.js
  - public/js/socket-client.js
  - public/js/index.js
  - public/js/\*.js

- Vistas a renderizar (donde pueden o no tener código JS - los <script>):
  - src/views/layouts/main.hbs - {{{body}}}
  - src/views/\*

## SERVER - BACKEND

El resto de los archivos, que se ejecutan en el servidor.
