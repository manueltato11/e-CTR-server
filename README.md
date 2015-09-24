#### [e-CTR Server - WebSocket para Node.js](https://github.com/manueltato11/e-CTR-server) / [Demo](https://websocket-over-nodejs-manueltato11.c9.io/)

Servidor del Plugin e-CTR "Comunicación en Tiempo Real" desarrollado con WebSockets para Node.js el cual tiene las siguientes funcionalidades del lado del navegador:

1. Chat de texto usando canales <rooms>
2. Chat de texto si usar canales <rooms>
3. WebRTC Peer Connection usando canales <rooms>

Tres archivos node.js:

1. signaler.js - Inicializa la señalización del servidor Websocket bajo HTTP creando los canales de comunicación WebSocket. <rooms>.
2. ssl.js - Inicializa la señalización del servidor Websocket bajo el protocolo HTTPS previa instalación del certificado de seguridad SSL/TLS, crea los canales de comunicación de forma segura entre el cliente y servidor. <channels>, es decir <rooms>.
3. simple.js - Inicializa la señalización del servidor Websocket bajo el protocolo HTTP sin canales de comunicación, es decir NO-room.

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