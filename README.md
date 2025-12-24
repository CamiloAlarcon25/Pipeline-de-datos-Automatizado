# Pipeline de Datos Automatizado: Dashboard de Ventas y Utilidades

## 1. Contexto y Objetivos

El objetivo de este proyecto fue diseñar e implementar un ecosistema de datos integrado para el monitoreo de ventas, costos y utilidades de una empresa con múltiples sucursales. El enfoque principal fue la automatización del flujo de información, eliminando procesos manuales y asegurando la integridad de los datos desde su generación hasta su visualización.

## 2. Arquitectura del Proyecto (Tecnologías)

Herramientas:

Generación y ETL	Python (Pandas):	Script automatizado para la inserción de nuevos registros (sucursales, productos, ventas) evitando duplicados.

Almacenamiento	MySQL:	Base de datos relacional robusta para centralizar la información operativa.

Validación	SQL:	Consultas avanzadas para auditoría de datos, cálculo de utilidades y top de ventas antes de la visualización.

Visualización	Power BI:	Conexión directa a SQL para la creación de un Dashboard ejecutivo interactivo.

## 3. Desarrollo Técnico
### A. Gestión de Base de Datos (SQL)
Se diseñó un esquema relacional optimizado en MySQL (ventas_costos.sql) que incluye tablas de sucursales, productos, ventas y costos. Se utilizaron llaves primarias y foráneas para garantizar la coherencia de la información. Además, se crearon scripts de revisión (revisión_datos.sql) para calcular métricas clave como la Utilidad por Sucursal directamente en el motor de base de datos.
### B. Automatización con Python (Pipeline ETL)
Para simular un entorno de producción real, se desarrolló un script en Python (insertar_nuevos_datos.py) que:

•	Carga datos desde archivos CSV.

•	Conecta con la base de datos MySQL.

•	Utiliza la lógica ON DUPLICATE KEY UPDATE para actualizar registros existentes o insertar nuevos, asegurando que el pipeline pueda ejecutarse repetidamente sin errores.

### C. Business Intelligence (Power BI)
El Dashboard (Proyecto_BI.pbix) se conecta directamente a la instancia de SQL, permitiendo:

•	Análisis de Rentabilidad: Comparación visual entre Ingresos y Costos para determinar el margen de utilidad.

•	Segmentación Dinámica: Filtros por región, ciudad y gerente de sucursal.

•	Ranking de Rendimiento: Identificación automática de los 5 productos más vendidos y las sucursales más rentables.

<img width="400" height="400" alt="Gemini_Generated_Image_sp66uisp66uisp66" src="https://github.com/user-attachments/assets/d133e934-7e90-4af7-9461-b821e5d512ec" /> 

Figura 1: Diagrama de Flujo

## 4. Resultados y Valor Agregado

La implementación de este flujo de trabajo permite a la organización:

•	Reducir tiempos operativos: La carga de datos que antes podía ser manual ahora se realiza mediante un script.

•	Escalabilidad: El sistema está preparado para recibir miles de registros sin perder rendimiento.

•	Veracidad: Al centralizar los datos en SQL y validarlos con scripts, se eliminan las discrepancias comunes de los reportes en archivos Excel sueltos.

Enlace del Dashboard en formato PDF: https://github.com/CamiloAlarcon25/Pipeline-de-datos-Automatizado/blob/main/Proyecto_BI.pdf
