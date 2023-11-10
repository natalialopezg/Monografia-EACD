<font size="5"> Seminario - Especialización en Analítica y Ciencia de Datos</font>

## ME01: Propuesta de proyecto

## ME02: Data Product Canvas 

<br>

# ME03: Data Preprocessing

## Contexto del dataset
Para el momento evaluativo 03 se seleccionó el dataset [**Dataset of groundnut plant leaf images for classification and detection**](https://data.mendeley.com/datasets/22p2vcbxfk/3), el cual contiene imágenes de hojas de plantas de cacahuete obtenidas mediante fotografías digitales en Koppal (Karnataka, India) [1]. El enfoque del dataset es la detección de enfermedades en las plantas de cacahuete a partir de fotografías de sus hojas. Este conjunto de datos es de libre acceso al público.

Se recortan las zonas de interés (hojas) de las imágenes originales, creándose un conjunto de datos compuesto por seis clases con 10361 imágenes. Cada imagen tiene un tamaño de 256 × 256 píxeles de color RGB en formato JPG [2].

Las imágenes recortadas se guardan en 6 carpetas: 

| Clase | Descripción | Cantidad de imágenes |
| :--- | :--- |:--- 
| healthy leaves | hojas sanas | 1871 |   
| early leaf spot | mancha temprana de la hoja | 1731 |
| late leaf spot | mancha tardía de la hoja | 1896 |   
| Nutrition deficiency | deficiencia nutricional | 1665 |
| rust | moho | 1724 |   
| early rust | moho temprano | 1474 |

<img src="https://drive.google.com/uc?id=1wSQGXHomtnpPXjQw1fq_BnDX1s99jspn" width="600">

<br>

Ejemplos de las imáganes del dataset:

<table>
  <tr>
    <td>Early Leaf Spot [2]</td>
     <td>Late Leaf Spot [2]</td>
  </tr>
  <tr>
    <td><img src="https://ars.els-cdn.com/content/image/1-s2.0-S2352340923003049-gr1.jpg" width=400></td>
    <td><img src="https://ars.els-cdn.com/content/image/1-s2.0-S2352340923003049-gr2.jpg" width=360></td>
  </tr>
 </table>

<br>

## Preprocesamiento de las imágenes

Para el preprocesamiento de la data se construyó el notebook en el IDE Colab [**Data_preprocessing.ipynb**](https://colab.research.google.com/drive/1_v71djbXR__qfboFdULZFTUWj9qUuuGu?usp=sharing). Este notebook tambi+én se encuentra dentro del repositorio de GitHub. Al inicio de este, se especifican los requerimientos de paquetes o librerías junto con sus versiones para una correcta ejecución.

### Entradas y salidas

#### Entradas
El notebook requiere como entradas:

*   Archivo **.xlsx** con la metadata de las imágenes como tabla estática.
*   Imágenes del *Dataset of groundnut plant leaf images for classification and detection*

Los archivos mencionados se encuentran almacenados en el repositorio de GitHub [natalialopezg/Seminario-Esp.Analitica
/Dataset of groundnut plant leaf images](https://github.com/natalialopezg/Seminario-Esp.Analitica/tree/master/Dataset%20of%20groundnut%20plant%20leaf%20images) y se accede a ellos mediante la librería de python [PyGithub](https://github.com/PyGithub/PyGithub) usando un token de acceso a GitHub REST API.


> Se cargó al repositorio una mínima cantidad de imágenes por cada directorio para efecto del desarrollo de la actividad.

La estructura de almacenamiento de las imágenes en el repositorio es la siguiente:

```
⌞ Dataset of groundnut plant leaf images [dir]
    ⌞ Metadata.xlsx [file]
    ⌞ test [dir]
        ⌞ early_leaf_spot [dir]
        ⌞ early_rust [dir]
        ⌞ healthy_leaf [dir]
        ⌞ late_leaf_spot [dir]
        ⌞ nutrition_deficiency [dir]
        ⌞ rust [dir]
    ⌞ train [dir]
        ⌞ early_leaf_spot [dir]
        ⌞ early_rust [dir]
        ⌞ healthy_leaf [dir]
        ⌞ late_leaf_spot [dir]
        ⌞ nutrition_deficiency [dir]
        ⌞ rust [dir]
```

>Para efecto del desarrollo de la actividad, se establecen los valores de los parámetros para acceder al repositorio directamente en el notebook.

<br>

#### Salidas
Como resultado del preprocesamiento se obtienen los sets de entrenamiento y prueba de tipo **numpy.ndarray** (*X_train, X_test, y_train, y_test*) a partir de las imágenes preprocesadas. Para visualizar mejor la data de salida, se presenta al final del notebook un dataframe con las etiquetas y las características de cada imagen preprocesada.

<img src="https://drive.google.com/uc?id=1YCS6zcrL98S8Z87QA_Dy872HOOsyTu64" width="600" >

<br>

En el preprocesamiento se aplican las siguientes transformaciones:

*    Redimensionamiento.
*    Filtrado
*    Normalizado

<img src="https://drive.google.com/uc?id=1hRBrPKCBEmG1ytTLd1Uc6lznii2XeIKi" width="600" >

<br>

## Referencias 

1.    Manvikar, Aishwarya; Reddy, Padmanabha  (2023), “Dataset of groundnut plant leaf images for classification and detection”, Mendeley Data, V3, doi: 10.17632/22p2vcbxfk.3
2.    M.p., A., & Reddy, A. P. (2023). Dataset of groundnut plant leaf images for classification and detection. Data in Brief, 48(109185), 109185. https://doi.org/10.1016/j.dib.2023.109185




