# 07. 🏪 Análisis de Expansión Retail

## 📊 Descripción
Dashboard estratégico desarrollado como prueba técnica para proceso de selección. El objetivo es identificar las 3 zonas óptimas para apertura de nuevas tiendas mediante análisis integrado de múltiples fuentes de datos.

## 🎯 Contexto del Proyecto
**Prueba técnica** con tiempo límite de 5 horas para posición de analista de datos. Se requirió integrar 7 fuentes de datos diferentes y generar recomendaciones basadas en evidencia.

## ⏱️ Información de Ejecución
- **Duración:** 3.5 horas efectivas
- **Fecha:** Noviembre 2024
- **Entregables:** Dashboard .PBIX + PDF exportado
- **Estado:** ✅ Completado

## 🛠️ Tecnologías Utilizadas
- **Power BI Desktop**
- **DAX** (Data Analysis Expressions)
- **Power Query** (ETL)
- **Modelo Estrella**
- **Visualización Interactiva**

## 📈 Características del Dashboard

### Página 1: Decisión de Expansión
![Página 1](screenshots/pagina1-decision.png)
- Score de expansión multivariable por zona
- Ranking interactivo con métricas clave
- Mapa geográfico con potencial comercial
- Filtro automático de zonas sin tiendas

### Página 2: Consumidor y Demanda
![Página 2](screenshots/pagina2-consumidor.png)
- Perfil de frecuencia de compra por zona
- Análisis de motivos de visita
- NPS (Net Promoter Score) promedio
- Comentarios de clientes filtrados

### Página 3: Competencia y Precios
![Página 3](screenshots/pagina3-competencia.png)
- Evolución de precios vs competencia
- Márgenes por categoría de producto
- Mapa de calor de stockouts
- Análisis competitivo por zona

## 🏗️ Arquitectura de Datos
Modelo Estrella con:
- Tabla Calendario (dimensión central)
- Socioeco_Zonas (dimensión principal)
- 6 tablas de hechos integradas
- Relaciones optimizadas para análisis cruzado

## 📁 Fuentes de Datos
Archivo	Filas	Descripción
Socioeco_Zonas.csv	42	Perfil demográfico y socioeconómico
Footfall_Zonas.csv	92,736	Tráfico peatonal por hora
Ventas_Tiendas.csv	16,560	Ventas internas por categoría
Precios_Competencia.csv	112,896	Precios de competencia
Encuesta_Consumidor.csv	4,200	Hábitos y satisfacción
Tiendas.csv	30	Tiendas existentes
Productos.csv	32	Catálogo de productos

## 🎨 Decisiones de Diseño Clave
Score Ponderado para decisión objetiva
Normalización de Métricas para comparación justa
Storytelling en 3 páginas con flujo lógico
Formato Condicional para insights rápidos
Filtros Inteligentes (excluir zonas con tiendas)
