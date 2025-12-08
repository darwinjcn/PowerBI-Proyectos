# 07. 🏪 Análisis de Expansión Retail

## 📊 Descripción
Dashboard estratégico desarrollado como prueba técnica para proceso de selección. El objetivo es identificar las 3 zonas óptimas para apertura de nuevas tiendas mediante análisis integrado de múltiples fuentes de datos.

## 🎯 Contexto del Proyecto
**Prueba técnica** con tiempo límite de 5 horas para posición de analista de datos. Se requirió integrar 7 fuentes de datos diferentes y generar recomendaciones basadas en evidencia.

## ⏱️ Información de Ejecución
- **Duración:** 3.5 horas efectivas
- **Fecha:** Noviembre 2025
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
- Archivo	Filas	Descripción
- Socioeco_Zonas.csv	42	Perfil demográfico y socioeconómico
- Footfall_Zonas.csv	92,736	Tráfico peatonal por hora
- Ventas_Tiendas.csv	16,560	Ventas internas por categoría
- Precios_Competencia.csv	112,896	Precios de competencia
- Encuesta_Consumidor.csv	4,200	Hábitos y satisfacción
- Tiendas.csv	30	Tiendas existentes
- Productos.csv	32	Catálogo de productos

## 🎨 Decisiones de Diseño Clave
- Score Ponderado para decisión objetiva
- Normalización de Métricas para comparación justa
- Storytelling en 3 páginas con flujo lógico
- Formato Condicional para insights rápidos
- Filtros Inteligentes (excluir zonas con tiendas)

## 🔍 Insights Generados
Top 3 Zonas Recomendadas:
- SAN-2 (San Salvador) - Mayor población, competencia moderada
- SAN-4 (San Salvador) - Baja competencia, ingresos estables
- SAN-1 (San Salvador) - Alto ingreso, zona comercial consolidada
Hallazgos Clave:
- Stockout crítico en Cuidado Personal (13.5%)
- Oportunidad en productos saludables (demanda insatisfecha)
- NPS promedio de 6.8/10 (base para mejora)

## 🚀 Cómo Ejecutar
- Descargar dashboard-retail.pbix
- Abrir con Power BI Desktop
- Los datos de muestra están incluidos
- Interactuar con filtros y segmentaciones

## 📚 Aprendizajes del Proyecto
- Integración de múltiples fuentes en tiempo limitado
- Creación de scores estratégicos multivariable
- Storytelling con datos para decisiones ejecutivas
- Optimización de modelos para análisis retail

## 📂 Estructura del Proyecto
07_Expansion_Retail/
├── dashboard-retail.pbix          # Archivo principal Power BI
├── README.md                      # Esta documentación
├── screenshots/                   # Imágenes del dashboard
│   ├── pagina1-decision.png
│   ├── pagina2-consumidor.png
│   └── pagina3-competencia.png
├── data/                          # Información de datos
│   ├── sample/                    # Datos de ejemplo
│   └── data-dictionary.md         # Diccionario de datos
└── analysis/                      # Análisis adicional
    └── insights.md                # Insights estratégicos

## 🏗️ Modelo de Datos
ARQUITECTURA ESTRELLA:
┌─────────────────┐
│   CALENDARIO    │ ← Dimensión central
└─────────────────┘
        ↑
┌─────────────────┐
│  SOCIOECO_ZONAS │ ← Dimensión principal (42 zonas)
└─────────────────┘
        ↑
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│FOOTFALL_ZONAS   │  │VENTAS_TIENDAS   │  │PRECIOS_COMPETENC│
│(92,736 filas)   │  │(16,560 filas)   │  │(112,896 filas)  │
└─────────────────┘  └─────────────────┘  └─────────────────┘
        ↑                   ↑                      ↑
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│   TIENDAS       │  │   PRODUCTOS     │  │ ENCUESTA_CONSUM │
│  (30 tiendas)   │  │  (32 productos) │  │  (4,200 ent.)   │
└─────────────────┘  └─────────────────┘  └─────────────────┘


## 📊 Medidas DAX Principales
Score Expansion = 
VAR PoblacionNorm = DIVIDE([Poblacion 10min], 100000, 0)
VAR FootfallNorm = DIVIDE([Footfall Promedio Diario], 1000, 0)
VAR IngresoNorm = DIVIDE([Ingreso Promedio Zona], 20000, 0)
VAR CompetidoresNorm = [Competidores por Zona]

RETURN
(PoblacionNorm * 0.3) +      // 30% Población
(FootfallNorm * 0.25) +      // 25% Tráfico peatonal
(IngresoNorm * 0.2) -        // 20% Poder adquisitivo
(CompetidoresNorm * 0.25)    // 25% Competencia (negativo)

# Métricas Clave Desarrolladas
// 1. Demográficas
Poblacion 10min = SUM(Socioeco_Zonas[Poblacion_10min])
Ingreso Promedio Zona = AVERAGE(Socioeco_Zonas[Ingreso_Prom_Q])

// 2. Comportamiento
Footfall Promedio Diario = 
CALCULATE(
    AVERAGE(Footfall_Zonas[Footfall_Total]),
    ALLEXCEPT(Footfall_Zonas, Footfall_Zonas[ZonaID])
)

// 3. Competencia
Competidores por Zona = AVERAGE(Socioeco_Zonas[Competidores_Dentro_2km])

// 4. Consumidor
NPS Promedio = AVERAGE(Encuesta_Consumidor[NPS_0a10])
Satisfaccion Promedio = AVERAGE(Encuesta_Consumidor[Satisfaccion_1a5])

// 5. Ventas
Ventas Totales = SUM(Ventas_Tiendas[Ventas_Q])
Margen Promedio % = AVERAGE(Ventas_Tiendas[Margen_%])
Stockout Promedio % = AVERAGE(Ventas_Tiendas[Stockout_%])
