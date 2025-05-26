#  Proyecto IoT: AQUALORA

Este proyecto tiene como propósito medir y monitorear en tiempo real la calidad del agua en una planta purificadora, mediante sensores integrados a microcontroladores con comunicación LoRa y envío de datos a través de MQTT.

##  Descripción General

El sistema se compone de sensores de **pH**, **TDS** y **temperatura/humedad** (DHT11), conectados a placas Heltec LoRa 32 para transmisión a larga distancia. Los datos son recolectados por una LilyGO T-SIM7070, enviados a un **broker MQTT** y visualizados en un **dashboard con Grafana**. Se contempla el uso de **Zabbix** para monitoreo adicional.

##  Estructura del Proyecto

- [Software](./software): Código fuente para los módulos emisor, receptor y transmisión celular.
- [Hardware](./hardware): Especificaciones y conexiones físicas de los componentes electrónicos.
- [Documentación](./documentación): Manuales, diseño técnico, instrucciones y descripciones del proyecto.
- [Diagramas](./diagramas): Diagramas lógicos, de flujo, topología y esquemáticos del hardware.

##  Tecnologías Utilizadas

**Lenguaje de Programación:**
- C++

**Frameworks / Librerías:**
- Arduino IDE
- TinyGSM (módem SIM7070)
- PubSubClient (MQTT)
- LoRa (comunicación inalámbrica)
- Adafruit SSD1306 y GFX (pantalla OLED)
- DHT (sensor temperatura y humedad)

**Herramientas:**
- Mosquitto (Broker MQTT)
- Grafana (visualización)
- Zabbix (monitoreo)

##  Módulos del Proyecto

### 1.  Módulo de Emisor (Heltec LoRa 32)
- Lee sensores: DHT11, TDS, pH
- Envía datos por LoRa

### 2.  Módulo Receptor (Heltec LoRa 32)
- Recibe y procesa datos del emisor
- Muestra datos en pantalla OLED

### 3.  Módulo Principal (LilyGO SIM7070)
- Envía datos al broker MQTT por red celular
- Administra la conexión y visualización remota

### 4.  Base de Datos y Dashboard
- Visualización en Grafana
- Almacenamiento MQTT en tiempo real

## 📈 Casos de Uso

- Monitoreo en tiempo real de calidad del agua
- Visualización remota mediante dashboard
- Alertas automáticas si los parámetros están fuera del rango normal

##  Instrucciones de Instalación

1. **Instalar Arduino IDE** y las siguientes librerías:
   - TinyGSM
   - PubSubClient
   - LoRa
   - DHT
   - Adafruit GFX / SSD1306

2. **Conectar Hardware** según el esquema del proyecto.

3. **Cargar el Código** a cada módulo:
   - Emisor, receptor y SIM7070.

4. **Configurar el Broker MQTT** (Mosquitto):
   - IP, puerto, usuario y contraseña.

5. **Visualizar datos** en Grafana:
   - Conecta el broker MQTT como fuente de datos.

## Limitaciones y Riesgos

- La precisión depende de la correcta calibración de sensores.
- Se requiere mantenimiento regular.
- Dependencia de la red celular.

## Mejoras Futuras

- Incorporar Zigbee o NB-IoT para mayor robustez.
- Sensores con mejor precisión y bajo mantenimiento.
- App móvil para monitoreo directo.

##  Contribuciones

¿Quieres contribuir? Sigue estos pasos:
- Reporta errores en [Issues](https://github.com/Marco22011538/AQUALORA)
- Haz un fork y crea un **Pull Request**
- Únete a las discusiones del proyecto

##  Licencia

Este proyecto se distribuye bajo la [Licencia MIT](./LICENSE).

---

Desarrollado por **Equipo AQUALORA** 
