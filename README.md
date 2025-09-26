# Team-Talk
Team Talk is a Java project that enables group communication over a local Wi-Fi hotspot. It supports multi-user text chat and optional voice streaming using Java sockets and multi-threading.
put the files in the following folder structure
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
