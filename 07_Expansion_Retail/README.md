# 🏪 Proyecto 07: Análisis de Expansión Retail

## 📊 Descripción
Dashboard estratégico desarrollado como **prueba técnica** para un proceso de selección.  
Objetivo: **identificar las 3 zonas óptimas para apertura de nuevas tiendas** mediante análisis integrado de múltiples fuentes de datos.

---

## 🎯 Contexto
- **Tipo:** Prueba técnica (tiempo límite: 5 horas)  
- **Duración real:** 3.5 horas efectivas  
- **Fecha:** Noviembre 2025  
- **Entregables:** Dashboard `.pbix` + PDF exportado  
- **Estado:** ✅ Completado  

---

## 🛠️ Tecnologías
- Power BI Desktop  
- DAX (Data Analysis Expressions)  
- Power Query (ETL)  
- Modelo Estrella  
- Visualización Interactiva  

---

## 📈 Características del Dashboard

### Página 1: Decisión de Expansión
![Página 1](imagenes/pagina1-decision.png)
- Score multivariable por zona  
- Ranking interactivo con métricas clave  
- Mapa geográfico con potencial comercial  
- Filtro automático de zonas sin tiendas  

### Página 2: Consumidor y Demanda
![Página 2](imagenes/pagina2-consumidor.png)
- Perfil de frecuencia de compra  
- Motivos de visita  
- NPS promedio  
- Comentarios filtrados de clientes  

### Página 3: Competencia y Precios
![Página 3](imagenes/pagina3-competencia.png)
- Evolución de precios vs competencia  
- Márgenes por categoría  
- Mapa de calor de stockouts  
- Análisis competitivo por zona  

---

## 🏗️ Arquitectura de Datos
Modelo Estrella con:
- **Dimensiones:** Calendario (central), Socioeco_Zonas (principal)  
- **Hechos:** Footfall, Ventas, Precios, Encuestas, Tiendas, Productos  
- Relaciones optimizadas para análisis cruzado  

---

## 📁 Fuentes de Datos

| Archivo                | Filas   | Descripción                          |
|-------------------------|---------|--------------------------------------|
| Socioeco_Zonas.csv      | 42      | Perfil demográfico y socioeconómico  |
| Footfall_Zonas.csv      | 92,736  | Tráfico peatonal por hora            |
| Ventas_Tiendas.csv      | 16,560  | Ventas internas por categoría        |
| Precios_Competencia.csv | 112,896 | Precios de competencia               |
| Encuesta_Consumidor.csv | 4,200   | Hábitos y satisfacción               |
| Tiendas.csv             | 30      | Tiendas existentes                   |
| Productos.csv           | 32      | Catálogo de productos                |

---

## 🎨 Decisiones de Diseño
- Score ponderado para decisión objetiva  
- Normalización de métricas para comparación justa  
- Storytelling en 3 páginas con flujo lógico  
- Formato condicional para insights rápidos  
- Filtros inteligentes (excluir zonas con tiendas)  

---

## 🔍 Insights Clave
**Top 3 zonas recomendadas:**
1. **SAN-2 (San Salvador):** Mayor población, competencia moderada  
2. **SAN-4 (San Salvador):** Baja competencia, ingresos estables  
3. **SAN-1 (San Salvador):** Alto ingreso, zona consolidada  

**Hallazgos adicionales:**
- Stockout crítico en Cuidado Personal (13.5%)  
- Oportunidad en productos saludables (demanda insatisfecha)  
- NPS promedio: 6.8/10 (área de mejora)  

---

## 🚀 Ejecución
1. Descargar `dashboard-retail.pbix`  
2. Abrir en **Power BI Desktop**  
3. Los datos de muestra están incluidos  
4. Explorar con filtros y segmentaciones  

---

## 📚 Aprendizajes
- Integración de múltiples fuentes en tiempo limitado  
- Creación de scores estratégicos multivariable  
- Storytelling con datos para decisiones ejecutivas  
- Optimización de modelos para análisis retail  

---

## 📂 Estructura del Proyecto
