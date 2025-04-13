# cowrie-elk

Este proyecto implementa un honeypot utilizando Cowrie para la captura de interacciones maliciosas SSH y Telnet, y utiliza el Elastic Stack para el análisis y visualización de los registros.  

Para obtener información detallada sobre Cowrie, consulta la [documentación oficial de Cowrie](https://github.com/cowrie/cowrie)

Este repositorio es un fork adaptado para funcionar con las nuevas versiones de ELK, implementando nuevas funcionalidades y mejoras. [Repositorio original](https://github.com/nagutabby/cowrie-elastic-stack).  

Además, se ha implementado un pipeline para geolocalizar las direcciones IP de los ataques y visualizarlas en un mapa, mejorando la capacidad de análisis de la procedencia de las amenazas.

**Importante:** Antes de la instalación, asegúrate de tener instalado en tu sistema (Debian/Ubuntu) Docker, Docker Compose y Git.

## Despliegue rápido

### Instrucciones:

1.  Clona este repositorio en tu equipo:  
    `git clone https://github.com/josusl/cowrie-elk`
2.  Levanta la pila de contenedores con Docker Compose:  
    `docker-compose up -d`
2.  Crea un nuevo fichero para guardar los logs:  
    `touch cowrie.json`
3.  Cambia los permisos a este fichero:
4.  `sudo chmod o+w cowrie/log/cowrie.json`
5.  Accede a Kibana a través de tu navegador:  
    `http://tu-direccion-ip:5601`
6.  Implementa manualmente el código de geolocalización. Copia el contenido del archivo *"copiar\_geolocalizacion.json"* y pégalo en la consola *"Dev Tools"* de Kibana. (Con este comando generaras los puntos *geo point* para interpretarlo en el mapa.)
7.  Finalmente, indexa el índice **"indice_cowrie"** en Kibana para poder visualizar los datos. Y crea el dashboard a tu gusto.