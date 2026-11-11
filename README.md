# Laboratorio XMPP - Análisis de Tráfico en Texto Plano

## Descripción del Proyecto
Este proyecto despliega una topología de red cliente-servidor para el protocolo XMPP utilizando contenedores Docker. El objetivo principal es analizar la comunicación en texto puro (XML) mediante la desactivación forzada del cifrado TLS, permitiendo la recolección de evidencia en Wireshark y la demostración de vulnerabilidades de red (Sniffing, Spoofing, MitM).

## Archivos del Repositorio
* *Dockerfile.servidor:* Despliega el servidor XMPP ejabberd exponiendo el puerto 5222 hacia la red física.
* *Dockerfile.cliente:* Configura un contenedor basado en Ubuntu con el cliente de terminal profanity instalado.
* *docker-compose.yml:* Orquesta la construcción y conexión de ambos nodos en una red interna (red_xmpp).

## Instrucciones de Ejecución
1. Clonar este repositorio en una máquina local.
2. Construir e iniciar los contenedores en segundo plano ejecutando:
   docker-compose up -d --build
3. El servidor iniciará automáticamente. Para que un cliente remoto se conecte, debe apuntar su configuración a la IP física de la máquina host en el puerto 5222, asegurándose de desactivar TLS.
4. Para ejecutar el cliente local e interactuar con el chat, abrir la terminal del contenedor:
   docker exec -it cliente_profanity profanity

## Video de Demostración
[https://drive.google.com/file/d/13zp0AVO_Sm0cZnojYXiKilk1dP5xRQcV/view?usp=drive_link]
