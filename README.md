# Team-Talk

Team Talk is a Java project that enables group communication over a local Wi-Fi hotspot. It supports multi-user text chat and optional voice streaming using Java sockets and multi-threading.

## Features

- Multi-user text chat
- Optional voice streaming
- User login/signup with database authentication (MySQL)
- Multi-threaded server handling multiple clients simultaneously

## Folder Structure
ProjectName/
│── chatdb.sql
│── dbauth.dat
│── lib/
│   └── mysql-connector.jar
│── src/
    ├── chatclient/
    │   ├── ChatFrame.java
    │   ├── Client.java
    │   ├── LoginDialog.java
    │   └── SignupDialog.java
    └── chatserver/
        ├── ClientHandler.java
        ├── DBManager.java
        ├── Server.java
        └── Session.java


## Overview

- The **server** handles multiple clients using threads and communicates with a MySQL database for authentication and session management.  
- The **client** provides a GUI for login, signup, and chatting with other users connected to the same local network.  

## Requirements

- Java 8 or higher
- MySQL server
- MySQL JDBC driver (`mysql-connector.jar` included in `lib/`)

## Setup Notes

1. **Database Setup**  
   - Run `chatdb.sql` on your MySQL server to create the database and tables.  
   - `dbauth.dat` contains the database credentials. Make sure it is correctly configured and secure.  

2. **Network Setup**  
   - Clients and server must be on the same local Wi-Fi hotspot.  
   - Voice streaming may require additional network configuration depending on your firewall and OS.  

3. **Compilation & Running**  
   - Compile all `.java` files:
     ```bash
     javac -cp lib/mysql-connector.jar -d bin src/chatserver/*.java src/chatclient/*.java
     ```
   - Start the server:
     ```bash
     java -cp "bin:lib/mysql-connector.jar" chatserver.Server
     ```
   - Start the client(s):
     ```bash
     java -cp "bin:lib/mysql-connector.jar" chatclient.Client
     ```

## Notes

- `dbauth.dat` is sensitive; do not include it in public repositories.  
- Ensure that the MySQL server is running and accessible from the local network.  
- The project uses multi-threading to support multiple clients; each new client connection is handled in a separate thread.  

