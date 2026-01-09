

# Trabajo de Consulta: EDA, Limpieza de Datos y Herramientas de IA

## Objetivo
Investigar y comprender los conceptos fundamentales del Análisis Exploratorio de Datos (EDA), con un enfoque especial en las fases de limpieza de datos y la integración de herramientas de Inteligencia Artificial para optimizar este proceso.

## Indicaciones
Responde a los siguientes puntos de manera clara y fundamentada. Utiliza ejemplos prácticos y referencias para apoyar tus respuestas.

---

## Aspectos a Investigar y Desarrollar

### 1. Definición del Análisis Exploratorio de Datos (EDA)

#### ¿Qué es el EDA?
El **Análisis Exploratorio de Datos (EDA)** es un enfoque fundamental en la ciencia de datos que consiste en investigar, visualizar y resumir las características principales de un conjunto de datos antes de aplicar técnicas de modelado más complejas. Es esencialmente el proceso de "conocer" los datos mediante técnicas estadísticas y visualizaciones.

El término fue popularizado por el estadístico **John Tukey** en la década de 1970, quien enfatizó la importancia de explorar los datos sin suposiciones previas rígidas, dejando que los propios datos "hablen" y revelen patrones inesperados.

#### Objetivos principales del EDA:
* **Comprender la estructura de los datos:** dimensiones, tipos de variables, relaciones entre ellas.
* **Detectar patrones y anomalías:** tendencias, clusters, outliers, valores atípicos.
* **Identificar problemas de calidad:** datos faltantes, inconsistencias, errores.
* **Formular hipótesis:** generar preguntas y suposiciones basadas en observaciones.
* **Validar supuestos:** verificar si los datos cumplen con las condiciones necesarias para análisis posteriores.
* **Seleccionar técnicas apropiadas:** determinar qué métodos estadísticos o de machine learning son más adecuados.

#### Importancia del EDA en el Análisis de Datos
El EDA es crucial por varias razones fundamentales:

1.  **Prevención de errores costosos:** Realizar un EDA adecuado puede evitar que se construyan modelos sobre datos defectuosos o mal entendidos. Un modelo de machine learning entrenado con datos de mala calidad producirá resultados poco confiables, independientemente de cuán sofisticado sea el algoritmo.
2.  **Ahorro de tiempo y recursos:** Aunque puede parecer que "retrasa" el análisis, el EDA ahorra tiempo a largo plazo al identificar tempranamente problemas que podrían requerir correcciones extensas más adelante.
3.  **Generación de insights valiosos:** Muchas veces, el EDA revela hallazgos interesantes que por sí mismos tienen valor de negocio, sin necesidad de modelado predictivo complejo.
4.  **Mejora en la toma de decisiones:** Proporciona contexto y comprensión profunda que permite tomar decisiones informadas sobre estrategias de análisis y modelado.
5.  **Comunicación efectiva:** Las visualizaciones y resúmenes del EDA facilitan la comunicación de hallazgos a stakeholders no técnicos.

#### Ejemplo práctico
Imagina que trabajas con datos de ventas de una empresa retail. Un EDA revelaría:
* Que las ventas de ciertos productos tienen patrones estacionales claros.
* Que hay valores negativos en la columna de "cantidad vendida" (probablemente errores de entrada).
* Que el 30% de los registros no tienen información de categoría de producto.
* Que existe una correlación fuerte entre la ubicación de la tienda y el ticket promedio de compra.

> Estos descubrimientos guiarían tanto la limpieza de datos como las decisiones de modelado posteriores.

---

### 2. Objetivos del EDA

Aunque el objetivo general es "conocer los datos", el EDA se desglosa en metas específicas que aseguran que el dataset esté listo para el modelado o la toma de decisiones. A continuación, se describen los objetivos clave:

#### A. Garantizar la Calidad e Integridad de los Datos
Antes de buscar patrones, es fundamental asegurar que los datos sean utilizables.
* **Detección de valores faltantes (Missing Values):** Identificar qué columnas tienen datos nulos, cuantificarlos y decidir la estrategia a seguir (eliminar filas, imputar con la media/mediana, o usar algoritmos predictivos).
* **Identificación de duplicados:** Encontrar registros repetidos que puedan sesgar los resultados estadísticos.
* **Corrección de tipos de datos:** Asegurar que las fechas sean objetos `datetime`, que los números no estén guardados como texto, y que las variables categóricas estén codificadas correctamente.

#### B. Comprender las Distribuciones de las Variables
Analizar cómo se comportan las variables de manera individual (**Análisis Univariable**).
* **Medidas de tendencia central:** Calcular la media, mediana y moda para entender el "valor típico".
* **Medidas de dispersión:** Analizar la desviación estándar, varianza y rango intercuartílico para ver qué tan dispersos están los datos.
* **Forma de la distribución:** Verificar si los datos siguen una distribución normal (campana de Gauss), si están sesgados hacia la izquierda o derecha (skewness), o si tienen colas pesadas (kurtosis).

#### C. Detección de Anomalías (Outliers)
Localizar valores que se alejan drásticamente del comportamiento normal del grupo.
* **Validación de errores:** Determinar si un outlier es un error de recolección (ej. una edad de 200 años) que debe eliminarse.
* **Hallazgo de eventos raros:** En contextos como detección de fraude o ciberseguridad, los outliers son el objetivo principal del análisis y no deben eliminarse, sino estudiarse.

#### D. Análisis de Relaciones y Correlaciones
Entender cómo interactúan las variables entre sí (**Análisis Bivariable y Multivariable**).
* **Correlación:** Identificar si el aumento de una variable (ej. inversión en publicidad) está asociado con el aumento o disminución de otra (ej. ventas).
* **Causalidad (indicios):** Aunque correlación no implica causalidad, el EDA ayuda a formular hipótesis sólidas sobre qué variables influyen en el resultado objetivo (Target).
* **Redundancia:** Detectar variables altamente correlacionadas entre sí (colinealidad) que podrían aportar la misma información, permitiendo simplificar el modelo eliminando una de ellas.

#### E. Verificación de Supuestos Estadísticos
Muchos algoritmos de Machine Learning (como la Regresión Lineal) asumen ciertas condiciones sobre los datos.
* **Normalidad:** Verificar si los residuos siguen una distribución normal.
* **Homocedasticidad:** Comprobar si la varianza de los errores es constante a lo largo del tiempo o de los valores predictores.
* **Independencia:** Asegurar que las observaciones no dependan unas de otras (especialmente en series temporales).

#### F. Selección y Creación de Características (Feature Engineering)
El EDA es la base creativa para mejorar los datos.
* **Selección de variables importantes:** Descartar columnas irrelevantes que solo añaden ruido.
* **Transformación:** Decidir si es necesario aplicar logaritmos o normalizaciones para escalar los datos.
* **Creación de nuevas variables:** Generar nuevos insights combinando columnas existentes (ej. crear una variable "Ticket Promedio" dividiendo "Ingresos Totales" para "Número de Transacciones").

---

### 3. Fases del EDA: Enfoque en Limpieza de Datos

La limpieza de datos (*Data Cleaning*) es el proceso de detectar y corregir (o eliminar) registros corruptos, inexactos o irrelevantes de un conjunto de datos.

#### 1. Detectar y Manejar Valores Faltantes (Missing Values)
Los datos faltantes aparecen como `NaN`, `null` o espacios vacíos. Ignorarlos puede causar fallos en los algoritmos o sesgos estadísticos graves.
* **Detección:** Se utilizan mapas de calor (*heatmaps*) para visualizar la distribución de nulos o conteos directos por columna.
* **Estrategias de Tratamiento:**
    * **Eliminación (Dropping):**
        * *Filas:* Se eliminan si el registro tiene demasiados campos vacíos y no aporta valor.
        * *Columnas:* Se elimina la variable completa si el porcentaje de faltantes es muy alto (ej. > 50-60%) y la variable no es crítica.
    * **Imputación (Imputation):** Rellenar los huecos con valores estimados para conservar la fila.
        * *Variables Numéricas:* Se suele rellenar con la **Media** (si la distribución es normal), la **Mediana** (si hay outliers, ya que es más robusta) o un valor constante (como 0).
        * *Variables Categóricas:* Se imputa con la **Moda** (el valor más frecuente) o se crea una nueva categoría llamada "Desconocido".
        * *Imputación Avanzada:* Usar algoritmos como K-Nearest Neighbors (KNN) para predecir el valor faltante basándose en filas similares.

#### 2. Eliminar Duplicados
La duplicidad ocurre cuando se combinan datos de diferentes fuentes o por errores en la recolección.
* **Importancia:** Los duplicados inflan artificialmente las estadísticas (como conteos o sumas) y dan más peso del debido a ciertos comportamientos, sesgando el modelo.
* **Ejecución:**
    * Se verifica la duplicidad basada en todas las columnas o en un subconjunto de identificadores únicos (ej. `ID_Cliente`).
    * Generalmente se mantiene la **primera aparición** y se descartan las siguientes, a menos que el registro más reciente sea el válido.

#### 3. Corregir Tipos de Datos (Casting)
A menudo, los datos no se cargan con el formato correcto (ej. el precio "1,000" se lee como texto debido a la coma).
* **Numéricos:** Convertir *strings* a enteros o flotantes. Si hay caracteres no numéricos (como símbolos de moneda `$`), deben eliminarse antes de la conversión.
* **Fechas:** Transformar cadenas de texto (ej. "2023-01-01") a objetos `datetime`. Esto es vital para poder extraer el año, mes, día de la semana o calcular diferencias de tiempo.
* **Categóricos:** Convertir variables con pocas opciones únicas (ej. "Sí/No", "Alto/Medio/Bajo") al tipo `category`, lo cual ahorra memoria y facilita el análisis.

#### 4. Normalizar y Limpiar Texto
Las cadenas de texto suelen ser la fuente más "sucia" de datos debido a la entrada manual humana.
* **Unificación de Mayúsculas/Minúsculas:** "Python", "python" y "PYTHON" deben tratarse como la misma entidad. Se suele estandarizar todo a minúsculas.
* **Eliminación de Espacios en Blanco:** Borrar espacios al inicio o final (`strip`) que hacen que "Dato " sea distinto de "Dato".
* **Manejo de Errores Tipográficos:** Usar distancias de edición (como Levenshtein) para agrupar términos similares (ej. "Barclona" -> "Barcelona").
* **Eliminación de Caracteres Especiales:** Retirar tildes, signos de puntuación o emojis si no son relevantes para el análisis.

#### 5. Manejo de Valores Atípicos (Outliers)
Son observaciones que se desvían tanto de las otras observaciones que levantan sospechas de haber sido generadas por un mecanismo diferente.
* **Identificación:**
    * **Rango Intercuartílico (IQR):** Se detectan valores que caen por debajo de `Q1 - 1.5*IQR` o por encima de `Q3 + 1.5*IQR`.
    * **Z-Score:** Valores que están a más de 3 desviaciones estándar de la media.
* **Decisión sobre Tratamiento:**
    * *Si es error:* Se corrige o elimina (ej. Edad = 200).
    * *Si es válido:* Se mantiene, pero a veces se aplica una transformación logarítmica para reducir su impacto, o se usa una técnica de "Winsorización" (topeando los valores extremos al percentil 95 o 99).

#### 6. Renombrar Columnas
Tener nombres de variables claros y consistentes facilita la codificación y la colaboración.
* **Estandarización:** Se recomienda usar el formato `snake_case` (minúsculas separadas por guiones bajos) en lugar de espacios o caracteres especiales.
    * *Mal:* "Fecha de Nacimiento", "Ventas($)"
    * *Bien:* `fecha_nacimiento`, `ventas_dolares`
* **Claridad:** Los nombres deben ser descriptivos pero concisos. Evitar abreviaciones crípticas (ej. cambiar `var1` por `temperatura_ambiente`).

---

### 4. Herramientas del EDA (Estadística Descriptiva y Visualización)

Para realizar un EDA efectivo, el analista se apoya en dos pilares fundamentales: los números (Estadística Descriptiva) y las gráficas (Visualización de Datos). Ambos son complementarios: la estadística ofrece precisión numérica, mientras que la visualización permite identificar patrones complejos de forma intuitiva.

#### A. Papel de la Estadística Descriptiva
La estadística descriptiva resume y condensa grandes volúmenes de datos en valores manejables que describen las propiedades del conjunto.

**1. Medidas de Tendencia Central**
Estas medidas buscan identificar el "centro" o valor más representativo de los datos.
* **Media (Promedio):** Es el valor promedio aritmético.
    * *Uso en EDA:* Útil para distribuciones simétricas (normales).
    * *Precaución:* Es muy sensible a los *outliers*. Un solo valor extremo puede distorsionar la media y dar una falsa imagen del grupo.
* **Mediana:** Es el valor que divide los datos ordenados exactamente a la mitad (50% por encima, 50% por debajo).
    * *Uso en EDA:* Es una medida **robusta**. Se prefiere sobre la media cuando los datos están sesgados (tienen "colas" largas) o contienen muchos valores atípicos (ej. salarios, precios de viviendas).
* **Moda:** Es el valor que aparece con mayor frecuencia.
    * *Uso en EDA:* Es la única medida de tendencia central válida para variables **categóricas** (no numéricas). También ayuda a identificar si una distribución es unimodal o bimodal.

**2. Medidas de Dispersión**
Indican qué tan esparcidos o concentrados están los datos alrededor del centro. Sin ellas, las medidas de tendencia central están incompletas.
* **Desviación Estándar ($\sigma$ o $s$):** Mide la distancia promedio de cada punto de datos respecto a la media.
    * *Interpretación:* Una desviación baja indica que los datos están agrupados cerca del promedio; una alta indica gran variabilidad. Está en las mismas unidades que los datos originales.
* **Varianza ($\sigma^2$ o $s^2$):** Es el cuadrado de la desviación estándar.
    * *Uso:* Fundamental en teoría estadística, pero menos intuitiva para la interpretación directa en el EDA porque sus unidades están elevadas al cuadrado.
* **Rango Intercuartílico (IQR):** Es la diferencia entre el tercer cuartil ($Q3$, 75%) y el primer cuartil ($Q1$, 25%).
    * *Uso:* Mide la dispersión del 50% central de los datos. Es la base matemática para detectar *outliers* en los diagramas de caja.

#### B. Uso de Visualizaciones Gráficas
La visualización aprovecha la capacidad del cerebro humano para procesar patrones visuales mucho más rápido que tablas numéricas. Permite detectar estructuras, tendencias y anomalías que la estadística descriptiva pura podría pasar por alto (como en el famoso cuarteto de Anscombe).

**Gráficos Univariables (Una sola variable)**
* **Histogramas:** Dividen los datos numéricos en intervalos (*bins*) y muestran la frecuencia en cada uno.
    * *Objetivo:* Revelar la forma de la distribución (Normal, Asimétrica, Bimodal).
* **Diagramas de Caja (Boxplots):** Representan visualmente los cuartiles, la mediana y los valores atípicos.
    * *Objetivo:* Comparar distribuciones entre categorías y detectar *outliers* de un vistazo.
* **Gráficos de Barras:** Muestran la frecuencia de categorías.
    * *Objetivo:* Comparar conteos en variables cualitativas.

**Gráficos Bivariables y Multivariables (Relaciones)**
* **Gráficos de Dispersión (Scatter Plots):** Muestran cada registro como un punto en coordenadas X-Y.
    * *Objetivo:* Visualizar la correlación entre dos variables numéricas (positiva, negativa, nula) y detectar patrones no lineales o *clusters*.
* **Mapas de Calor (Heatmaps):** Utilizan colores para representar la intensidad de valores en una matriz.
    * *Objetivo:* Se usan comúnmente para visualizar **Matrices de Correlación**, donde los colores cálidos indican alta correlación positiva y los fríos correlación negativa.
* **Gráficos de Línea:** Conectan puntos de datos en orden.
    * *Objetivo:* Analizar tendencias a lo largo del tiempo (Series Temporales).



### 5. Caso Práctico con IA (Ejecución por Fases)

* **Herramientas IA:** Investiga y utiliza herramientas como **Julius AI**, **Gemini**, para realizar este ejercicio.
* **Dataset:** Utiliza el siguiente archivo de datos de **películas (Movies)** para tu análisis:
    * [Enlace al Dataset (Google Drive)](https://drive.google.com/file/d/1uHvGXxrcULwZM0QiKZeCpu94GGlcHhiG/view?usp=drive_link)
    * *Columnas disponibles:* `adult`, `belongs_to_collection`, `budget`, `genres`, `homepage`, `id`, `imdb_id`, `original_language`, `original_title`, `overview`, `popularity`, `poster_path`, `production_companies`, `production_countries`, `release_date`, `revenue`, `runtime`, `spoken_languages`, `status`, `tagline`, `title`, `video`, `vote_average`, `vote_count`, `keywords`, `cast`, `crew`, `ratings`.

#### Actividad - Realiza el EDA en las siguientes 3 Fases:

#### Fase 1: Resumen y Limpieza (Vista General)
He ejecutado el proceso de carga y limpieza paso a paso en el entorno de análisis. A continuación, documento los hallazgos y correcciones aplicadas para cada uno de los 6 puntos de calidad de datos solicitados.

**1. Resumen General (`info`, `head`)**
Al cargar los datos, obtenemos una vista preliminar del conjunto. Se trata de un dataset pequeño de muestra con las siguientes características:
* **Dimensiones:** 99 filas y 28 columnas.
* **Tipos de datos:** Mezcla de numéricos (`int64`, `float64`), booleanos y texto (`object`).
* **Columnas clave:** `title`, `budget`, `revenue`, `release_date`, `vote_average`.

**Documentación de los 6 Pasos de Limpieza**
He aplicado las transformaciones necesarias para asegurar la calidad de los datos. Aquí el reporte detallado:

1.  **Detección de Nulos:**
    * Se realizó un escaneo completo de valores faltantes (`NaN`).
    * **Resultado:** En este dataset de muestra (`pi_movies_small`), **no se detectaron valores nulos** (`0 missing values`). Todas las columnas cuentan con 99 registros completos.
    * *Nota:* En datasets reales más grandes, columnas como `homepage` o `tagline` suelen tener muchos nulos que requerirían imputación o eliminación.

2.  **Eliminación de Duplicados:**
    * Se verificó la existencia de filas repetidas y duplicados en el identificador único (`id`).
    * **Filas duplicadas completas:** 0 encontradas.
    * **Duplicados por ID:** 0 encontrados.
    * **Acción:** No fue necesario eliminar filas; la integridad de unicidad es correcta.

3.  **Corrección de Tipos de Datos:**
    * Se detectaron columnas con formatos inadecuados y se corrigieron:
        * **Fechas:** La columna `release_date` se convirtió de texto (`object`) a formato de fecha (`datetime64[ns]`) para permitir análisis temporales.
        * **Numéricos:** Se aseguró que `budget`, `revenue`, `popularity`, `runtime`, `vote_average` y `vote_count` fueran numéricos (`int` o `float`).
    * *Estado Final:* `release_date` ahora es `datetime64[ns]`.

4.  **Limpieza de Texto:**
    * Se procesaron las columnas de texto principales (`title`, `original_title`, `overview`, `tagline`).
    * **Acción:** Se aplicó una limpieza estándar eliminando espacios en blanco al inicio y final (`strip`), y corrigiendo múltiples espacios internos.
    * **Ejemplo:** Títulos como `" Lock, Stock "` pasarían a `"Lock, Stock"`.

5.  **Detección de Outliers (Valores Atípicos):**
    * Analicé la columna **`revenue` (ingresos)** utilizando el método del Rango Intercuartílico (IQR) para detectar anomalías financieras.
    * **Criterio:** Valores por encima de `Q3 + 1.5 * IQR`.
    * **Resultado:** Se detectaron **8 películas** consideradas outliers (con ingresos excepcionalmente altos o bajos respecto a la distribución normal de la muestra).

6.  **Renombrado de Columnas:**
    * Se revisaron los nombres de las columnas para asegurar consistencia.
    * **Acción:** Se estandarizó todo a `snake_case` (minúsculas con guiones bajos).
    * **Resultado:** Las columnas originales (`original_title`, `vote_average`, etc.) ya cumplían con el estándar de buenas prácticas de Python, por lo que no se requirieron cambios drásticos, solo confirmación.

**Conclusión de la Fase 1:** El dataset está ahora limpio, estructurado y tipado correctamente. Está listo para pasar a la **Fase 2** o **Fase 3** con confianza.

**Código Utilizado por la IA (Fase 1):**
```python
import pandas as pd
import numpy as np

# Load the dataset
file_path = 'pi_movies_small (1).csv'
try:
    df = pd.read_csv(file_path, sep=';')
except Exception as e:
    print(f"Error loading with ; separator: {e}")
    # Fallback to try default comma if ; fails
    df = pd.read_csv(file_path)

# --- Phase 1: Summary and Cleaning ---

# 0. General Summary
print("--- 0. GENERAL SUMMARY ---")
print(df.info())
print(df.head())

# 1. Detection of Nulls
print("\n--- 1. NULL DETECTION ---")
null_counts = df.isnull().sum()
print(null_counts[null_counts > 0])

# 2. Duplicate Removal
print("\n--- 2. DUPLICATE REMOVAL ---")
duplicates_count = df.duplicated().sum()
print(f"Full row duplicates found: {duplicates_count}")
df = df.drop_duplicates()
if 'id' in df.columns:
    id_dupes = df.duplicated(subset=['id']).sum()
    print(f"Duplicates based on 'id': {id_dupes}")
    df = df.drop_duplicates(subset=['id'])

# 3. Correction of Data Types
print("\n--- 3. DATA TYPE CORRECTION ---")
if 'release_date' in df.columns:
    df['release_date'] = pd.to_datetime(df['release_date'], errors='coerce')

numeric_cols = ['budget', 'revenue', 'popularity', 'runtime', 'vote_average', 'vote_count']
for col in numeric_cols:
    if col in df.columns:
        df[col] = pd.to_numeric(df[col], errors='coerce')

# 4. Text Cleaning
print("\n--- 4. TEXT CLEANING ---")
text_cols = ['title', 'original_title', 'overview', 'tagline']
for col in text_cols:
    if col in df.columns:
        df[col] = df[col].astype(str).str.strip().str.replace(r'\s+', ' ', regex=True)
        df.loc[df[col] == 'nan', col] = np.nan

# 5. Outlier Detection
print("\n--- 5. OUTLIER DETECTION ---")
target_col = 'revenue'
if target_col in df.columns:
    Q1 = df[target_col].quantile(0.25)
    Q3 = df[target_col].quantile(0.75)
    IQR = Q3 - Q1
    outliers = df[(df[target_col] < (Q1 - 1.5 * IQR)) | (df[target_col] > (Q3 + 1.5 * IQR))]
    print(f"Outliers detected in '{target_col}': {len(outliers)}")

# 6. Column Renaming
print("\n--- 6. COLUMN RENAMING ---")
df.columns = [c.lower().replace(' ', '_') for c in df.columns]
print(df.columns.tolist())

```

---

#### Fase 2: Análisis Univariable (Caso de Estudio)

<img width="1000" height="400" alt="Code_Generated_Image (4)" src="https://github.com/user-attachments/assets/24428415-a70d-4f6d-85bc-038a8d8c3211" />
<img width="1500" height="1000" alt="Code_Generated_Image (3)" src="https://github.com/user-attachments/assets/7b9535e1-ae70-4a65-9f2e-296af3622688" />

He seleccionado un grupo de variables clave para entender el comportamiento financiero y de crítica de las películas: **`revenue` (ingresos)**, **`vote_average` (calificación)**, **`budget` (presupuesto)** y **`runtime` (duración)**.

**1. Estadísticas Descriptivas**
La IA ha calculado las métricas principales para las variables seleccionadas. Aquí los hallazgos más relevantes:

| Estadística | Revenue (Ingresos) | Budget (Presupuesto) | Vote Average (0-10) | Runtime (min) |
| --- | --- | --- | --- | --- |
| **Media (Promedio)** | ~$16.6 Millones | ~$3.6 Millones | 5.43 | 99 min |
| **Mediana (50%)** | $0 | $0 | 6.0 | 98 min |
| **Máximo** | ~$847 Millones | $130 Millones | 9.5 | 360 min |
| **Desviación Std.** | Elevada (Alta variabilidad) | Elevada | 2.38 | 44 min |

*Observación Importante sobre Ceros:* Tanto para `revenue` como para `budget`, la mediana es **0**. Esto indica que una gran parte de este dataset de muestra no tiene datos financieros reportados.

**2. Análisis Gráfico y Visualización**
He generado histogramas y diagramas de caja (boxplots) para visualizar la distribución.

* **A. Análisis de `revenue` (Ingresos):**
* *Histograma:* Muestra una distribución extremadamente **sesgada a la derecha (right-skewed)**.
* *Boxplot:* Confirma la presencia de **outliers severos**.


* **B. Análisis de `vote_average` (Calificación Promedio):**
* *Histograma:* La distribución es mucho más **normal** (forma de campana), centrada alrededor de 6.0.
* *Boxplot:* Muestra una dispersión razonable.


* **C. Análisis de `runtime` (Duración):**
* La duración promedio es de **99 minutos**. Se detecta un valor atípico máximo de **360 minutos**.



**Entregable: Interpretación de la Distribución (Caso `revenue`)**
Para el "Caso de Estudio" profundo, nos centramos en **`revenue`**:

1. **Concentración en Cero:** La mayoría de las películas en esta muestra no reportaron ingresos (valor 0).
2. **Desigualdad Extrema:** Es un mercado de "el ganador se lo lleva todo", donde unos pocos títulos generan la gran mayoría del dinero total.
3. **No Normalidad:** Definitivamente **no sigue una distribución normal**.

**Código Utilizado por la IA (Fase 2):**

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# ... (Previous cleaning steps assumed) ...

# --- Phase 2: Univariate Analysis ---

# 1. Descriptive Statistics
selected_vars = ['budget', 'revenue', 'vote_average', 'runtime']
desc_stats = df[selected_vars].describe()
print("Descriptive Statistics:")
print(desc_stats)

# 2. Plots
plt.figure(figsize=(15, 10))

# Histogram and Boxplot for Revenue
plt.subplot(2, 2, 1)
sns.histplot(df['revenue'], kde=True, color='blue')
plt.title('Distribution of Revenue')

plt.subplot(2, 2, 2)
sns.boxplot(x=df['revenue'], color='blue')
plt.title('Boxplot of Revenue')

# Histogram and Boxplot for Vote Average
plt.subplot(2, 2, 3)
sns.histplot(df['vote_average'], kde=True, color='green')
plt.title('Distribution of Vote Average')

plt.subplot(2, 2, 4)
sns.boxplot(x=df['vote_average'], color='green')
plt.title('Boxplot of Vote Average')

plt.tight_layout()
plt.savefig('univariate_analysis.png')

```

---

# Fase 3: Análisis Bivariable / Multivariable (Relaciones)

<img width="1000" height="800" alt="image-1" src="https://github.com/user-attachments/assets/f52b448c-6483-4de1-aea2-9bdcd61ba247" />
<img width="1200" height="500" alt="image" src="https://github.com/user-attachments/assets/2a02a391-901a-41eb-abba-4f7be819cd61" />
He generado la matriz de correlación y gráficos de dispersión para visualizar cómo interactúan las variables clave del dataset.

**1. Matriz de Correlación (Heatmap)**
La matriz muestra coeficientes de correlación de Pearson (que van de -1 a 1).

* **Relación Más Fuerte: Budget vs. Revenue (0.97):** Existe una correlación positiva **extremadamente fuerte** entre el presupuesto y los ingresos.
* **Popularidad y Votos (0.89):** `vote_count` y `popularity` tienen una correlación muy alta.
* *Nota:* `vote_average` (calidad percibida) **no** tiene una correlación fuerte con el éxito financiero.

**2. Análisis Gráfico (Scatter Plots)**

* **Gráfico 1: Budget vs Revenue:** Se observa claramente una tendencia lineal positiva. Los puntos se agrupan en una línea ascendente.
* **Gráfico 2: Popularity vs Vote Average:** La dispersión es mucho mayor. No hay una línea clara, lo que indica que películas populares no siempre tienen las mejores calificaciones.

**Código Utilizado por la IA (Fase 3):**

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# ... (Previous preprocessing assumed) ...

numeric_cols = ['budget', 'revenue', 'vote_average', 'vote_count', 'popularity', 'runtime']
corr_matrix = df[numeric_cols].corr()

# 3. Plot Correlation Matrix (Heatmap)
plt.figure(figsize=(10, 8))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', fmt=".2f", linewidths=.5)
plt.title('Matriz de Correlación: Variables Numéricas')
plt.savefig('correlation_matrix.png')

# 4. Plot Scatter Plots
plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
sns.scatterplot(data=df, x='budget', y='revenue', alpha=0.6)
plt.title('Budget vs Revenue')

plt.subplot(1, 2, 2)
sns.scatterplot(data=df, x='popularity', y='vote_average', alpha=0.6, color='orange')
plt.title('Popularity vs Vote Average')

plt.tight_layout()
plt.savefig('scatter_plots.png')

```

**Conclusión del Caso Práctico:**
A través de las 3 fases, hemos limpiado un dataset crudo, descubierto que la distribución de ingresos es altamente desigual (Fase 2) y confirmado que el dinero llama al dinero (`Budget` -> `Revenue`), pero que el presupuesto no compra la calidad crítica (`Vote Average`) (Fase 3).

---

### 6. Referencias

Aquí tienes la sección final para tu documento. Estas referencias respaldan tanto la teoría como la práctica desarrollada.

**Fundamentos Teóricos y Estadísticos:**

* **Bruce, P., Bruce, A., & Gedeck, P.** (2020). *Practical statistics for data scientists: 50+ essential concepts using R and Python* (2.ª ed.). O'Reilly Media.
* **Tukey, J. W.** (1977). *Exploratory data analysis*. Addison-Wesley.
* **Hair, J. F., Black, W. C., Babin, B. J., & Anderson, R. E.** (2019). *Multivariate data analysis* (8.ª ed.). Cengage Learning.

**Herramientas Técnicas y Limpieza de Datos (Python/Pandas):**

* **McKinney, W.** (2022). *Python for data analysis: Data wrangling with pandas, NumPy, and Jupyter* (3.ª ed.). O'Reilly Media.
* **VanderPlas, J.** (2016). *Python data science handbook: Essential tools for working with data*. O'Reilly Media.

**Recursos de Industria y Definiciones:**

* **IBM Cloud Education.** (2020, 25 de agosto). *Exploratory Data Analysis*. IBM. [https://www.ibm.com/cloud/learn/exploratory-data-analysis](https://www.ibm.com/cloud/learn/exploratory-data-analysis)

---

### Resumen de la Actividad Completa

Con esto, has completado una guía integral de EDA que abarca:

1. **Definición:** El enfoque de "conocer los datos" de Tukey.
2. **Objetivos:** Desde la calidad hasta la generación de hipótesis.
3. **Proceso Técnico:** Una guía detallada de limpieza (Missing values, Outliers, etc.).
4. **Herramientas:** Estadística descriptiva y visualización.
5. **Práctica:** Un caso de uso real con el dataset de "Movies" validado con código.
6. **Sustento:** Bibliografía académica y técnica confiable.

---

## Formato de Entrega

* **Formato:** Documento tipo Wiki sobre este archivo README.md
* **Fecha de Entrega:** 18 de diciembre 2025.
* **Evaluación:** Se priorizará la calidad y detalle en la **Fase 1 (Limpieza)**, la correcta ejecución del caso de estudio univariable y la evidencia del uso de IA.

---

## Nota

Este trabajo será discutido en clase. Prepárate para mostrar cómo las herramientas de IA te ayudaron a limpiar y entender los datos del caso práctico de películas.

```

```
