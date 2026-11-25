
# Neta sabes?

**Neta sabes?** es un juego de mesa digital de trivia y estrategia por turnos para 2 a 4 jugadores, que pueden ser personas o bots. Los participantes avanzan por un tablero con ayuda de un dado, responden preguntas de distintas categorías y acumulan puntos para intentar ganar la partida.

## Características

- Partidas locales con jugadores y bots.
- Tres niveles de dificultad para los bots: fácil, medio y difícil.
- Modo multijugador en línea mediante salas con código de invitación.
- Preguntas de opción múltiple o respuesta escrita.
- Siete categorías: Historia, Matemáticas, Filosofía, Ciencias, Arte, Cultura general y Geografía.
- Casillas y cartas EXTRA con retos, bonificaciones, penalizaciones y movimientos especiales.
- Perfiles, historial de partidas y logros guardados en el navegador.
- Temporizador para responder preguntas en las partidas en línea.

## Cómo funciona

El juego utiliza un banco de preguntas incluido en el proyecto. Las preguntas no se generan automáticamente durante cada partida: el juego selecciona preguntas del banco disponible y controla cuáles se han utilizado durante la partida.

En el modo local, los bots participan siguiendo la lógica de juego programada y el nivel de dificultad seleccionado.

El modo en línea utiliza un servidor Node.js con Express y WebSocket para administrar salas y sincronizar el estado de la partida entre participantes.

## Tecnologías

- React
- TypeScript
- Vite
- Tailwind CSS
- Node.js
- Express
- WebSocket (`ws`)

## Requisitos

- Node.js instalado.
- npm (incluido con Node.js).

## Ejecutar el proyecto localmente

1. Descarga o clona este repositorio.
2. Abre una terminal en la carpeta del proyecto.
3. Instala las dependencias:

   ```bash
   npm install
   ```

4. Inicia la aplicación en modo desarrollo:

   ```bash
   npm run dev
   ```

5. Abre en el navegador la dirección local que indique la terminal. De forma predeterminada, el servidor utiliza el puerto `3000`.

## Crear una compilación de producción

Para generar los archivos de producción del frontend, ejecuta:

```bash
npm run build
```

La compilación se genera en la carpeta `dist/`.

**Importante para el despliegue:** el proyecto incluye un servidor Node.js y utiliza WebSocket para el modo multijugador. Para mantener esa modalidad al publicar el juego, el servicio de alojamiento debe poder ejecutar una aplicación Node.js y admitir conexiones WebSocket. Un alojamiento exclusivamente estático puede servir el frontend, pero no ejecutará por sí solo el servidor de partidas en línea.

El servidor utiliza la variable de entorno `PORT` cuando está definida; si no, escucha en el puerto `3000`.

## Estructura general

```text
.
├── public/              # Recursos públicos
├── src/
│   ├── components/      # Pantallas y componentes de interfaz
│   ├── data/            # Tablero, preguntas, cartas y logros
│   ├── types/           # Tipos de TypeScript
│   ├── utils/           # Sonido y almacenamiento de perfiles
│   ├── App.tsx          # Lógica principal de la aplicación
│   ├── index.css        # Estilos globales
│   └── main.tsx         # Punto de entrada de React
├── server.ts            # Servidor Express y WebSocket
├── package.json         # Dependencias y comandos
└── vite.config.ts       # Configuración de Vite
```

## Datos guardados

Los perfiles, logros e historial de partidas se almacenan en el `localStorage` del navegador. Por ello, esos datos pertenecen al navegador y dispositivo donde se juega; no se sincronizan automáticamente entre distintos dispositivos.

## Créditos

**Desarrollado por:**

- Goretti Betsabe Izquierdo Villalobos
- Brianna Paula Safa Rodriguez
- Santiago Carrizales Montelongo
- Valeria Sofía Mata Rodríguez
