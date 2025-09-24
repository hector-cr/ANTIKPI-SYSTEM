# Sistema de Detección y Reportes Automáticos de KPIs

## Descripción del Proyecto
Este proyecto implementa un sistema en la nube para **monitoreo automático de KPIs (Indicadores Clave de Desempeño)** y la **generación de reportes en PDF** de manera programada.  
El objetivo es reducir el esfuerzo manual en la supervisión de métricas, mejorar la toma de decisiones en tiempo real y facilitar la entrega de resultados a la gerencia mediante reportes claros y accesibles.

  - Firestore (base de datos en tiempo real)  
  - Hosting (despliegue del sistema)  
- Librerías para generación de **PDF**  
- Logs automáticos para trazabilidad  

## Historias de Usuario Implementadas

### HU-001: Reportes Automáticos
**Como administrador quiero generar reportes automáticos en PDF, para entregar resultados con mayor eficacia a gerencia.**  

**Criterios de Aceptación:**
- Reportes programables (diario / semanal / mensual).  
- Generación en formato PDF con fecha.  
- Almacenamiento en la nube con enlace seguro.  
- Registro de cada generación en bitácora.  
- Manejo de errores con descarga local y log de incidentes.  

## Funcionalidades Clave
- **Reportes en PDF** programables y almacenados en la nube.  
- **Alertas en tiempo real** cuando un KPI cruza umbrales definidos.  
- **Dashboard interactivo** con KPIs filtrables por fechas y áreas.  
- **Bitácora de eventos** (logs de reportes, modificaciones y auditoría).  
- **Seguridad y roles de acceso** diferenciados.  

## Instalación 
1. Clonar el repositorio.  
2. Instalar dependencias:  
   ```bash
   npm install
