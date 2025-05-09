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
