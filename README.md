#  Taller-Tarea2: Protocolo IRC en Docker

Este proyecto implementa una comunicación IRC (Internet Relay Chat) completamente contenida en Docker, utilizando **InspIRCd** como servidor IRC y **irssi** como cliente. Fue desarrollado como parte de un trabajo académico para comprender el funcionamiento del protocolo IRC y cómo interactúan sus componentes.

---

##  Tabla de contenido

- [Información general](#información-general)
- [Tecnologías utilizadas](#tecnologías-utilizadas)
- [Instalación del servidor IRC](#instalación-del-servidor-irc)
- [Instalación y uso del cliente IRC](#instalación-y-uso-del-cliente-irc)
- [Conexión Cliente-Servidor](#conexión-cliente-servidor)
- [Estado del proyecto](#estado-del-proyecto)
- [Autores](#autores)

---

##  Información general

El objetivo principal del proyecto es levantar un entorno IRC funcional entre un cliente y un servidor utilizando contenedores Docker. El cliente y el servidor se comunican a través de la red local mediante el protocolo IRC, con el fin de enviar y recibir mensajes dentro de un canal común.

**Objetivos específicos:**

- Crear un servidor IRC con InspIRCd utilizando Docker.
- Ejecutar un cliente IRC (irssi) dentro de otro contenedor Docker.
- Establecer la comunicación entre ambos.
- Probar comandos básicos IRC como `/connect`, `/nick`, `/join` y `/msg`.

---

##  Tecnologías utilizadas

- Docker 24.0+
- InspIRCd (Servidor IRC)
- irssi (Cliente IRC)
- Terminal bash
- Sistema operativo Linux

---

##  Instalación del servidor IRC

Ejecuta el siguiente comando para crear y ejecutar el servidor IRC con InspIRCd:

```bash
docker run -d --name irc-server -p 6667:6667 inspircd/inspircd-docker
```

Para reiniciar el servidor después de haberlo detenido:

```bash
docker start irc-server
```

---

##  Instalación y uso del cliente IRC

Ejecutar el cliente IRC `irssi` en un contenedor Docker conectado a la red host:

```bash
docker run -it --name irc-client --network host irssi
```

Si el cliente fue cerrado, se puede volver a ingresar con:

```bash
docker start -ai irc-client
```

---

##  Conexión Cliente-Servidor

Para establecer conexión con el servidor, asegúrate de conocer la dirección IP del host (donde está corriendo el contenedor del servidor) y el puerto (6667).

Dentro de irssi, usar los siguientes comandos:

```text
/connect 192.168.100.9 6667
/nick Test
/join #test
/msg #test message
```

Reemplazar `192.168.100.9` con la IP real de tu servidor si es distinta.

---




## Autores

- Felipe Cuevas  
- Ignacio Antiguay
