# Proyecto: Configuración y Pruebas de un Servidor IP PBX con Asterisk

Este proyecto presenta la instalación, configuración y pruebas de un servidor IP PBX basado en **Asterisk**, implementado en un entorno Linux. El objetivo principal es explorar la gestión de llamadas VoIP, redireccionamiento de llamadas y configuración de buzones de voz mediante la edición de archivos de configuración y análisis de tráfico de red.

## 🛠️ Instalación y Configuración

1. **Instalación de Asterisk en Linux**:
   - Configuración de un servidor IP PBX utilizando máquinas virtuales.
   - Creación y ajuste de los archivos de configuración `sip.conf`, `extensions.conf` y `voicemail.conf`.

2. **Configuración de Anexos**:
   - **7001**: Configuración básica sin buzón de voz ni redireccionamiento.
   - **7002**: Redireccionamiento automático al anexo 7003 después de 10 segundos de no respuesta.
   - **7003**: Configuración de buzón de voz para almacenar mensajes cuando no se responde una llamada.

3. **Comandos de Consola**:
   - Validación de registros: `sip show peers`, `sip show channels`, entre otros.

## 📊 Análisis de Experiencias

### Experiencia 1: Llamada entre Softphones
- **Escenario**: Softphone 1 llama a Softphone 2, este contesta y finaliza la llamada.
- **Resultados**:
  - Reproducción y análisis del flujo RTP.
  - Visualización de los flujos SIP en Wireshark, incluyendo la negociación del codec **g711U**.
  - Verificación de calidad de llamada con tasa de transferencia cercana a 64 kbps.

### Experiencia 2: Redireccionamiento Automático
- **Escenario**: Softphone 1 llama a Softphone 2, que no contesta, y la llamada es redirigida al Softphone 3.
- **Resultados**:
  - Análisis de los flujos SIP y RTP de dos llamadas consecutivas (7001 → 7002 y 7001 → 7003).
  - Identificación de congestión de red mediante estadísticas de **Packet Loss** y **Max Delta**.

### Experiencia 3: Llamada al Buzón de Voz
- **Escenario**: Softphone 1 llama a Softphone 2, este no contesta y se redirige al buzón de voz configurado en el Softphone 3.
- **Resultados**:
  - Registro del mensaje en el buzón de voz.
  - Reproducción de audio del mensaje almacenado.
  - Análisis detallado del flujo SIP y RTP en Wireshark.

## 📈 Herramientas Utilizadas
- **Asterisk**: Servidor IP PBX para configuración y manejo de llamadas.
- **Wireshark**: Análisis de tráfico de red y visualización de flujos SIP y RTP.
- **Softphones**: Clientes para realizar y recibir llamadas VoIP.

## 🧾 Conclusiones
- El proyecto demostró cómo configurar y administrar un servidor IP PBX para gestionar llamadas VoIP, redireccionamientos y buzones de voz.
- Se verificaron los flujos SIP y estadísticas RTP, mostrando el proceso de negociación de codecs, redireccionamiento y almacenamiento de mensajes.
- Las experiencias permitieron profundizar en el análisis de calidad de llamadas, detectando limitaciones como congestión de red y pérdida de paquetes.

## 📁 Archivos Adjuntos
- Configuración de archivos (`sip.conf`, `extensions.conf`, `voicemail.conf`).
- Capturas de pantalla y análisis de flujos SIP/RTP.
- Videos de las experiencias realizadas.

---

¡Explora este repositorio para conocer más sobre el funcionamiento de un servidor IP PBX con Asterisk!
