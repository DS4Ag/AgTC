[![Wang lab logo](https://static.wixstatic.com/media/c544bf_0e3064b159ae42238c83dca23bc352e8~mv2.png/v1/crop/x_0,y_0,w_1918,h_2080/fill/w_91,h_100,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/lab_icon_3.png)](https://github.com/Purdue-LuisVargas/AgTC)



[![Python version](https://img.shields.io/pypi/pyversions/pandas)](https://www.python.org/)
[![JupyterLab](https://img.shields.io/badge/Jupyter-lab-orange)](https://jupyter.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![YAML 1.2](https://img.shields.io/badge/YAML-1.2-success)](https://yaml.org/)



[![DOI](https://zenodo.org/badge/680893453.svg)](https://zenodo.org/badge/latestdoi/680893453)


_Read this in_ [English](README.md) 

[Clic en este enlace para ver los videos tutoriales.](https://www.youtube.com/playlist?list=PLb-PBxMrefhP9qO2Fe7Dcz72cUWMoQyy_)


Nota: para abrir los enlaces de manual en una nueva ventana usa CTRL+click (Windows y Linux) o CMD+click (MacOS).
 

### ¿Qué es AgTC?

**Ag**ronomic Experiments Data **T**emplate **C**reator son un conjunto de funciones escritas en **Py**thon que permiten crear plantillas personalizadas para colectar datos en la mayoría de los experimentos agronómicos comunes. También puede ser utilizada como plantilla para los archivos “Field” en la aplicación  [Field Book app](https://www.phenoapps.org/apps/). 


## ¿Cómo ejecutar AgTC?

- Opción 1
  - Usando un ambiente de [Jupyter Hub](https://jupyter.org/try).
  - **Para miembros de Purdue University** Jupyter Hub está disponible en https://notebook.scholar.rcac.purdue.edu/. Requiere el uso de BoilerKey Two-Factor Authentication.

- Opción 2

    - Puedes hacer una [instalación](https://jupyter.org/install "jupyter.org") de **JupyterLab** o de **Jupyter Notebook**. También puedes instalar un gestor de entornos como [conda](https://docs.conda.io/en/latest/), [mamba](https://mamba.readthedocs.io/), o [pipenv](https://pipenv.pypa.io/).


## Prerrequisitos

- Opción 1

    - Using Requirements File 

 ```sh
    pip install -r requirements.txt
``` 
- Opción 2

  - Instala los siguentes paquetes usando el [pip package installer](https://pypi.org/project/pip/) de Python.

    [PyYAML](https://pypi.org/project/PyYAML/)
    
    ```sh
        pip install pyyaml
    
    ```
    [Pandas](https://pypi.org/project/pandas/)
    ```sh
        pip install pandas
    
    ``` 
    
## Clona o descarga AgTC desde el repositorio de GitHub

- Opción [Clonar](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).
    1. Abre una nueva terminal en Jupyter Notebook.
    
    New > Terminal 
    
    2. Clona el repositorio de GitHub. 
    
    ```sh
        git clone https://github.com/Purdue-LuisVargas/AgTC.git
    
    ```
-  Opción **descargar**:

    1. Descarga el repositorio de GitHub usando el siguiente enlace: [https://github.com/Purdue-LuisVargas/AgTC](https://github.com/Purdue-LuisVargas/AgTC).
    
    2. Descomprime el folder, después copia (si estas usando Jupyter en modo local) o carga los archivos descargados (si esas usando Jupyter Hub) en tu folder de Jupyter Notebook.

## Carga la Plantilla Base

Carga la Plantilla Base en la carpeta _./input._ El archivo debe estar en formato CSV y contener la información que es diferente por cada unidad experimental (parcela, maceta, cámara de crecimiento, etc.). Por ejemplo, el número de parcela y repetición, el nombre del genotipo, etc. La siguiente tabla es un ejemplo de columnas y filas que podría tener una Plantilla Base:
<table class="dataframe" border="1">
  <thead>
    <tr style="text-align: right;">
      <th>plot</th>
      <th>genotype</th>
      <th>repetition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>PI594301</td>
      <td>3</td>
    </tr>
    <tr>
      <td>2</td>
      <td>LD-07-3395bf</td>
      <td>23</td>
    </tr>
    <tr>
      <td>3</td>
      <td>SA1730464</td>
      <td>18</td>
    </tr>
    <tr>
      <td>4</td>
      <td>PI154189</td>
      <td>14</td>
    </tr>
    <tr>
      <td>5</td>
      <td>PI594451</td>
      <td>2</td>
    </tr>
    <tr>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <td>71</td>
      <td>CR16-0042</td>
      <td>20</td>
    </tr>
    <tr>
      <td>72</td>
      <td>SA1811280</td>
      <td>25</td>
    </tr>
    <tr>
      <td>73</td>
      <td>E19517GT</td>
      <td>24</td>
    </tr>
    <tr>
      <td>74</td>
      <td>LD-07-3395bf</td>
      <td>23</td>
    </tr>
    <tr>
      <td>75</td>
      <td>PI6548362</td>
      <td>8</td>
    </tr>
  </tbody>
</table>

## Contenido del Archivo de Configuración

El archivo **config.yml** es un [documento YML](https://yaml.org/ "yaml.org") que se puede abrir con Jupyter notebooks o con un editor de texto. El archivo se divide en seis _Bloques_ de configuraciones, donde cada bloque se identifica con letras mayúsculas. Dichos _Bloques_ puede tener _Claves_, _Valores_ y/o _Listas_.

Por ejemplo, la siguiente estructura de datos contiene los elementos más comunes en el archivo **config.yml**.

```sh
TEMPLATE_INPUT: 
  Folder : ./input/
  Sample_name: 
    - A
    - B
```
Donde: 


TEMPLATE_INPUT = **BLOQUE**

Folder = _**Clave**_

Sample_name = _**Clave**_

./input/ = _**Valor**_

A, B = _**Lista**_


Las estructuras de datos en el archivo **config.yml** podrían tener uno de los siguientes arreglos.


   - Caso 1
```sh
    BLOQUE:
       Clave: Valor
```

   - Caso 2 
```sh
    BLOQUE: 
       Clave: 
          - Lista
```
        
   - Caso 3
```sh
    BLOQUE:
       - Lista 
```


## Actualizar el Archivo de Configuración 

Actualiza el archivo **config.yml** con la información del experimento.

Reglas generales:
1.  **No es recomendable** cambiar los nombres de los _Bloques_. Si los cambias, tendrás que actualizar la siguiente línea de código del archivo **main.ipynb**.
``` sh
functions.create_new_template('config.yml', 'TEMPLATE_INPUT', 'COLUMNS_TEMPLATE', 'NEW_COLUMNS', 'SAMPLES_PER_PLOT', 'SAMPLE_IDENTIFIER', 'TEMPLATE_OUTPUT')
```

2.  **Puedes** modificar el nombre de cualquier _Clave_. Adicionalmente, en algunos _Bloques_ tienes que eliminar o agregar más _Claves_ según la información del experimento.
3.  **Tienes** que actualizar los _Valores_ con información del experimento. 
4.  **Tienes** que agregar o eliminar elementos la _Lista_ como sea necesario. 
5.  Asegúrate de mantener la identacion adecuada en cada  línea de código. Usa la barra espaciadora en lugar del la techa del tabulación.

#### TEMPLATE_INPUT

Indica la ruta y nombre del archivo de la Plantilla Base.

- Puedes modificar el nombre de las _Claves_.
- **Debes** actualizar el los _Valores_. (ej. trialInformation_PPAC_soybean_M2_y22.csv) con el nombre de la Plantilla Base. 
```sh
TEMPLATE_INPUT: 
  Folder : ./input/
  Input_template_file_name : trialInformation_PPAC_soybean_M2_y22.csv
```

#### COLUMNS_TEMPLATE

Contiene los nombres de las columnas que serán seleccionadas de la Plantilla Base. 
- Incluso si quieres del mantener todas las columnas de la Plantilla Base, **tienes que** escribir sus nombres como una _Lista_. Agrega o elimina todas los elementos de la _Lista_ como sea necesario. 

```sh
COLUMNS_TEMPLATE:
  - Plot
  - Repetition
  - Genotype
```

#### NEW_COLUMNS

Permite escribir los nombres y valores de las columnas que se añadirán a la Nueva Plantilla.
- **Puedes** agregar, eliminar o modificar _Claves_ de acuerdo con la información de tu experimento. 
- **Tienes que** actualizar los _Valores_ de acuerdo de acuerdo con la información de tu experimento.

```sh
NEW_COLUMNS: 
  Experiment : ACRE-Biomass
  Season : y22
  Environment : Early planting date
  Measurment : Plant height
  Sampling_identifier : Sampling-2
```   

#### SAMPLES_PER_PLOT

Este bloque es usado para especificar el numero de veces que se repite en una medida en la misma unidad experimental (parcela, maceta, cámara de crecimiento, etc.). Esto creara una fila por cada submuestra de acuerdo con los elementos de la _Lista_ que indique el usuario. 

- **Tienes que** especificar los elementos de la _Lista_ con el nombre con el cual quieres identificar cada submuestra. Elimina, agrega o cambia las secuencias de acuerdo con las características de la medida para la que se creara la Nueva Plantilla. 

```sh
SAMPLES_PER_PLOT:
  Sample_name: 
    - A
    - B
    - C
    - D
```

#### SAMPLE_IDENTIFIER

Permite especificar los nombres de columnas con los valores que serán usados para crear un identificador único para cada submuestra (fila). 

- **No debes** de agregar o eliminar _Claves_, pero puedes cambiar su nombre. _La clave_ es el nombre de la columna que tendrá la Nueva Plantilla. 

- **Tienes que** actualizar los elementos de la _Lista_ de acuerdo a la información del experimento. Puedes agregar tantos elementos a la _Lista_ como sea necesario. Asegúrate que los elementos de la _Lista_ existen como _Claves_ en los siguientes elementos: COLUMNS_TEMPLATE, NEW_COLUMNS y SAMPLES_PER_PLOT.

```sh
SAMPLE_IDENTIFIER :
  id_sample:
    - Plot
    - Sample_name
    - Experiment
    - Environment
    - Season
    - Measurment
    - Sampling_identifier
```

#### TEMPLATE_OUTPUT

Permite especificar los nombres de las columnas cuyos valores se utilizarán para crear el nombre de la Nueva Plantilla. 
- **Tienes que** actualizar los elemetos de la _Lista_ de acuerdo con la información del experimento. Agrega o elimina tantos los elemetos de la _Lista_ como sea necesario. Asegúrate que los elemetos de la _Lista_ existen como _Claves_ en el NEW_COLUMNS _item_.

```sh
TEMPLATE_OUTPUT: 
  - Measurment
  - Sampling_identifier
  - Experiment
  - Environment
  - Season
```

## Ejecutar las funciones de Python  

Abre el archivo **main.ipynb**  en  **Jupyter**, ejecuta los dos bloques de instrucciones. En nuevo Template creado se encontrara en la carpera_./output_.

## ¿Cómo citar?

Vargas-Rojas L, Ting T-C, Rainey KM, Reynolds M and Wang DR (2024) AgTC and AgETL: open-source tools to enhance data collection and management for plant science research. Front. Plant Sci. 15:1265073. doi: [10.3389/fpls.2024.1265073](https://www.frontiersin.org/journals/plant-science/articles/10.3389/fpls.2024.1265073/full).

## Contacto

Luis Vargas Rojas - [lvargasr@purdue.edu](lvargasr@purdue.edu)

Purdue University, Wang Lab [dianewanglab.com](https://www.dianewanglab.com/)