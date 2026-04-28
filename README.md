***Pontificia Universidad Javeriana***
# **Procesamiento de Alto Volumen de Datos**
# Calidad-del-Agua
Implementar modelos de predicción utilizando la biblioteca de aprendizaje automático MLlib PySpark, con el fin de explorar y aplicar técnicas de IA en entornos de procesamiento con alto volúmen de datos
### Parcial: **Tratamiento de Datos y Machine Learning con PySpark**

Autor: Sara Mejia Giraldo

# Secciones
## *1. Importación de bibliotecas*
### *1.1. Levantamiento de variables de entorno pip*
### *1.2. Levantamiento de sesión SPARK*
### *1.3. Carga de Datos desde el HADOOP HDFS*
## *2. Análisis y Preparación de Datos*
### 2.1. Tipos de datos: coherencia de tipo de datos, transformacion
### 2.1.1. Revisión inicial de la estructura:
### 2.1.2. Definición de tipos esperados:
### 2.1.3. Transformación de variables:
### 2.2. Columnas: conocimiento de las columnas, eliminación
### 2.3. Estadisticas Descriptivas
### 2.4. Visualización de los DATOS NULOS
### 2.4.1. Análisis Faltantes
### 2.4.2. Imputacion de valores:
### 2.4.3. Eliminación de filas con registros faltantes
## *3. Análisis Exploratorio de los Parámetros de Calidad del Agua*
### 3.1. Distribución de los Parámetros
### 3.2. Correlación entre los Parámetros
### 3.3. Distribución del Oxígeno Disuelto (DO) y pH
### 3.4. Distribución de la Demanda Bioquímica de Oxígeno (BOD) y Nitrógeno
### 3.5. Distribución de Coliformes Fecales (FC) y Conductividad
## *4. Clasificación de la Calidad del Agua Mediante Rangos por Variable*
### 4.1. Clasificación según el pH
### 4.2. Clasificación según DO
### 4.3. Clasificación según COND
### 4.4. Clasificación según BOD
### 4.5. Clasificación según NITRATE_N_NITRITE_N
### 4.6. Clasificación según el Material Fecal
## *5. Construcción del Índice de Calidad del Agua (ICA)*
### 5.1. Verificación del DataFrame Base (df08)
### 5.2. Creación de Variables de Puntaje por Parámetro
### 5.3. Cálculo del Índice Global de Calidad del Agua
### 5.4. Clasificación Final del Agua según ICA
### **6. Visualización de Estados de la India**
### 6.1. Se cargan los datos de los mapas disponibles
### 6.2. Se carga un objeto dataframe de los datos comprimidos de los mapas
### 6.3. Se visualiza el tipo de dataframe que da geopandas y las columnas 
### 6.4. Corrección nombres 
### 6.5. Mapa inicial
### 6.6. Mapa del Indice de Calidad WQI de la India
### 6.7. Histograma de WQI por Estado
## *7. Predicción del Índice de Calidad del Agua mediante Redes Neuronales*
### 7.1. Preparación de Datos para el Modelo
### 7.2. Construcción de la Red Neuronal
### 7.3. Compilación y Entrenamiento del Modelo
### 7.4. Evaluación del Modelo Predictivo

#### Importante
Se emplearon los siguientes intervalos para determinar la calidad del agua:
**Intervalos de Índices para WQI**
- Excelente: agua dulce ***WQI = [0.0 , 25.0]***
- Buena: agua moderada ***WQI = (25.0 , 50.0]***
- Baja: agua dura ***WQI = (50.0 , 75.0]***
- Muy_Baja: agua muy dura ***WQI = (75.0 , 100.0]***
- Inadecuada: agua residual ***WQI > 100***

#### Sugerencias
- Debido a que CONDUCTIVITY y FECAL_COLIFORM presentaron la mayor cantidad de valores faltantes. Se tomo la decision de reemplazar los valores en lugar de eliminar los registros.
- Ambas variables mostraron alta dispersión (desviación estándar elevada), lo cual sugiere presencia de variabilidad considerable y posibles valores extremos, por ende se empleo la MEDIANA al momento de imputar los valores faltantes.
- En fases posteriores, si se detectan diferencias territoriales, temporales o por tipo de fuente, se recomienda evaluar una imputación por grupos homogéneos (state, zona, periodo, etc.).

#### Fuentes
Describe the relationship between dissolved oxygen and BOD. . . | Filo. (2025, 1 septiembre). Filo. https://askfilo.com/user-question-answers-smart-solutions/describe-the-relationship-between-dissolved-oxygen-and-bod-3337363932313533
Fuente: Sensor, R. (2026, 9 febrero). La conexión entre los niveles de pH y la calidad del agua. https://www.rikasensor.com/es/a-the-connection-between-ph-levels-and-water-quality.html

### 🔸 Software necesario

- Python **3.8 o superior**
- Apache Spark **3.x**
- Java **8 o 11** (necesario para Spark)
- Jupyter Notebook o Jupyter Lab

---

### 🔧 Configuración de Apache Spark

1. Descargar Apache Spark desde:  
   👉 https://spark.apache.org/downloads.html

2. Configurar variables de entorno:

### En Linux / Mac:
```bash
export SPARK_HOME=/ruta/a/spark
export PATH=$SPARK_HOME/bin:$PATH
```

### En Windows:
- Configurar `SPARK_HOME`
- Agregar `SPARK_HOME/bin` al `PATH`

---

### ▶️ Ejecución del proyecto

1. Clonar el repositorio:

```bash
git clone https://github.com/tu-usuario/tu-repo.git
cd tu-repo
```

2. Abrir el notebook:

```bash
jupyter notebook
```

3. Ejecutar el archivo `.ipynb`

---

