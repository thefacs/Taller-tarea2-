# Taller-tarea2- Protocolo IRC en Docker 

Este documento contiene las instrucciones para establecer el protocolo IRC(InspIRCd) en Docker en conjunto de contenedores para inicializar el Cliente y el Servidor. 

# Instalación del servidor IRC (InspIRCd)

Ejecute el siguiente comando para crear y ejecutar el servidor:

docker run -d --name irc-server -p 6667:6667 inspircd/inspircd-docker

# Reiniciar el servidor despues de cerrarlo

docker start irc-server

# Instalación y uso del cliente

docker run -it --name irc-client --network host irssi

# Volver al Irsii despues de cerrarlo 

docker start -ai irc-client

# Conexión Cliente-Servidor

Para establecer esta conexión, es necesario considerar la dirección IP donde se encuentra alojado el servidor, así como el puerto expuesto que se configuró al crear el contenedor Docker del servidor; en este caso, el puerto 6667

/connect 192.168.100.9 6667
/nick Test
/join #test
/msg #test message
