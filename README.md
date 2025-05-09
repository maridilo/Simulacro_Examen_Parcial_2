# Simulacro Examen Parcial 2 Redes

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
    1. **Inicialización**: A cada nodo se le asigna una distancia inicial ∞, salvo el nodo origen que recibe 0.  
    2. **Selección**: Se elige el nodo no visitado con la distancia mínima.  
    3. **Relajación**: Para cada vecino del nodo seleccionado, se comprueba si la distancia al origen puede mejorar pasando por el nodo actual; en caso afirmativo, se actualiza.  
    4. **Marcaje**: El nodo seleccionado pasa a visitado y no se vuelve a considerar.  
    5. **Repetición**: Se repiten pasos 2–4 hasta visitar todos los nodos o alcanzar el destino.  

> **Complejidad**: O((V+E)·log V) con montículos binarios (V = nodos, E = aristas).

**b)** Describe el método de Enrutamiento por Inundación (Flooding) y discute sus ventajas y desventajas comparándolo con Dijkstra.
- **Mecanismo**: Cada paquete recibido se reenvía a **todos** los vecinos excepto aquel por el que llegó. Se suelen usar contadores de saltos (TTL) o caché de paquetes para evitar bucles.  
- **Ventajas**:  
  - No requiere tablas de enrutamiento ni información global.  
  - Si existe al menos un camino, lo encontrará.  
- **Desventajas**:  
  - **Sobrecarga**: Gran cantidad de duplicados inundan la red.  
  - **Ineficiente**: Usa ancho de banda innecesario.  
  - **No óptimo**: No garantiza la ruta más corta ni evalúa costes.
    
---

### Pregunta 2: Cálculo de Direcciones de Broadcast y Subredes
**a)** Para la subred `172.29.152.0` con máscara `255.255.248.0`, determina la dirección de broadcast. Explica el proceso de conversión de la máscara a binario y cómo se obtiene el resultado.  
1. **Máscara en binario**:
   255.255.248.0 → 11111111.11111111.11111000.00000000
2. **Bits de host**: 32 – 21 = 11 bits.  
3. **Broadcast**: Al poner todos los bits de host a 1:
   172.29. (152 → 10011000) | host=11111111.111 → 159.255 → 172.29.159.255
   
**b)** Dado el bloque `172.18.26.0/23`, calcula la dirección de broadcast y justifica el proceso.
1. **Máscara**:  255.255.252.0 → 11111111.11111111.11111100.00000000
2. **Bloque de 4 en tercer octeto** (bits de red: 22): 252 = 11111100 → múltiplos de 4.  
3. **Red**: tercer octeto de 53 → 52 (último múltiplo de 4 ≤ 53) → 172.22.52.0  
4. **Broadcast**: suma 3 al tercer octeto y pone host=255 → 172.22.55.255  
5. **Rango de hosts**:  
- Primera: 172.22.52.1  
- Última: 172.22.55.254

---

### Pregunta 3: Última Dirección Válida y Rango de Hosts
**a)** Con la subred `172.30.67.192` y máscara `255.255.255.192`, determina cuál es la última dirección de host válida (excluyendo la dirección de broadcast).  
- Tamaño: 2^(32–26)=2^6=64 direcciones (hosts+red+broadcast).  
- Rango de la subred: 172.30.67.192–172.30.67.255  
- **Broadcast**: 172.30.67.255  
- **Última host válida**: 172.30.67.254  

**b)** Para el host `172.22.53.199` con máscara `255.255.252.0`, determina el rango de direcciones válidas (primera y última dirección de host) de la subred.
1. **Máscara**:  
255.255.252.0 → 11111111.11111111.11111100.00000000
2. **Bloque de 4 en tercer octeto** (bits de red: 22): 252 = 11111100 → múltiplos de 4.  
3. **Red**: tercer octeto de 53 → 52 (último múltiplo de 4 ≤ 53) → 172.22.52.0  
4. **Broadcast**: suma 3 al tercer octeto y pone host=255 → 172.22.55.255  
5. **Rango de hosts**:  
- Primera: 172.22.52.1  
- Última: 172.22.55.254  

---

### Pregunta 4: Capacidad y Segmentación de Subredes
**a)** Calcula el número de equipos (hosts) que pueden conectarse en la red `172.26.0.0` con máscara `255.255.255.192`.  
- Hosts = 2^(32–26) – 2 = 64 – 2 = **62 equipos**.
  
**b)** Dado el host `172.18.171.190/23`, identifica a qué subred pertenece, explicando cómo se determina el bloque correspondiente.
1. /23 → bloques de 2 en el tercer octeto.  
2. 171 → múltiplo de 2 más cercano ≤ 171 = 170.  
3. **Subred**: 172.18.170.0/23.

---

### Pregunta 5: Número de Subredes Necesarias
Explica cómo se determina el número de subredes disponibles utilizando la fórmula:  
Nº de subredes = 2^s
donde _s_ es el número de bits prestados al identificador de subred. Aplica este concepto a un escenario en el que se requieren al menos 4 subredes para segmentar una red.
- Para ≥ 4 subredes: 2^s ≥ 4 → s ≥ 2.
- **Ejemplo**: partimos de /24, pedimos s=2 → /26 → obtenemos 4 subredes de 64 direcciones cada una.
  
---

## Parte II: Capa de Transporte

### Pregunta 6: Comparación entre TCP y UDP
**a)** Compara TCP y UDP en términos de:  
- Necesidad de establecer conexión  
- Fiabilidad y control de errores  
- Control de flujo y congestión  
- Velocidad de transmisión
  
| Característica                  | TCP                                  | UDP                         |
|---------------------------------|--------------------------------------|-----------------------------|
| **Conexión**                    | Orientado a conexión (handshake)     | Sin conexión                |
| **Fiabilidad**                  | Sí (retransmisiones, ACKs, secuencias) | No (mejor esfuerzo)         |
| **Control de flujo/congestión** | Ventana deslizante, Slow Start, AIMD | No integra                   |
| **Velocidad**                   | Menor (mayor sobrecarga)             | Mayor (menor overhead)      |

**b)** Menciona dos ejemplos de aplicaciones en las que se prefiera usar UDP y justifica la elección.
1. **VoIP** (p. ej. SIP/RTP): baja latencia, tolera pérdidas.  
2. **Streaming en vivo** (p. ej. IPTV): prefiere continuidad sobre retransmisión.

---

### Pregunta 7: Establecimiento y Terminación de Conexión en TCP
Describe en detalle el proceso de establecimiento de conexión en TCP (Three-Way Handshake) y el proceso de terminación de la conexión (Four-Way Handshake). Explica la importancia de cada uno de los pasos involucrados.
1. **Three-Way Handshake**  
 1. Cliente → Servidor: **SYN**, seq=x  
 2. Servidor → Cliente: **SYN-ACK**, seq=y, ack=x+1  
 3. Cliente → Servidor: **ACK**, ack=y+1  
 > Garantiza que ambos conocen el número de secuencia inicial y que el canal está operativo.

2. **Four-Way Handshake (cierre)**  
 1. Iniciador → Otro: **FIN**, seq=u  
 2. Otro → Iniciador: **ACK**, ack=u+1  
 3. Otro → Iniciador: **FIN**, seq=v  
 4. Iniciador → Otro: **ACK**, ack=v+1  
 > Asegura cierre ordenado y entrega de datos pendientes.

---

### Pregunta 8: Multiplexación y Demultiplexación
Explica el concepto de multiplexación descendente y multiplexación ascendente en la capa de transporte, y proporciona un ejemplo práctico para cada caso.

- **Multiplexación (descendente)**  
- Múltiples _streams_ de aplicación se encapsulan en segmentos TCP/UDP usando diferentes **puertos fuente**.  
- **Ejemplo**: un navegador abre conexiones simultáneas a varios servidores web; localmente usa puertos 49152, 49153, ….

- **Demultiplexación (ascendente)**  
- El receptor lee cada segmento y lo entrega a la aplicación correcta según **(IP destino, puerto destino)**.  
- **Ejemplo**: servidor web en puerto 80 distingue peticiones HTTP de clientes distintos por el par (IP_cliente, puerto_origen).

---

### Pregunta 9: Cálculo del Tamaño de Ventana en TCP
Se tiene un enlace con los siguientes parámetros:

- RTT = 50 ms  
- Ancho de banda = 100 Mbps  
- MSS (Tamaño máximo de segmento) = 1 500 bytes  

Realiza lo siguiente:  
-  Convierte las unidades necesarias (RTT a segundos y ancho de banda a bps).
   - RTT = 50 ms = 0,05 s  
   - BW = 100 Mbps = 100·10⁶ bps  
-  Calcula el tamaño óptimo de la ventana en bits y en bytes con la fórmula: Ventana_óptima = Ancho de banda × RTT
    - W = BW × RTT = 100·10⁶ bps × 0,05 s = 5·10⁶ bits = 5 000 000 bits ÷ 8 = 625 000 bytes
-  Determina aproximadamente el número de segmentos MSS que pueden estar en tránsito simultáneamente.
   N = 625 000 bytes ÷ 1 500 bytes ≈ 416,7 → ≈ 417 segmentos
   
Muestra todos los pasos de tu cálculo.

---

### Pregunta 10: Control de Congestión en TCP
Explica brevemente cómo TCP implementa mecanismos de control de congestión, haciendo énfasis en:  
- El Algoritmo de Arranque Lento (Slow Start)
  - Objetivo: descubrir capacidad disponible.  
  - Estrategia: cwnd inicia en 1 MSS y se duplica cada RTT hasta un umbral (ssthresh).
- El Algoritmo de Nagle
  - Objetivo: reducir número de segmentos pequeños.  
  - Estrategia: cuando hay datos sin ACK pendientes, agrupa y espera antes de enviar nuevos fragmentos.
- El Algoritmo de Clark
  - Objetivo: detección rápida de pérdidas y ajuste del envío.  
  - Estrategia: tras 3 ACK duplicados, retransmite inmediatamente el segmento perdido (fast retransmit) y aplica AIMD (reduce cwnd a la mitad).

---

## Parte III: Capa de Aplicación y Aplicaciones Multimedia

### Pregunta 11: Funcionamiento de DNS
Describe el proceso completo de resolución de nombres en el Sistema de Nombres de Dominio (DNS), desde que el usuario ingresa un dominio en el navegador hasta que se obtiene la dirección IP del servidor.
1. El usuario introduce “ejemplo.com”.  
2. El **resolver local** (stub) consulta al **servidor recursivo**.  
3. Si no está en caché, el recursivo pregunta al **root** → derivación al TLD “.com”.  
4. Se consulta al **servidor autoritativo** de “ejemplo.com”.  
5. Devuelve la **dirección IP**, que asciende al stub y al navegador.  
6. **Caché** intermedias aceleran futuras consultas.

---

### Pregunta 12: Protocolos de Correo Electrónico
Compara las características de los protocolos POP3, IMAP y SMTP en términos de:  
- Función principal  
- Tipo de uso y acceso  
- Modo de almacenamiento de correos  

Incluye ejemplos de situaciones en las que cada uno sea más adecuado.

| Protocolo | Función principal                     | Acceso                    | Almacenamiento            | Uso típico                         |
|-----------|---------------------------------------|---------------------------|---------------------------|-------------------------------------|
| **SMTP**  | Envío de correo (cliente → servidor)  | Puertos 25, 587           | No aplica                 | Servidores de salida                |
| **POP3**  | Descarga y borrado del servidor       | Puerto 110                | Local (cliente)           | Usuarios con acceso puntual         |
| **IMAP**  | Sincronización y acceso remoto        | Puerto 143                | Servidor                  | Múltiples dispositivos (móvil/PC)   |

---

### Pregunta 13: Funcionamiento de HTTP y FTP
**a)** Explica el funcionamiento básico de HTTP, mencionando los métodos más utilizados (GET, POST, PUT, DELETE).  
- Modelo **petición-respuesta** sobre TCP.  
- Métodos clave:  
- **GET**: leer recurso  
- **POST**: enviar datos al servidor  
- **PUT**: reemplazar recurso  
- **DELETE**: eliminar recurso
  
**b)** Describe el funcionamiento de FTP y señala las diferencias esenciales con HTTP, especialmente en el uso de conexiones (control y datos).
- Usa **dos conexiones** TCP:  
- **Control** (puerto 21): comandos  
- **Datos** (puerto dinámico o 20): transferencia  
- **Diferencias**: FTP mantiene canal separado para datos, HTTP usa la misma conexión (o multiplexa) para control y contenido.

---

### Pregunta 14: Streaming y VoIP
**a)** Define y compara brevemente los siguientes tipos de streaming:  
- **UDP Streaming**: RTP/UDP → baja latencia, usado en videoconferencias.  
- **HTTP Streaming**: HTTP progresivo → descarga continua, usado en YouTube.  
- **Adaptive HTTP Streaming (DASH)**: segmentos adaptativos según ancho de banda, usado en Netflix. 
  
**b)** Explica el proceso de funcionamiento de VoIP (Voz sobre IP) y enumera algunos problemas comunes (retardo, pérdida de paquetes, eco) junto con posibles soluciones.
1. **Proceso**: muestreo → codificación (codec) → encapsulado en RTP/UDP → envío IP → decodificación y reproducción.  
2. **Problemas**:  
- Retardo → jitter buffer  
- Pérdida de paquetes → FEC o retransmisión selectiva  
- Eco → cancelación de eco en extremos

---

### Pregunta 15: Control de Congestión en Redes Multimedia
Describe dos técnicas utilizadas para evitar la congestión en aplicaciones multimedia (por ejemplo, uso de buffering en el cliente o marcado de paquetes – DiffServ) y explica cómo contribuyen a mejorar la calidad del servicio.
1. **Buffering en cliente**  
  - Acumula datos antes de reproducir → suaviza variaciones de llegada.  
2. **Marcado de paquetes (DiffServ)**  
  - Etiqueta paquetes según prioridad → routers aplican colas diferenciadas.

---

### Pregunta 16: Best-Effort vs Servicios Multiclase
Compara el modelo Best-Effort con los Servicios Multiclase, enfatizando:  
- La manera en que se maneja el tráfico  
- La garantía (o falta de ella) en la calidad de servicio  
- Ejemplos de aplicaciones para cada enfoque

| Característica           | Best-Effort                         | Multiclase / QoS                |
|--------------------------|-------------------------------------|---------------------------------|
| Trato al tráfico         | “Mejor esfuerzo”, sin garantías     | Colas y prioridades definidas   |
| Garantía de servicio     | Ninguna                             | Garantías de retardo/ancho      |
| Ejemplos                 | Navegación web, email               | VoIP, videoconferencia          |

---

## Parte IV: Seguridad en Redes

### Pregunta 17: Problemas de Seguridad en Redes
Identifica y explica brevemente las siguientes áreas críticas de seguridad en redes, mencionando para cada una una técnica o solución para mitigar el riesgo:  
- Confidencialidad  
- Autenticación  
- No repudio  
- Integridad

| Ámbito           | Descripción                                      | Técnicas Mitigación         |
|------------------|--------------------------------------------------|-----------------------------|
| **Confidencialidad** | Evitar lectura no autorizada                  | Cifrado simétrico/asimétrico |
| **Autenticación**    | Verificar identidad                            | MFA, certificados           |
| **No repudio**       | Imposibilidad de negar una acción               | Firmas digitales            |
| **Integridad**       | Garantizar datos sin alteraciones no detectadas | MAC, hashes criptográficos  |

---

### Pregunta 18: Cifrado Simétrico vs Asimétrico
Realiza una comparación entre cifrado simétrico y asimétrico, abordando:  
- Número de claves requeridas  
- Velocidad y eficiencia  
- Ejemplos de algoritmos y aplicaciones típicas en cada caso

| Aspecto             | Simétrico                       | Asimétrico                   |
|---------------------|---------------------------------|------------------------------|
| Claves              | Una sola clave                  | Par (pública/privada)        |
| Velocidad           | Muy rápido                      | Más lento                    |
| Ejemplos            | AES, 3DES                       | RSA, ECC                     |
| Uso típico          | Cifrado de datos en tránsito    | Intercambio de claves, firma |

---

### Pregunta 19: Funcionamiento del Algoritmo RSA
**a)** Describe el proceso de generación de claves en RSA (selección de primos, cálculo de _n_ y _ϕ(n)_, determinación de _e_ y _d_).  
1. Elegir primos grandes p, q.  
2. Calcular n = p·q.  
3. Calcular φ(n) = (p–1)(q–1).  
4. Elegir e tal que 1 < e < φ(n) y gcd(e, φ(n))=1.  
5. Calcular d ≡ e^–1 mod φ(n).
   
**b)** Realiza un ejemplo numérico sencillo (por ejemplo, _p_ = 3, _q_ = 11, _e_ = 7) para demostrar el cifrado y descifrado de un mensaje (_M_ = 4).
- p=3, q=11 → n=33, φ=20  
- Elegimos e=7 (coprimo con 20)  
- d: 7·d ≡1 mod20 → d=3  
- Mensaje M=4  
- **Cifrado**: C = 4^7 mod33 = 16  
- **Descifrado**: M = 16^3 mod33 = 4  

---

### Pregunta 20: Firewalls, VPN e IPSec
**a)** Explica el funcionamiento de un firewall, mencionando al menos dos tipos (filtrado de paquetes y firewall de estado) y su importancia.  
- **Filtrado de paquetes**: inspecciona cabeceras IP/puerto.  
- **Firewall de estado**: además rastrea sesiones TCP.  
- **Importancia**: primera línea de defensa, bloquea tráfico no deseado.
  
**b)** Compara VPN e IPSec en términos de propósito, modo de operación y ejemplos de uso.

| Aspecto         | VPN (SSL/TLS)              | IPSec                            |
|-----------------|----------------------------|----------------------------------|
| Propósito       | Acceso remoto seguro       | Túneles site-to-site o host-to-host |
| Modo            | Basado en TLS sobre TCP    | AH/ESP sobre IP, transport/túnel |
| Ejemplo         | Cliente teletrabajo        | Conexión entre sedes corporativas |

---

### Pregunta 21: SSL/TLS y DNS Spoofing
**a)** Describe brevemente el funcionamiento del protocolo SSL/TLS y su importancia para la seguridad en la web (HTTPS).  
1. Negociación de versión y cifras.  
2. Intercambio de certificados X.509.  
3. Generación de secreto compartido.  
4. Cifrado simétrico de la sesión.  
> Asegura conf., integridad y autenticación en HTTPS.

**b)** Explica qué es el DNS Spoofing y cómo DNSSEC ayuda a proteger la integridad de las respuestas DNS.
- **Definición**: inserción de respuestas DNS falsas → redirige tráfico.  
- **DNSSEC**: firma digital de registros DNS, permite al resolver verificar la integridad y autenticidad de las respuestas.
