# WebSocket Server: Real-Time Document Editor

A real-time collaborative text editor. Users can create, open, edit, and delete documents, and every change is pushed instantly to everyone viewing the same document. Documents are saved in MongoDB.

Built while following Alura's WebSockets course, as a learning project on real-time communication.

## Tech

Node.js · Express · Socket.IO · MongoDB · HTML / JavaScript

## Features

- Create, list, and delete documents
- Live editing: text changes are broadcast to every client in the same document
- Persistent storage in MongoDB
- Duplicate-name check when creating a document

## How it works

- `src/servidor.js`: Express serves the front end and starts the Socket.IO server.
- `src/socket-back.js`: handles socket events (list, create, edit, delete documents).
- `src/documentosDb.js`: MongoDB queries for the `documentos` collection.
- `public/`: front end that connects to the server through Socket.IO.

## Run locally

```bash
git clone https://github.com/JoaoAntonioCarvalho/WebSocket-Server
cd WebSocket-Server
npm install
```

Create a `.env` file in the project root with your MongoDB connection string:

```
LINK=mongodb+srv://<user>:<password>@<cluster>/
```

Then start the server:

```bash
npm run dev
```

Open http://localhost:3100.

## What I learned

- How WebSockets differ from regular HTTP requests
- Event-driven server design with Socket.IO rooms and events
- Keeping several clients in sync with a shared database
