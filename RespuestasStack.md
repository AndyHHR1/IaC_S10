### Prometheus:

- Recolecta métricas mediante Pull desde `/metrics` de las apps y de exporters como node-exporter o cAdvisor. Las guarda en series temporales segun la retención configurada.

### Loki:

- Almacena logs en formato JSON de forma eficiente porqué no indexa todo el texto, sino solo por etiquetas como tier o container, haciendo las búsquedas más rápidas.

### Grafana Alloy:

- Es el agente que descubre los contenedores usando el Docker socket, parsea los logs en JSON y los manda a Loki bien etiquetados por servicio.

### Grafana:

- La plataforma de visualisación donde conectas Prometheus para ver métricas y Loki para logs, permitiéndote armar dashboards y configurar alertas con umbrales.

### node-exporter:

- Exporta métricas de hardware del sistema operativo (CPU, RAM, disco del host) para que Prometheus las scrapeé y puedas monitorear la infraestructura.

### cAdvisor:

- Monitorea los recursos consumidos a nivel de contenedores (CPU y memoria de Docker) y expone esas métricas para que Prometheus de la observabilidad de las apps.

### Backend/Frontend:

- Son las apps en Node.js instrumentadas con `prom-client`. Exponen su propio `/metrics` y tiran logs estructurados que luego recolecta Alloy.
