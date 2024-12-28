# Web Log Analyzer and Anomaly Detector

Este proyecto consiste en un notebook de Jupyter que analiza archivos de log de acceso a un servidor web (en formato Apache Common Log Format) para obtener información valiosa y detectar posibles anomalías, como intentos de fuerza bruta y escaneos de vulnerabilidades.

## Descripción

El notebook realiza las siguientes tareas:

1. **Lectura y Parseo de Logs:** Lee un archivo de log línea por línea utilizando una expresión regular y lo convierte en un DataFrame de Pandas para facilitar el análisis.
2. **Limpieza y Conversión de Datos:** Limpia los datos y convierte las columnas relevantes a los tipos de datos correctos (fechas, enteros, etc.).
3. **Análisis Exploratorio:** Realiza un análisis exploratorio de los datos para obtener información general, incluyendo:
    *   IPs más frecuentes.
    *   Códigos de estado HTTP.
    *   URLs más visitadas.
    *   Tráfico a lo largo del tiempo (peticiones por hora).
    *   User-Agents más comunes.
    *   Referers más comunes.
4. **Detección de Anomalías:** Implementa algoritmos para detectar:
    *   **Picos de Tráfico:** Basados en la media más un múltiplo de la desviación estándar del número de peticiones por hora.
    *   **Intentos de Fuerza Bruta:** Basados en la cantidad de intentos de acceso fallidos (códigos de estado 4xx y 5xx) desde una misma IP en una ventana de tiempo determinada.
    *   **Escaneos de Vulnerabilidades:** Basados en la detección de patrones sospechosos en las URLs solicitadas y una alta proporción de códigos de estado 404.
5. **Investigación de IPs Sospechosas:** Proporciona funciones para obtener información adicional sobre las IPs detectadas como sospechosas, incluyendo:
    *   **Información WHOIS:** Utiliza el comando `whois` del sistema.
