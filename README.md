# WebSocketChat

**WebSocketChat** is a real-time chat application developed using **Node.js** and **Socket.io**. It enables users to communicate instantly by sending and receiving messages through WebSockets, offering a seamless, real-time chatting experience.

### How it Works

1. **Server Setup**: 
   - The server is created using **Express** and **Socket.io**. 
   - It serves static HTML files from the `public` directory to display the chat interface in the browser.

2. **WebSockets with Socket.io**:
   - When a user connects, a unique **socket** is created for that user.
   - The server listens for new connections and logs when a user joins via the socket’s `connection` event.
   
3. **Message Handling**:
   - All messages are stored in an array (`messages[]`) on the server.
   - When a new user joins, the server sends them the **previous messages** using the `previousMessages` event.
   - When a user sends a new message, it is sent to the server using the `sendMessage` event.
   - The server saves this message and broadcasts it to all other users using the `receivedMessage` event, so that everyone connected to the chat can see it in real time.

4. **Real-time Updates**:
   - By using **Socket.io**, messages are delivered instantly to all connected clients, creating a real-time chat experience without the need for page reloads.

### Key Features

- **Instant Messaging**: Users can send messages, which are immediately broadcast to all connected users in real-time.
- **Message History**: New users receive the chat history (stored messages) when they join, ensuring they are up-to-date with the conversation.
- **Simple UI**: The front-end uses **HTML** and **Socket.io** to render messages and handle interactions.

### How to Run

1. **Clone the repository**:
   ```
   git clone https://github.com/renatosilveira99/web-socket-chat
   ```

2. **Install the dependencies**:
   ```
   npm install
   ```

3. **Start the server**:
   ```
   npm start
   ```

4. **Access the application**:
   Open a browser and go to `http://localhost:3000` to start chatting.

### Code Overview

- **Server (`index.js`)**: 
   - Manages socket connections and message broadcasting.
   - Stores all messages in memory and sends them to new users when they connect.

- **Front-end**: 
   - The chat interface is built using **HTML** and uses **Socket.io** to communicate with the server, displaying messages in real-time.

---

This project demonstrates the basics of how to build a chat application using **Node.js** and **Socket.io**, making it a great starting point for learning about real-time communication over the web.
