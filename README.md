# Simulacro_Examen_Parcial_2

# Examen de Redes

## Índice
- [Parte I: Capa de Red](#parte-i-capa-de-red)  
  - [Pregunta 1: Cálculo de Ruta Más Corta](#pregunta-1-cálculo-de-ruta-más-corta)  
  - [Pregunta 2: Cálculo de Direcciones de Broadcast y Subredes](#pregunta-2-cálculo-de-direcciones-de-broadcast-y-subredes)  
  - [Pregunta 3: Última Dirección Válida y Rango de Hosts](#pregunta-3-última-dirección-válida-y-rango-de-hosts)  
  - [Pregunta 4: Capacidad y Segmentación de Subredes](#pregunta-4-capacidad-y-segmentación-de-subredes)  
  - [Pregunta 5: Número de Subredes Necesarias](#pregunta-5-número-de-subredes-necesarias)
    
- [Parte II: Capa de Transporte](#parte-ii-capa-de-transporte)  
  - [Pregunta 6: Comparación entre TCP y UDP](#pregunta-6-comparación-entre-tcp-y-udp)  
  - [Pregunta 7: Establecimiento y Terminación de Conexión en TCP](#pregunta-7-establecimiento-y-terminación-de-conexión-en-tcp)  
  - [Pregunta 8: Multiplexación y Demultiplexación](#pregunta-8-multiplexación-y-demultiplexación)  
  - [Pregunta 9: Cálculo del Tamaño de Ventana en TCP](#pregunta-9-cálculo-del-tamaño-de-ventana-en-tcp)  
  - [Pregunta 10: Control de Congestión en TCP](#pregunta-10-control-de-congestión-en-tcp)  
- [Parte III: Capa de Aplicación y Aplicaciones Multimedia](#parte-iii-capa-de-aplicación-y-aplicaciones-multimedia)  
  - [Pregunta 11: Funcionamiento de DNS](#pregunta-11-funcionamiento-de-dns)  
  - [Pregunta 12: Protocolos de Correo Electrónico](#pregunta-12-protocolos-de-correo-electrónico)  
  - [Pregunta 13: Funcionamiento de HTTP y FTP](#pregunta-13-funcionamiento-de-http-y-ftp)  
  - [Pregunta 14: Streaming y VoIP](#pregunta-14-streaming-y-voip)  
  - [Pregunta 15: Control de Congestión en Redes Multimedia](#pregunta-15-control-de-congestión-en-redes-multimedia)  
  - [Pregunta 16: Best-Effort vs Servicios Multiclase](#pregunta-16-best-effort-vs-servicios-multiclase)
     
- [Parte IV: Seguridad en Redes](#parte-iv-seguridad-en-redes)  
  - [Pregunta 17: Problemas de Seguridad en Redes](#pregunta-17-problemas-de-seguridad-en-redes)  
  - [Pregunta 18: Cifrado Simétrico vs Asimétrico](#pregunta-18-cifrado-simétrico-vs-asimétrico)  
  - [Pregunta 19: Funcionamiento del Algoritmo RSA](#pregunta-19-funcionamiento-del-algoritmo-rsa)  
  - [Pregunta 20: Firewalls, VPN e IPSec](#pregunta-20-firewalls-vpn-e-ipsec)  
  - [Pregunta 21: SSL/TLS y DNS Spoofing](#pregunta-21-ssltls-y-dns-spoofing)  

---

## Parte I: Capa de Red

### Pregunta 1: Cálculo de Ruta Más Corta
**a)** Explica brevemente el funcionamiento del Algoritmo de Dijkstra para encontrar la ruta más corta entre dos nodos en un grafo ponderado.  
**b)** Describe el método de Enrutamiento por Inundación (Flooding) y discute sus ventajas y desventajas comparándolo con Dijkstra.

### Pregunta 2: Cálculo de Direcciones de Broadcast y Subredes
**a)** Para la subred `172.29.152.0` con máscara `255.255.248.0`, determina la dirección de broadcast. Explica el proceso de conversión de la máscara a binario y cómo se obtiene el resultado.  
**b)** Dado el bloque `172.18.26.0/23`, calcula la dirección de broadcast y justifica el proceso.

### Pregunta 3: Última Dirección Válida y Rango de Hosts
**a)** Con la subred `172.30.67.192` y máscara `255.255.255.192`, determina cuál es la última dirección de host válida (excluyendo la dirección de broadcast).  
**b)** Para el host `172.22.53.199` con máscara `255.255.252.0`, determina el rango de direcciones válidas (primera y última dirección de host) de la subred.

### Pregunta 4: Capacidad y Segmentación de Subredes
**a)** Calcula el número de equipos (hosts) que pueden conectarse en la red `172.26.0.0` con máscara `255.255.255.192`.  
**b)** Dado el host `172.18.171.190/23`, identifica a qué subred pertenece, explicando cómo se determina el bloque correspondiente.

### Pregunta 5: Número de Subredes Necesarias
Explica cómo se determina el número de subredes disponibles utilizando la fórmula:  
Nº de subredes = 2^s
donde _s_ es el número de bits prestados al identificador de subred. Aplica este concepto a un escenario en el que se requieren al menos 4 subredes para segmentar una red.

---

## Parte II: Capa de Transporte

### Pregunta 6: Comparación entre TCP y UDP
**a)** Compara TCP y UDP en términos de:  
- Necesidad de establecer conexión  
- Fiabilidad y control de errores  
- Control de flujo y congestión  
- Velocidad de transmisión  
**b)** Menciona dos ejemplos de aplicaciones en las que se prefiera usar UDP y justifica la elección.

### Pregunta 7: Establecimiento y Terminación de Conexión en TCP
Describe en detalle el proceso de establecimiento de conexión en TCP (Three-Way Handshake) y el proceso de terminación de la conexión (Four-Way Handshake). Explica la importancia de cada uno de los pasos involucrados.

### Pregunta 8: Multiplexación y Demultiplexación
Explica el concepto de multiplexación descendente y multiplexación ascendente en la capa de transporte, y proporciona un ejemplo práctico para cada caso.

### Pregunta 9: Cálculo del Tamaño de Ventana en TCP
Se tiene un enlace con los siguientes parámetros:

- RTT = 50 ms  
- Ancho de banda = 100 Mbps  
- MSS (Tamaño máximo de segmento) = 1 500 bytes  

Realiza lo siguiente:  
1. Convierte las unidades necesarias (RTT a segundos y ancho de banda a bps).  
2. Calcula el tamaño óptimo de la ventana en bits y en bytes con la fórmula:  
Ventana_óptima = Ancho de banda × RTT
3. Determina aproximadamente el número de segmentos MSS que pueden estar en tránsito simultáneamente.  
4. Muestra todos los pasos de tu cálculo.

### Pregunta 10: Control de Congestión en TCP
Explica brevemente cómo TCP implementa mecanismos de control de congestión, haciendo énfasis en:  
- El Algoritmo de Arranque Lento (Slow Start)  
- El Algoritmo de Nagle  
- El Algoritmo de Clark  

Para cada uno, menciona su objetivo y cómo contribuye a optimizar el rendimiento de la red.

---

## Parte III: Capa de Aplicación y Aplicaciones Multimedia

### Pregunta 11: Funcionamiento de DNS
Describe el proceso completo de resolución de nombres en el Sistema de Nombres de Dominio (DNS), desde que el usuario ingresa un dominio en el navegador hasta que se obtiene la dirección IP del servidor.

### Pregunta 12: Protocolos de Correo Electrónico
Compara las características de los protocolos POP3, IMAP y SMTP en términos de:  
- Función principal  
- Tipo de uso y acceso  
- Modo de almacenamiento de correos  

Incluye ejemplos de situaciones en las que cada uno sea más adecuado.

### Pregunta 13: Funcionamiento de HTTP y FTP
**a)** Explica el funcionamiento básico de HTTP, mencionando los métodos más utilizados (GET, POST, PUT, DELETE).  
**b)** Describe el funcionamiento de FTP y señala las diferencias esenciales con HTTP, especialmente en el uso de conexiones (control y datos).

### Pregunta 14: Streaming y VoIP
**a)** Define y compara brevemente los siguientes tipos de streaming:  
- UDP Streaming  
- HTTP Streaming  
- Adaptive HTTP Streaming (DASH)  

Menciona un ejemplo de aplicación para cada uno.  
**b)** Explica el proceso de funcionamiento de VoIP (Voz sobre IP) y enumera algunos problemas comunes (retardo, pérdida de paquetes, eco) junto con posibles soluciones.

### Pregunta 15: Control de Congestión en Redes Multimedia
Describe dos técnicas utilizadas para evitar la congestión en aplicaciones multimedia (por ejemplo, uso de buffering en el cliente o marcado de paquetes – DiffServ) y explica cómo contribuyen a mejorar la calidad del servicio.

### Pregunta 16: Best-Effort vs Servicios Multiclase
Compara el modelo Best-Effort con los Servicios Multiclase, enfatizando:  
- La manera en que se maneja el tráfico  
- La garantía (o falta de ella) en la calidad de servicio  
- Ejemplos de aplicaciones para cada enfoque

---

## Parte IV: Seguridad en Redes

### Pregunta 17: Problemas de Seguridad en Redes
Identifica y explica brevemente las siguientes áreas críticas de seguridad en redes, mencionando para cada una una técnica o solución para mitigar el riesgo:  
- Confidencialidad  
- Autenticación  
- No repudio  
- Integridad

### Pregunta 18: Cifrado Simétrico vs Asimétrico
Realiza una comparación entre cifrado simétrico y asimétrico, abordando:  
- Número de claves requeridas  
- Velocidad y eficiencia  
- Ejemplos de algoritmos y aplicaciones típicas en cada caso

### Pregunta 19: Funcionamiento del Algoritmo RSA
**a)** Describe el proceso de generación de claves en RSA (selección de primos, cálculo de _n_ y _ϕ(n)_, determinación de _e_ y _d_).  
**b)** Realiza un ejemplo numérico sencillo (por ejemplo, _p_ = 3, _q_ = 11, _e_ = 7) para demostrar el cifrado y descifrado de un mensaje (_M_ = 4).

### Pregunta 20: Firewalls, VPN e IPSec
**a)** Explica el funcionamiento de un firewall, mencionando al menos dos tipos (filtrado de paquetes y firewall de estado) y su importancia.  
**b)** Compara VPN e IPSec en términos de propósito, modo de operación y ejemplos de uso.

### Pregunta 21: SSL/TLS y DNS Spoofing
**a)** Describe brevemente el funcionamiento del protocolo SSL/TLS y su importancia para la seguridad en la web (HTTPS).  
**b)** Explica qué es el DNS Spoofing y cómo DNSSEC ayuda a proteger la integridad de las respuestas DNS.
