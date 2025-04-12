# cowrie-elk

Este proyecto implementa un honeypot utilizando Cowrie para la captura de interacciones maliciosas SSH y Telnet, y utiliza el Elastic Stack para el análisis y visualización de los registros.  

Para obtener información detallada sobre Cowrie, consulta la [documentación oficial de Cowrie](https://github.com/cowrie/cowrie)

Este repositorio es un fork adaptado para funcionar con las nuevas versiones del Elastic Stack.  

Además, se ha implementado un pipeline para geolocalizar las direcciones IP de los ataques y visualizarlas en un mapa, mejorando la capacidad de análisis de la procedencia de las amenazas.

**Importante:** Antes de la instalación, asegúrate de tener instalado en tu sistema (Debian/Ubuntu) Docker, Docker Compose y Git.

## Despliegue rápido

Las instrucciones de despliegue se han simplificado para una configuración rápida:

1.  Clona este repositorio en tu equipo local:  
    `git clone https://github.com/josusl/cowrie-elk`
2.  Levanta la pila de contenedores con Docker Compose:  
    `docker-compose up -d`
3.  Accede a Kibana a través de tu navegador:  
    `http://tu-direccion-ip:5601`
4.  Implementa manualmente el código de geolocalización.  
    Copia el contenido del archivo "copiar\_geolocalizacion.json" y pégalo en la consola "Dev Tools" de Kibana.
5.  Finalmente, indexa el índice en Kibana para poder visualizar los datos.
