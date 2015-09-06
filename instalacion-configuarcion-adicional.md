#### 1. Base de datos MongoDB

De forma predeterminada, Origami utiliza la base de datos `origami-dev` en `localhost:27017`, sin autenticación.
Para cambiar esta configuración, abra el archivo `manager/config-default.json`


```
{
  "ip": "0.0.0.0", // IP a la que responde pedidos
  "port": 9000, // puerto en el que escucha los pedidos
  "expressSecret": "thisIsAnObviousSecret", // clave para encriptar las cookies
  "auth": {
    "origami-auth-local": {
      "mongo": {
        "database": "origami-dev",
        "host": "127.0.0.1",
        "port": 27017,
        "username": "",
        "password": "",
        "collection": "local-users"
      }
    }
  },
  "protocol": "spdy",
  "prefix": "https://localhost:9000/",
  "mongo": {
    "database": "origami-dev",
    "host": "127.0.0.1",
    "port": 27017,
    "username": "",
    "password": ""
  },
  "mongoSessions": {
    "db": "origami-dev",
    "host": "127.0.0.1",
    "port": 27017,
    "username": "",
    "password": "",
    "auto_reconnect": true
  },
  "keys": {
    "key": "keys/localhost.pem",
    "cert": "keys/localhost.pem",
    "ca": "keys/localhost.pem"
  }
}
```