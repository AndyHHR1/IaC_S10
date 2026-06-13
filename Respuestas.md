### ¿Por qué necesitamos Loki además de Prometheus si ya tenemos /metrics?

- Porque /metrics y Prometheus solo te dan números y contadores (como el uso de CPU o cuantas llamadas fallaron). En cambio, con Loki guardas los logs reales para saber exactamente el contexto de qué pasó, cuándo y dónde cuando algo se rompe.

### ¿Qué ventaja aporta que las fuentes de datos de Grafana estén aprovisionadas como código y no creadas a mano?

- Que automatizas todo y te olvidas de configurar a mano. Cualquiera puede levantar el proyecto completo con un solo comando y ya le viene todo listo, sin errores de tipeo ni tener que estar copiando y pegando credenciales.

### El panel "CPU contenedor" y el panel "CPU host" pueden mostrar valores muy distintos. ¿Por qué? ¿Cuál usarías para alertar sobre una aplicación concreta?

- El CPU del host mide lo que consume todo el servidor físico con los demas procesos, mientras que el del contenedor solo mide el de tu app. Para alertar sobre una aplicación en específico usaria la del contenedor, porqué ahí ves el consumo real y aislado de ese servicio.

### ¿Qué diferencia hay entre el evaluation interval y el pending period de una alarma?

- El evaluation interval es cada cuánto tiempo el sistema revisa si se cumple la condición. El pending period es el tiempo que tiene que mantenerse activa esa condición para que recien se dispare la alarma y no te tire alertas falsas por un pico de un segundo.
