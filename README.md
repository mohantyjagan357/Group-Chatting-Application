<div align="center">

```
 ██████╗ ██████╗  ██████╗ ██╗   ██╗██████╗ 
██╔════╝ ██╔══██╗██╔═══██╗██║   ██║██╔══██╗
██║  ███╗██████╔╝██║   ██║██║   ██║██████╔╝
██║   ██║██╔══██╗██║   ██║██║   ██║██╔═══╝ 
╚██████╔╝██║  ██║╚██████╔╝╚██████╔╝██║     
 ╚═════╝ ╚═╝  ╚═╝ ╚═════╝  ╚═════╝ ╚═╝     
 ██████╗██╗  ██╗ █████╗ ████████╗
██╔════╝██║  ██║██╔══██╗╚══██╔══╝
██║     ███████║███████║   ██║   
██║     ██╔══██║██╔══██║   ██║   
╚██████╗██║  ██║██║  ██║   ██║   
 ╚═════╝╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝   
     █████╗ ██████╗ ██████╗ ██╗     ██╗ ██████╗ █████╗ ████████╗██╗ ██████╗ ███╗   ██╗
    ██╔══██╗██╔══██╗██╔══██╗██║     ██║██╔════╝██╔══██╗╚══██╔══╝██║██╔═══██╗████╗  ██║
    ███████║██████╔╝██████╔╝██║     ██║██║     ███████║   ██║   ██║██║   ██║██╔██╗ ██║
    ██╔══██║██╔═══╝ ██╔═══╝ ██║     ██║██║     ██╔══██║   ██║   ██║██║   ██║██║╚██╗██║
    ██║  ██║██║     ██║     ███████╗██║╚██████╗██║  ██║   ██║   ██║╚██████╔╝██║ ╚████║
    ╚═╝  ╚═╝╚═╝     ╚═╝     ╚══════╝╚═╝ ╚═════╝╚═╝  ╚═╝   ╚═╝   ╚═╝ ╚═════╝ ╚═╝  ╚═══╝
```

### ⬡ Java · Sockets · Multi-threading · MySQL · Real-time Chat

[![Java](https://img.shields.io/badge/Java-17+-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://adoptium.net/)
[![Sockets](https://img.shields.io/badge/Java-Sockets-326CE5?style=for-the-badge&logo=java&logoColor=white)](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/Socket.html)
[![Threads](https://img.shields.io/badge/Multi--Threading-Enabled-8B5CF6?style=for-the-badge)](https://docs.oracle.com/en/java/javase/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-Backend-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/)
[![Maven](https://img.shields.io/badge/Maven-Build-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)](https://maven.apache.org/)

<br/>

> **A real-time multi-client Group Chatting Application built from scratch in Java.**
> **One server. Many clients. Instant message broadcasting. Pure socket power.**

```
  CLIENT 1 ──┐
             │
  CLIENT 2 ──┼──► [ SERVER :PORT ] ──► broadcasts to ALL connected clients
             │         │
  CLIENT 3 ──┘         └──► MySQL (message persistence)
```

</div>

---

## 💬 What Is This?

**Group-Chatting-Application** is a real-time chat system built entirely in **Java** using **TCP Sockets** and **Multi-threading**. It follows a classic **Server-Client architecture** — a central server manages all connections, and every message sent by any client is instantly broadcast to all other connected participants in the group.

This project demonstrates core Java networking concepts — `ServerSocket`, `Socket`, `InputStream/OutputStream`, `Thread` — along with **MySQL** for optional message persistence and **Spring Boot** for the backend layer.

---

## ⚡ How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                        SERVER  (:PORT)                           │
│                                                                  │
│    ServerSocket.accept()  ←─── waits for new connections         │
│           │                                                      │
│     ┌─────▼──────────────────────────────────────────────┐      │
│     │              ClientHandler Thread Pool              │      │
│     │                                                     │      │
│     │   Thread-1 (Client A)   Thread-2 (Client B)  ...   │      │
│     │        │                      │                     │      │
│     │        └──────────────────────┘                     │      │
│     │               BROADCAST                             │      │
│     │     message from A → sent to B, C, D ...            │      │
│     └─────────────────────────────────────────────────────┘      │
│                          │                                       │
│                    ┌─────▼──────┐                                │
│                    │   MySQL    │  (message history)             │
│                    └────────────┘                                │
└─────────────────────────────────────────────────────────────────┘

┌──────────┐        TCP Socket        ┌──────────┐
│ CLIENT A │ ◄──────────────────────► │  SERVER  │
└──────────┘                          └──────────┘

┌──────────┐        TCP Socket        ┌──────────┐
│ CLIENT B │ ◄──────────────────────► │  SERVER  │
└──────────┘                          └──────────┘
```

---

## ✨ Features

| Feature | Detail |
|---|---|
| 💬 **Real-time Messaging** | Instant message delivery across all connected clients |
| 👥 **Multi-Client Support** | Multiple users can connect and chat simultaneously |
| 🧵 **Multi-threading** | Each client handled by a dedicated thread — no blocking |
| 📡 **TCP Socket Communication** | Reliable, ordered message delivery via Java Sockets |
| 🗄️ **MySQL Persistence** | Chat messages stored in database for history |
| 🚀 **Spring Boot Backend** | Clean backend structure with Maven build |
| 🏷️ **Username Support** | Each client connects with a unique username |
| 📢 **Broadcast Engine** | Server relays every message to all active clients |
| 🔌 **Join/Leave Notifications** | Group notified when a user joins or disconnects |

---

## 🛠️ Tech Stack

```
Language         │  Java 17+
Architecture     │  Server-Client (TCP Sockets)
Concurrency      │  Java Multi-threading (one thread per client)
Backend          │  Spring Boot + Maven
Database         │  MySQL 8.0
Networking       │  java.net.ServerSocket / Socket
I/O              │  java.io.BufferedReader / PrintWriter
IDE              │  IntelliJ IDEA (recommended)
```

---

## 📁 Project Structure

```
Group-Chatting-Application/
│
├── src/
│   └── main/
│       ├── java/
│       │   └── com/chat/application/
│       │       ├── server/
│       │       │   ├── ChatServer.java          # Main server — binds port, accepts clients
│       │       │   └── ClientHandler.java       # Thread per client — reads & broadcasts msgs
│       │       ├── client/
│       │       │   ├── ChatClient.java          # Client — connects to server, sends/receives
│       │       │   └── MessageListener.java     # Thread to listen for incoming messages
│       │       ├── model/
│       │       │   └── Message.java             # Message entity (sender, content, timestamp)
│       │       ├── repository/
│       │       │   └── MessageRepository.java   # JPA repository for message persistence
│       │       └── GroupChattingApplication.java
│       └── resources/
│           └── application.properties           # DB + server port config
│
├── .mvn/wrapper/                                # Maven wrapper
├── mvnw / mvnw.cmd
├── pom.xml
└── README.md
```

---

## ⚙️ Prerequisites

| Tool | Purpose | Install |
|---|---|---|
| ☕ Java JDK 17+ | Compile & run | [adoptium.net](https://adoptium.net/) |
| 🐬 MySQL 8.0+ | Message persistence | [mysql.com](https://dev.mysql.com/downloads/) |
| 💡 IntelliJ IDEA | IDE (recommended) | [jetbrains.com](https://www.jetbrains.com/idea/) |
| 📦 Maven 3.8+ | Build tool | [maven.apache.org](https://maven.apache.org/) *(mvnw included)* |

---

## 🚀 Getting Started

### Step 1 — Clone the Repository
```bash
git clone https://github.com/mohantyjagan357/Group-Chatting-Application.git
cd Group-Chatting-Application
```

### Step 2 — Set Up MySQL Database
```sql
CREATE DATABASE chat_db;
```

### Step 3 — Configure `application.properties`
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/chat_db
spring.datasource.username=YOUR_MYSQL_USERNAME
spring.datasource.password=YOUR_MYSQL_PASSWORD
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
server.port=8080
chat.server.port=9090
```

### Step 4 — Build the Project
```bash
./mvnw clean package -DskipTests    # Linux / Mac
mvnw.cmd clean package -DskipTests  # Windows
```

### Step 5 — Start the SERVER First 🔑

> **Critical: Always start the server before any clients!**

```bash
# Run the server
java -cp target/group-chatting-*.jar com.chat.application.server.ChatServer
```

Or run `ChatServer.java` directly from IntelliJ IDEA.

The server will start and listen for incoming client connections.

```
[SERVER] Chat Server started on port 9090
[SERVER] Waiting for clients...
```

### Step 6 — Start CLIENT(s) in Separate Terminals

Open a **new terminal for each client** and run:

```bash
java -cp target/group-chatting-*.jar com.chat.application.client.ChatClient
```

Or run multiple instances of `ChatClient.java` from IntelliJ IDEA.

```
Enter your username: Soumya
[CONNECTED] You joined the chat!
[SERVER] Soumya has joined the group 🎉
```

### Step 7 — Start Chatting! 💬

Type messages in any client terminal — they'll appear instantly on all other connected clients.

```
Soumya: Hey everyone! 👋
[SERVER] Ravi has joined the group
Ravi: Hi Soumya! What's up?
Soumya: Testing our Group Chat App 🚀
Ravi: This is awesome!
```

---

## 🔄 Message Flow Diagram

```
  SOUMYA types: "Hello!"
        │
        ▼
  ChatClient.java
  → sends via Socket OutputStream
        │
        ▼
  ChatServer.java
  → ClientHandler receives message
  → iterates over ALL connected clients
  → broadcasts to each via PrintWriter
        │
   ┌────┴──────────────────┐
   ▼                       ▼
RAVI's terminal        PRIYA's terminal
"Soumya: Hello!"      "Soumya: Hello!"
```

---

## 🧵 Multi-threading Design

```java
// Server accepts new connection → spawns a thread
while (true) {
    Socket clientSocket = serverSocket.accept();
    ClientHandler handler = new ClientHandler(clientSocket, clients);
    new Thread(handler).start();  // each client = own thread
    clients.add(handler);
}

// ClientHandler reads message → broadcasts to all
public void run() {
    String message;
    while ((message = reader.readLine()) != null) {
        broadcast("[" + username + "]: " + message);
    }
}
```

This ensures **no client blocks another** — true concurrent multi-user messaging.

---

## 🗺️ Roadmap

- [x] TCP Socket-based real-time messaging
- [x] Multi-threaded server (one thread per client)
- [x] Username-based identification
- [x] Join/leave notifications
- [x] MySQL message persistence
- [ ] Private (direct) messaging between users
- [ ] Chat room / channel support
- [ ] File & image sharing
- [ ] Web frontend (React + WebSocket)
- [ ] JWT authentication
- [ ] Docker containerisation

---

## 🤝 Contributing

1. Fork the repository
2. Create your branch: `git checkout -b feature/private-messaging`
3. Commit: `git commit -m 'feat: add private messaging support'`
4. Push: `git push origin feature/private-messaging`
5. Open a Pull Request

---

## 👨‍💻 Author

<div align="center">

**Soumya Mohanty**

[![GitHub](https://img.shields.io/badge/GitHub-mohantyjagan357-1fffa0?style=for-the-badge&logo=github&logoColor=white)](https://github.com/mohantyjagan357)

*DevOps Engineer · Java Developer · Cloud Native*

</div>

---

<div align="center">

```
// BUILT WITH JAVA · SOCKETS · THREADS · MYSQL //
// CONNECT IT. CHAT IT. BROADCAST IT. //
```

⭐ **Star this repo if you found it useful!**

</div>
