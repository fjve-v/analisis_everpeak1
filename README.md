# ⚙️ Data Cleaning Pipeline: Everpeak Retail

Este repositorio contiene un flujo de trabajo (pipeline) completamente automatizado para transformar datos brutos (raw data) en un dataset optimizado para análisis y modelos predictivos.

## 🎯 Objetivo del Proyecto
Eliminar la intervención manual en la limpieza de datos mediante un script que garantiza la consistencia de los datos, aplicando reglas de negocio y transformaciones estadísticas de forma programática.

## 🛠️ Arquitectura del Pipeline

El pipeline procesa los datos en las siguientes etapas críticas:

1. **Estandarización de Texto:** - Normalización de columnas categóricas (`city`, `state`, `payment_method`) eliminando espacios en blanco y estandarizando mayúsculas/minúsculas.

2. **Ingeniería de Características Temporales:**
   - Conversión de objetos a `datetime`.
   - Extracción automática de componentes temporales (Día, Mes, Año, Día de la Semana).

3. **Imputación Estadística de Nulos:**
   - Aplicación de **mediana** para variables numéricas (`order_value`, `customer_age`) para mitigar el efecto de valores atípicos.
   - Imputación por **moda** (valor más frecuente) para variables categóricas geográficas.

4. **Validación de Integridad:**
   - Verificación final de valores nulos (0% missingness garantizado tras ejecución).

## 📊 Impacto en los Datos
* **Dataset Original:** 5,008 registros con múltiples inconsistencias y nulos en columnas clave.
* **Dataset Procesado:** 100% libre de nulos, con columnas temporales enriquecidas y listo para alimentar un dashboard de BI o un modelo de ML.

## 🚀 Uso
1. Coloca tu archivo `everpeak_retail.csv` en la carpeta raíz.
2. Ejecuta el notebook `Construyendo_un_pipeline_completo_para_limpieza_de_datos.ipynb`.
3. El dataset limpio se exportará automáticamente como `everpeak_retail_limpio.csv`.

---
*Desarrollado para optimizar procesos de Data Engineering y Analytics.*
