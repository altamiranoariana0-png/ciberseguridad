# 🔐 Laboratorios de Ciberseguridad

Repositorio correspondiente al desarrollo de laboratorios prácticos orientados a la seguridad informática y ciberseguridad ofensiva/defensiva.

---

# Introducción

La ciberseguridad se ha convertido en un elemento fundamental dentro de cualquier infraestructura tecnológica moderna. Actualmente, las organizaciones deben proteger información sensible frente a amenazas como ataques de fuerza bruta, robo de credenciales, manipulación de archivos y espionaje de tráfico de red.

El objetivo de estos laboratorios es comprender, de manera práctica, cómo funcionan distintas técnicas de ataque utilizadas por actores maliciosos y, posteriormente, aplicar mecanismos de defensa capaces de mitigar dichos riesgos.

Durante el desarrollo de los laboratorios se trabajó con tecnologías y herramientas ampliamente utilizadas en el área de seguridad informática, tales como:

- Criptografía asimétrica
- Funciones hash
- Firma digital
- SSH
- HTTPS/TLS
- MFA (Multi-Factor Authentication)
- Docker
- Hydra
- Wireshark

Los entornos fueron implementados utilizando contenedores Docker, permitiendo simular arquitecturas reales de ataque y defensa dentro de redes controladas y aisladas.

---

# Laboratorio 1 — Integridad y Firma Digital

## Descripción

En este laboratorio se trabajó con mecanismos criptográficos orientados a garantizar la integridad y autenticidad de archivos digitales.

Se utilizó hashing mediante SHA-256 para generar huellas digitales únicas de archivos y posteriormente se aplicó criptografía asimétrica para generar y verificar firmas digitales.

El laboratorio demuestra cómo una mínima modificación en un archivo altera completamente su hash, permitiendo detectar manipulaciones no autorizadas.

Además, mediante el uso de llaves públicas y privadas, se valida la autenticidad de los archivos y se garantiza el principio de no repudio.

---

## Conceptos trabajados

- Integridad de datos
- Hashing
- SHA-256
- Criptografía asimétrica
- Llave pública y privada
- Firma digital
- No repudio
- Autenticidad

---

## Actividades realizadas

- Creación de archivos de prueba
- Generación de hashes SHA-256
- Modificación de archivos para comprobar cambios de integridad
- Generación de llaves RSA
- Firma digital de archivos
- Verificación de firmas utilizando llave pública

---

## Objetivo específico

Demostrar cómo las funciones hash y las firmas digitales permiten proteger información frente a modificaciones maliciosas y validar la autenticidad de un archivo.

---

## Evidencias

<img src="img/lab1_hash" width="700">

---

# Laboratorio 2 — Ataque de Fuerza Bruta con Hydra + MFA

## Descripción

En este laboratorio se simuló un ataque de fuerza bruta sobre un servicio SSH utilizando la herramienta Hydra desde un entorno atacante basado en Kali Linux.

Inicialmente, el servidor víctima poseía autenticación únicamente mediante contraseña, permitiendo demostrar cómo el uso de claves débiles puede comprometer completamente un sistema.

Posteriormente, se implementó MFA (Multi-Factor Authentication) mediante Google Authenticator, agregando un segundo factor de autenticación dinámico basado en códigos temporales.

Finalmente, se repitió el ataque utilizando Hydra, evidenciando que, aunque la contraseña fuese descubierta, el atacante no podía autenticarse sin el segundo factor.

---

## Conceptos trabajados

- Fuerza bruta
- Ataque de diccionario
- SSH
- Hydra
- Google Authenticator
- Autenticación multifactor

---

## Actividades realizadas

- Creación de entorno atacante y víctima mediante Docker
- Configuración de servicio SSH
- Creación de usuarios vulnerables
- Creación de diccionario de contraseñas
- Ejecución de ataque Hydra
- Validación de acceso exitoso
- Configuración de MFA con Google Authenticator
- Integración de MFA con SSH
- Repetición del ataque y validación de mitigación

---

## Objetivo específico

Demostrar cómo los ataques automatizados pueden vulnerar contraseñas débiles y cómo la autenticación multifactor reduce significativamente el riesgo de compromiso.

---

## Evidencias

<img src="img/lab2_hydra" width="700">

---

# Laboratorio 3 — Intercepción de Tráfico: HTTP vs HTTPS

## Descripción

En este laboratorio se analizó el comportamiento del tráfico de red utilizando herramientas de sniffing para demostrar las diferencias de seguridad entre HTTP y HTTPS.

Inicialmente se implementó un servidor web utilizando HTTP, permitiendo observar cómo las credenciales enviadas mediante formularios web viajan en texto plano y pueden ser capturadas fácilmente por un atacante conectado a la red.

Posteriormente, se implementó HTTPS mediante certificados SSL/TLS, comprobando que el tráfico pasa a encontrarse cifrado, imposibilitando la lectura directa de las credenciales capturadas.

Finalmente, se trabajó con túneles SSH para encapsular tráfico inseguro dentro de canales cifrados.

---

## Conceptos trabajados

- Sniffing
- HTTP
- HTTPS
- TLS
- Tráfico en texto plano
- Cifrado en tránsito
- SSH Tunneling
- Seguridad de red

---

## Actividades realizadas

- Implementación de entorno mediante Docker
- Configuración de servidor web Apache
- Creación de formulario vulnerable
- Captura de tráfico con tcpdump y curl.
- Intercepción de credenciales HTTP
- Configuración de certificados SSL/TLS
- Implementación de HTTPS
- Comparación de tráfico HTTP y HTTPS
- Creación de túneles SSH

---

## Objetivo específico

Demostrar cómo el cifrado protege la confidencialidad de la información transmitida a través de redes y cómo protocolos inseguros exponen credenciales sensibles.

---

## Evidencias

<img src="img/lab3_http" width="700">


---

# Conclusión General

Los laboratorios permitieron comprender, de forma práctica, distintas problemáticas de seguridad informática relacionadas con integridad, autenticación y confidencialidad de la información.

A través de escenarios reales de ataque y defensa se logró evidenciar la importancia de:

- Utilizar mecanismos de cifrado
- Implementar autenticación multifactor
- Validar integridad de archivos
- Proteger credenciales en tránsito
- Aplicar buenas prácticas de seguridad

Además, el uso de Docker permitió construir entornos controlados y reproducibles para el análisis seguro de vulnerabilidades y mecanismos de mitigación.
