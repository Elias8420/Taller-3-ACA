# Documentación del Ecosistema Backend de Buhos-App

Bienvenido al portal técnico de **Buhos-App**, la solución integral diseñada para la automatización, control de aforos y reserva de asientos en tiempo real para las aulas del campus universitario. 

Este backend provee una interfaz robusta de servicios web para conectar las aplicaciones cliente (web y móvil) con las capas de lógica de negocio y persistencia de datos.

!!! note "Lineamientos de Integración"
    Todos los servicios expuestos en este entorno operan de manera síncrona bajo el protocolo HTTP/1.1 y transfieren información estrictamente en formato JSON utilizando codificación UTF-8.

## Audiencia Destinataria

Este compendio de guías está optimizado para:
* **Desarrolladores Frontend:** Consumo ágil de servicios y control de respuestas estandarizadas.
* **Administradores de Sistemas:** Despliegue de infraestructura mediante contenedores aislados.
* **Equipo de QA:** Validación de contratos de datos y códigos de estado HTTP esperados.

## Acceso Rápido al Catálogo

Para comenzar con las pruebas de integración y verificar la estructura interna de los controladores de persistencia, procede directamente a explorar la [Servicios de Aulas](endpoints.md). Encontrarás ejemplos interactivos y la matriz de parámetros obligatorios de consulta.