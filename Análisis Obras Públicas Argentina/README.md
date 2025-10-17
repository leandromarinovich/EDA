# Análisis Exploratorio de Datos (EDA)

## Descripción

Este repositorio contiene el **Análisis Exploratorio de Datos (EDA)** realizado sobre el conjunto de datos de **Presupuesto y Ejecución de Obras Públicas del Ministerio de Obras Públicas de la República Argentina**.

El objetivo central de este EDA es **descubrir patrones**, **detectar anomalías**, y **verificar hipótesis** sobre la distribución del gasto y el avance de la obra pública a nivel nacional, utilizando resúmenes estadísticos y representaciones gráficas.

---

## Contenido del Repositorio

- `Analisis_Obras_Publicas.ipynb`: Notebook de **Análisis Exploratorio de Datos (EDA)** sobre el Presupuesto y Ejecución de Obras Públicas de Argentina.
- `data/`: Contiene los conjuntos de datos originales, como el archivo `Mapa de inversiones Argentina.csv` y el *dataset* limpio resultante.
- `README.md`: Este archivo, que proporciona una descripción general y un resumen analítico del proyecto.

---

## Observaciones Críticas y Oportunidades de Mejora

El análisis inicial revela interesantes patrones en la asignación y ejecución de la obra pública, pero también señala puntos de fricción importantes para el desarrollo de proyectos y la transparencia.

### 1. Desbalance Crítico entre Avance Financiero y Físico (Observación Alta)

El hallazgo más relevante es la **notable brecha entre el dinero pagado y la obra realmente ejecutada** (Avance Financiero vs. Avance Físico).

* **Situación Detectada:** En la mayoría de los rangos de avance (0-80%), el avance financiero es **superior** al físico. Más aún, un gran número de obras se encuentran en el rango **80-100% de avance financiero** (completamente pagadas), pero su **avance físico aún no alcanza el 100%**. Esto significa que **el Estado ha pagado por obras que aún no están terminadas**.
* **Impacto y Fundamento:** Esta anomalía (pagar antes de recibir) es un indicador de **ineficiencia en la gestión financiera y de proyectos**. Puede implicar riesgos de sobrecostos, demoras en la entrega de infraestructura vital o, en el peor de los casos, la culminación de obras con fondos públicos ya desembolsados.
* **Alternativa para Optimizarlo:** Se recomienda el diseño de un **sistema de *Escrow* o retención de pagos** donde un porcentaje significativo del monto final sea liberado únicamente tras la certificación del **100% de la ejecución física**. Esto alinearía el incentivo financiero con el resultado operativo.

### 2. Baja Prioridad a Sectores Sociales Clave (Observación Media)

Al analizar la distribución por sector, se observa una asignación desproporcionada.

* **Situación Detectada:**
    * El sector **"AGUA Y CLOACA"** es el más numeroso en cantidad de proyectos, pero su costo promedio es de los más bajos.
    * Sectores de alto impacto social como **"VIVIENDA / HÁBITAT"**, **"EDUCACIÓN"** y **"SALUD"** reciben una **escasa asignación** tanto en número de proyectos como en monto total, a pesar de ser pilares del desarrollo.
    * **"RECURSOS HÍDRICOS"** concentra una **inversión monetaria considerable**.
* **Impacto y Fundamento:** La baja inversión relativa en vivienda y educación puede ralentizar el cierre de brechas sociales fundamentales. El foco parece estar en infraestructura de servicio (agua/cloacas/viales) y grandes obras hídricas, lo cual, si bien es necesario, merece un **análisis de la rentabilidad social** de los proyectos desatendidos.
* **Alternativa para Optimizarlo:** Proponer un **análisis de *Trade-off*** que pondere el costo-beneficio de los proyectos con bajo costo unitario (como cloacas) versus el impacto de proyectos sociales (vivienda/salud). Esto puede justificar una **reorientación presupuestaria** hacia áreas con mayor rezago de infraestructura social.

### 3. Inconsistencia en la Serie Histórica de Datos (Observación Baja)

El análisis temporal revela un desafío inicial de calidad de datos.

* **Situación Detectada:** El conteo de obras por `anio_inicio` muestra una **gran dispersión y datos faltantes** en la serie histórica (especialmente entre 2008 y 2015). Esto forzó a utilizar el `anio_fin` para obtener una visión más coherente de la actividad reciente.
* **Impacto y Fundamento:** La falta de una serie histórica robusta y completa dificulta la capacidad de realizar **análisis comparativos de largo plazo** o **predecir patrones temporales** de manera precisa.
* **Alternativa para Optimizarlo:** A futuro, se debe indagar sobre la **metodología de carga de datos** para los años iniciales. Si la información no se puede recuperar, se deben aplicar técnicas de **imputación de series de tiempo** o delimitar claramente el *scope* del análisis solo a períodos con datos completos (post-2016) para no sesgar las conclusiones.

---

## Requisitos

Para ejecutar los *notebooks* y reproducir el análisis, se requieren las siguientes dependencias:

* Python 3.x
* Jupyter Notebook o JupyterLab
* Librerías clave: `pandas`, `numpy`, `matplotlib` y `seaborn`.

---

## Proyección a Futuro

El proyecto está en una fase inicial de EDA. La matriz de correlación generada al final ya indica una ruta clara para la **siguiente etapa: el análisis predictivo**. Variables como el `monto_total`, `duracion_dias` y los indicadores de `avance` son excelentes candidatos para entrenar algoritmos de Machine Learning y **predecir desviaciones presupuestarias o retrasos**.

---

## Contribuciones

Las contribuciones son bienvenidas. Siéntete libre de abrir un *issue* para reportar problemas o enviar un *pull request* con mejoras al código o al análisis.

---

## Contacto

Si tienes alguna pregunta, no dudes en ponerte en contacto:

* **Nombre:** Leandro Marinovich
* **Email:** leandromarinovich@gmail.com

***
