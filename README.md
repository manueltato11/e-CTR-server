#### [e-CTR Server - WebSocket over Node.js](https://github.com/manueltato11/e-CTR-server) / [Demo](https://websocket-over-nodejs-manueltato11.c9.io/)

Server del Plugin e-CTR "Comunicación en Tiempo Real" desarrollado con WebSockets Over Node.js el cual tiene las siguientes demostraciones del lado del navegador:

1. Chat de texto usando habitaciones <rooms>
2. Chat de texto si usar habitaciones <rooms>
3. WebRTC Peer Connection usando habitaciones <rooms>

Tres archivos node.js:

1. signaler.js - HTTP basado en Websocket para la señalización de servidor junto a la creación de canales WebSocket <channels>, es decir <rooms>.
2. ssl.js - HTTPs i.e. SSL basado en Websocket para la señalizacion más segura de la conexión, junto a la creacion de canales Websocket <channels>, es decir <rooms>.
3. simple.js - HTTP basado en Websocket para la señalización sin canales ni habitaciones, es decir NO-room.

=

#### Dependencias

1. WebSocket - Para la señalización Websocket sobre la conexión en Node.js.

```
npm install websocket
```

2. Node-Static - para servir recursos estáticos, es decir archivos HTML/CSS/JS.

```
npm install node-static
```

=

#### Ejecutar el servidor

Ejecutar el archivo Nodejs `signaler.js`:

```
node e-CTR-server/signaler.js
```

Se utiliza el puerto "8080", por ejemplo: `http://localhost:8080/`

=

#### Verificar si el servidor está corriendo

```
// Reemplazar "localhost" con el nombre del dominio!
http://localhost:8080/
```

=

#### Al implementar la aplicación

Primero que todo; cambiar **subdominio** en el archivo `package.json`:

```
{
  "name": "just-a-name",
  "subdomain": "must-be-unique",
  "scripts": {
    "start": "signaler.js"
  },
  main: "signaler.js",
  "version": "0.0.1",
  "engines": {
    "node": "0.10.x"
  },
  "dependencies": {
    "websocket": "1.0.x"
  }
}
```

Y listo!

Ahora, el servidor se escucha de la siguiente manera:

```javascript
// Se debe de incluir el puerto "8080"!
var websocket = new WebSocket('ws://subdomain.jit.su:8080');

// o
var websocket = new WebSocket('ws://subdomain.nodejitsu.com:8080');

// o SSL
var websocket = new WebSocket('wss://subdomain.nodejitsu.com:443');
```

=

https://github.com/muaz-khan/WebRTC-Experiment/blob/master/Signaling.md

=

#### Licencia

[WebSocket over Node.js](https://github.com/muaz-khan/WebRTC-Experiment/blob/master/websocket-over-nodejs) esta publicado bajo la [Licencia MIT](https://webrtc-experiment.appspot.com/licence/)  Copyright (c) [Muaz Khan](https://plus.google.com/+MuazKhan).