```plantuml
actor Client
database Server
Client -> Server : Hi i want to talk via Websocket
Server -> Client : Hört sich gut an

Client -> Server : Das ist eine Nachricht 
Client -> Server : Noch eine Nachricht
Server --> Client : Super habe beide bekommen

note right
	The Connection between server and 
	Client does not get stopped
end note


```

```plantuml

class connection{

}

class message {

}

class room {

}

class Server {

}

class Client {

}
```