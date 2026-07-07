# Análisis del Uso de Clientes – Telecom LATAM

## Descripción del proyecto

Este proyecto tiene como objetivo analizar el comportamiento de los clientes de una empresa de telecomunicaciones en Latinoamérica mediante técnicas de análisis exploratorio de datos (EDA) y limpieza de datos. A partir de la información de clientes, planes contratados y registros de uso del servicio, se busca identificar patrones de consumo, segmentar usuarios y generar recomendaciones de negocio basadas en datos.

El proyecto incluye las etapas de evaluación de la calidad de los datos, tratamiento de valores faltantes e inconsistentes, análisis estadístico, visualización de datos y creación de segmentos de clientes.

---

# Objetivos

- Evaluar la calidad de los datos e identificar posibles problemas.
- Limpiar y preparar la información para su análisis.
- Analizar el comportamiento de los usuarios mediante estadísticas descriptivas y visualizaciones.
- Crear segmentos de clientes según su edad y nivel de uso del servicio.
- Generar insights y recomendaciones que apoyen la toma de decisiones de negocio.

---

# Conjunto de datos

El análisis utiliza tres archivos en formato CSV:

| Archivo | Descripción |
|----------|-------------|
| **plans.csv** | Contiene la información de los planes telefónicos disponibles (Básico y Premium). |
| **users_latam.csv** | Contiene la información demográfica de los clientes, incluyendo edad, ciudad, fecha de registro, plan contratado y fecha de cancelación. |
| **usage.csv** | Contiene el historial de uso de cada cliente, incluyendo llamadas, mensajes de texto, duración de llamadas y longitud de los mensajes. |

Los archivos se cargan mediante:

```python
import pandas as pd

plans = pd.read_csv('/datasets/plans.csv')
users = pd.read_csv('/datasets/users_latam.csv')
usage = pd.read_csv('/datasets/usage.csv')
```

---

# Etapas del análisis

## 1. Carga e inspección de los datos

- Importación de librerías.
- Carga de los tres conjuntos de datos.
- Revisión de dimensiones, tipos de datos y estructura general.

## 2. Evaluación de la calidad de los datos

- Identificación de valores nulos.
- Detección de registros duplicados.
- Búsqueda de valores centinela (por ejemplo, `-999`).
- Validación de fechas.
- Revisión de variables categóricas.
- Análisis descriptivo de variables numéricas.

## 3. Limpieza de datos

Durante esta etapa se realizaron las siguientes acciones:

- Reemplazo del valor `"?"` por valores nulos en la columna **city**.
- Sustitución del valor centinela **-999** en la edad por la mediana.
- Conversión de las columnas de fecha al formato `datetime`.
- Identificación y tratamiento de fechas fuera del período de estudio.
- Validación de los valores nulos de acuerdo con las reglas del negocio.

## 4. Análisis Exploratorio de Datos (EDA)

Se realizaron diferentes análisis para comprender el comportamiento de los clientes:

- Estadísticos descriptivos.
- Histogramas.
- Boxplots.
- Distribuciones de variables categóricas.
- Detección de valores atípicos mediante el método del rango intercuartílico (IQR).

## 5. Integración de datos

Los registros de uso fueron agregados por usuario para calcular:

- Cantidad total de mensajes enviados.
- Cantidad total de llamadas realizadas.
- Minutos totales de llamadas.

Posteriormente, esta información se integró con la base de datos de clientes para construir un perfil consolidado de cada usuario.

## 6. Ingeniería de variables

Se crearon nuevas variables para facilitar el análisis:

### Segmentación por edad

- Joven
- Adulto
- Adulto Mayor

### Segmentación por nivel de uso

- Bajo uso
- Uso medio
- Alto uso

## 7. Análisis de negocio

Finalmente, se desarrolló un análisis orientado al negocio que incluye:

- Segmentación de clientes.
- Análisis del comportamiento de consumo.
- Identificación de oportunidades comerciales.
- Recomendaciones estratégicas basadas en datos.

---

# Principales hallazgos

- La mayoría de los clientes pertenece al segmento de **Uso medio**, representando aproximadamente el 74 % de la cartera.
- Los usuarios de **Alto uso** constituyen un grupo reducido, pero representan un segmento estratégico para la empresa.
- Los problemas de calidad encontrados fueron limitados y pudieron resolverse sin afectar significativamente la información.
- La mayoría de los valores nulos correspondían al comportamiento esperado del negocio y no a errores de captura.
- La segmentación realizada facilita la identificación de oportunidades para campañas de fidelización y estrategias comerciales diferenciadas.

---

# Tecnologías utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Google Colab

---

# Cómo ejecutar el proyecto

## Opción 1: Google Colab

1. Descarga el archivo del notebook (`.ipynb`).
2. Abre **Google Colab**.
3. Sube el notebook.
4. Carga los archivos `plans.csv`, `users_latam.csv` y `usage.csv` en la carpeta `datasets` o modifica las rutas de acceso según corresponda.
5. Ejecuta todas las celdas en orden.

## Opción 2: Jupyter Notebook

1. Clona el repositorio:
2. Instala las librerías necesarias:
3. Abre el notebook:
4. Ejecuta todas las celdas de forma secuencial.

---

# Estructura del proyecto

```
proyecto/
│
├── datasets/
│   ├── plans.csv
│   ├── users_latam.csv
│   └── usage.csv
│
├── notebooks/
│   └── Analisis_Uso_Clientes.ipynb
│
├── README.md
│
└── images/
```

---

# Autor

**Naiara Altuna**

Data Analyst | Environmental & Sustainability Analytics | SQL | Python | ESG Reporting
