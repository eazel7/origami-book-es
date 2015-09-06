#### 1. Base de datos MongoDB

De forma predeterminada, Origami utiliza la base de datos `origami-dev` en `localhost:27017`, sin autenticación.
Para cambiar esta configuración, abra el archivo `manager/config-default.json` y actualícelo de forma acorde a su entorno.

```
{
  "ip": "0.0.0.0", // IP a la que responde pedidos
  "port": 9000, // puerto en el que escucha los pedidos
  "expressSecret": "thisIsAnObviousSecret", // clave para encriptar las cookies
  "auth": {
    // "origami-auth-local" es un nombre de plugin de autenticación
    // el objeto llega al plugin como su configuración
    "origami-auth-local": {
      "mongo": {
        // base de datos donde se guardarán los nombres de usuario locales
        "database": "origami-dev",
        // host de la base de datos
        "host": "127.0.0.1",
        // puerto
        "port": 27017,
        // usuario, dejar en blanco para no utilizar autenticación de MongoDB
        "username": "",
        "password": "",
        // nombre de la colección con los usuarios y contraseñas locales
        "collection": "local-users"
      }
    }
  },
  // protocolo con el que se escuchará, puede ser "http" o "spdy"
  // en el caso de elegir "spdy" la sección "keys" es requerida
  "protocol": "spdy",
  "keys": {
    // clave privada para SSL
    "key": "keys/localhost.pem",
    // certificado para SSL
    "cert": "keys/localhost.pem",
    // certificado de la entidad de certificación para SSL
    "ca": "keys/localhost.pem"
  },
  // URL con la que se anunciarán las aplicaciones
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
  }
}
```

#### 2. Instalación de paquetes básicos de UI

#### 3. Generación de certificados para SSL

