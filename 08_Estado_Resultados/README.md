# 📊 08. Dashboard de Estado de Resultados (P&L - 2025)

## 📝 Objetivo del Proyecto
Este dashboard financiero tiene como objetivo visualizar y analizar el **Estado de Resultados** de una organización de manera dinámica. Permite el control de métricas críticas de rentabilidad, análisis de variaciones mensuales y el cálculo de puntos de equilibrio, facilitando la interpretación de la salud financiera.

> **Nota:** Este proyecto es una adaptación propia basada en el tutorial de **Visual Data**, ajustando la data original (2023) al contexto del año **2025**.

---

## ✨ Visualización del Dashboard

El diseño está optimizado para mostrar KPIs principales en la parte superior y un análisis detallado de la evolución de costos y ventas en el cuerpo principal.

> **Vista General del Estado de Resultados**
> ![Dashboard de Estado de Resultados](imagenes/dashboard_principal.png)

---

## 🔍 Aspectos Técnicos y Habilidades

### 📚 Créditos y Referencias
* **Autor Original:** [Visual Data](https://www.youtube.com/@visualdata_oficial)
* **Video Tutorial:** [Crea un Genial Dashboard de Estado de Resultados](https://www.youtube.com/watch?v=14BhMkcZPR4)

### 📈 Análisis Vertical y Variaciones
El proyecto destaca por la implementación de:
* **Análisis Vertical:** Determinación del peso porcentual de cada cuenta sobre las Ventas Netas.
* **Variaciones Mensuales:** Uso de funciones de inteligencia de tiempo para comparar el rendimiento contra el periodo anterior.

### 🛠️ Fórmulas DAX Destacadas
Se crearon medidas avanzadas con lógica `VAR/RETURN` y filtros específicos por `Id-Cuenta`:

| Métrica | Descripción |
| :--- | :--- |
| **Utilidad Neta** | Resultado final tras deducir costos, gastos e impuestos. |
| **Impuestos** | Calculado sobre una tasa del **34%** (Referencia ISLR Venezuela). |
| **Punto de Equilibrio** | Determina el nivel de ventas necesario para cubrir los gastos fijos. |
| **% Variación** | Lógica de `PREVIOUSMONTH` para análisis de tendencias. |

---

## 🔗 Enlaces
* [Archivo Power BI (PBIX)](./Dashboard-Estado-de-Resultados-2025.pbix)
