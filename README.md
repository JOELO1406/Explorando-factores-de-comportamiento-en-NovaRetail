# 🛒 Exploración de Factores de Comportamiento en NovaRetail+
<img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/8990acea-f64f-4469-b8b5-6dd6d256608d" />

> **Proyecto de Análisis Correlacional y Exploratorio de Datos (EDA) Proyecto TripleTen.**  
> **Área:** Crecimiento y Retención | **Empresa:** NovaRetail+ (E-Commerce Latinoamérica)
> 
> **Autor:** Joel Serrato Guzman.  

---

## 📌 1. Visión General del Proyecto

**NovaRetail+** es una plataforma de comercio electrónico líder en Latinoamérica con millones de usuarios activos. Al cierre de 2024, el equipo de **Crecimiento y Retención** impulsó este estudio con el objetivo de responder a la pregunta estratégica del negocio:

> **¿Qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado?**

### ⚠️ Principio Clave del Análisis
Este estudio es de carácter **correlacional y exploratorio**.  
* **Recordatorio fundamental:** **Correlación no implica causalidad.** La presencia de una asociación estadística entre el comportamiento del usuario y sus ingresos no garantiza una relación causa-efecto directa sin experimentos controlados (A/B testing).

---

## 📊 2. Estructura y Limpieza del Dataset

El conjunto de datos comprende **15,000 registros** de usuarios activos y **12 variables**, sin presencia de valores nulos (100% de completitud).

| Columna | Tipo Original | Tipo Optimizado | Descripción |
| :--- | :--- | :--- | :--- |
| `id_cliente` | `object` | `object` | Identificador único del usuario (`CL-100000`). |
| `edad` | `float64` | `int64` | Edad del usuario (Rango: 18 - 75 años, Media: 38.2). |
| `nivel_ingreso` | `float64` | `float64` | Ingreso anual estimado del cliente ($8,000 - $74,790). |
| `visitas_mes` | `int64` | `int64` | Frecuencia mensual de visitas a la app/sitio web. |
| `compras_mes` | `int64` | `int64` | Número de compras mensuales concretadas. |
| `gasto_publicidad_dirigida` | `float64` | `float64` | Inversión en publicidad dirigida asignada al cliente. |
| `satisfaccion` | `float64` | `float64` | Nivel de satisfacción medido en escala Likert (1 a 5). |
| `miembro_premium` | `int64` | `int64` (Binaria) | Suscripción activa Premium (1) o Estándar (0). |
| `abandono` | `int64` | `int64` (Binaria) | Indicador de deserción/churn (1) o Retenido (0). |
| `tipo_dispositivo` | `object` | `category` | Dispositivo de acceso principal (`móvil`, `escritorio`, `tablet`). |
| `region` | `object` | `category` | Región geográfica (`norte`, `sur`, `este`, `oeste`). |
| `ingreso_anual` | `float64` | `float64` | **Métrica Objetivo:** Ingreso generado para la empresa. |

---

## 🔍 3. Hallazgos y Diagnóstico Descriptivo

### 📈 Comportamiento del Consumidor
* **Distribución de Ingresos (`ingreso_anual`):** Presenta una media de **$36.59** y una mediana de **$30.70** con alta dispersión ($\sigma = 34.48$, máx: $244.69$). Más del 25% de los clientes registran $0 en ingresos anuales, lo que coincide directamente con los usuarios que no concretan compras mensuales (`compras_mes = 0`).
* **Suscripción Premium (`miembro_premium`):** Adopción del **13.93%** (2,089 usuarios). Representa un nicho de alto valor potencial para estrategias de upsell.
* **Tasa de Churn (`abandono`):** Tasa de deserción del **15.07%** (2,261 usuarios) frente a un 84.93% de retención.
* **Plataforma Predilecta (`tipo_dispositivo`):** Predominio absoluto del canal **Móvil (65.45%)**, seguido de Escritorio (24.80%) y Tablet (9.75%).
* **Cobertura Geográfica (`region`):** Balanceada entre las 4 zonas principales: Norte (29.30%), Oeste (25.40%), Sur (24.84%) y Este (20.46%).

---

## 🧪 4. Metodología Estadística y Supuestos

Para evaluar las asociaciones entre el comportamiento y el ingreso anual, se aplicaron coeficientes específicos según el tipo de variable:

1. **Coeficiente de Pearson ($r$):** Evaluó linealidad entre variables continuas y cuantitativas.
2. **Coeficiente de Spearman ($
ho$):** Evaluó relaciones monótonas y distribuciones no normales.
3. **Correlación Punto Biserial ($r_{pb}$):** Midió la relación entre variables continuas y binarias (`miembro_premium`, `abandono`).
4. **V de Cramér ($V$):** Evaluó el grado de asociación entre variables categóricas nominales (`tipo_dispositivo`, `region`).

---

## 💡 5. Recomendaciones de Crecimiento & Retención

1. **Estrategia Mobile-First:** Dado que el 65.45% de los usuarios navega vía dispositivos móviles, las campañas de retención y la optimización de UX/UI deben priorizarse en la app móvil.
2. **Activación de Usuarios Inactivos:** Convertir al grupo de usuarios con 0 compras mensuales (y 0 ingreso generado) mediante promociones grupales o retargeting de primera compra.
3. **Fidelización Premium:** Diseñar programas de lealtad específicos para expandir la base Premium actual del 13.93%, reduciendo a su vez el riesgo de churn.

---

## 🛠️ Tecnologías Utilizadas

* **Lenguaje:** Python 3.x
* **Procesamiento de Datos:** `pandas`, `numpy`
* **Visualización:** `seaborn`, `matplotlib`
* **Análisis Estadístico:** `scipy.stats` (Chi-cuadrado, Point Biserial)

---

## 📁 Estructura del Repositorio

```text
├── datasets/
│   └── novaretail_comportamiento_clientes_2024.csv
├── notebooks/
│   └── Proyecto_7_Explorando_factores_comportamiento_NovaRetail.ipynb
├── README.md
└── requirements.txt
```

## 🛠️ Proyecto Elaborado por Ing. Joel Serrato Guzmán.
