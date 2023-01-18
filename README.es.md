[![Wang lab logo](https://static.wixstatic.com/media/c544bf_0e3064b159ae42238c83dca23bc352e8~mv2.png/v1/crop/x_0,y_0,w_1918,h_2080/fill/w_91,h_100,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/lab_icon_3.png)](https://github.com/Purdue-LuisVargas/agrXdatec)



[![Python version](https://img.shields.io/pypi/pyversions/pandas)](https://www.python.org/)
[![JupyterLab](https://img.shields.io/badge/Jupyter-lab-orange)](https://jupyter.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![YAML 1.2](https://img.shields.io/badge/YAML-1.2-success)](https://yaml.org/)


_Read this in_ [English](README.md) 


Nota: para abrir los enlaces de manual en una nueva ventana usa CTRL+click (Windows y Linux) o CMD+click (MacOS).
 

### ¿Qué es agrXdatec?

**AGR**onomic E**X**periments **DA**ta **TE**mplate **C**reator son un conjunto de funciones escritas en Python que permiten crear plantillas personalizadas para colectar datos en la mayoría de los experimentos agronómicos comunes. También puede ser utilizada como plantilla para los archivos “Field” en la aplicación  [Field Book app](https://www.phenoapps.org/apps/). 


## ¿Cómo ejecutar agrXdatec?

- Opción 1
  - Usando un ambiente de [Jupyter Hub](https://jupyter.org/try).
  - **Para miembros de Purdue University** Jupyter Hub está disponible en https://notebook.scholar.rcac.purdue.edu/. Requiere el uso de BoilerKey Two-Factor Authentication.

- Opción 2

    - Puedes hacer una [instalación](https://jupyter.org/install "jupyter.org") de **JupyterLab** o de **Jupyter Notebook**. También puedes instalar un gestor de entornos como [conda](https://docs.conda.io/en/latest/), [mamba](https://mamba.readthedocs.io/), o [pipenv](https://pipenv.pypa.io/).


## Prerrequisitos

Instala los siguentes paquetes usando el [pip package installer](https://pypi.org/project/pip/) de Python.

- [PyYAML](https://pypi.org/project/PyYAML/)
    
    ```sh
            pip install pyyaml
    
    ```
- [Pandas](https://pypi.org/project/pandas/)
    ```sh
        pip install pandas
    
    ``` 
    
## Clona o descarga agrXdatec desde el repositorio de GitHub

- Opción [Clonar](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).
    1. Abre una nueva terminal en Jupyter Notebook.
    
    New > Terminal 
    
    2. Clona el repositorio de GitHub. 
    
    ```sh
        git clone https://github.com/Purdue-LuisVargas/agrXdatec.git
    
    ```
-  Opción **descargar**:

    1. Descarga el repositorio de GitHub usando el siguiente enlace: [https://github.com/Purdue-LuisVargas/agrXdatec](https://github.com/Purdue-LuisVargas/agrXdatec).
    
    2. Descomprime el folder, después copia (si estas usando Jupyter en modo local) o carga los archivos descargados (si esas usando Jupyter Hub) en tu folder de Jupyter Notebook.

## Carga la Plantilla Base

Carga la Plantilla Base en la carpeta _./input._ El archivo debe estar en formato CSV y contener la información que es diferente por cada unidad experimental (parcela, maceta, cámara de crecimiento, etc.). Por ejemplo, el número de parcela y repetición, el nombre del genotipo, etc. La siguiente tabla es un ejemplo de columnas y filas que podría tener una Plantilla Base:
<table class="dataframe" border="1">
  <thead>
    <tr style="text-align: right;">
      <th>parcela</th>
      <th>genotipo</th>
      <th>repetición</th>
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

El archivo **config.yml** es un [documento YML](https://yaml.org/ "yaml.org") que se puede abrir con Jupyter notebooks o con un editor de texto. El archivo se divide en seis bloques de configuraciones, donde cada bloque se identifica con letras mayúsculas. Dichos bloques de configuraciones (BLOCK COLLECTION) puede tener claves (_Key_), valores (_Value_) y/o secuencias (_Sequences_).

Por ejemplo, la siguiente estructura de datos contiene los elementos más comunes en el archivo **config.yml**.

```sh
TEMPLATE_INPUT: 
  Folder : ./input/
  Sample_name: 
    - A
    - B
```
Donde: 


TEMPLATE_INPUT = **BLOCK COLLECTION**

Folder = _**Key**_

Sample_name = _**Key**_

./input/ = _**Value**_

A, B = _**Sequences**_


Las estructuras de datos en el archivo **config.yml** podrían tener uno de los siguientes arreglos.


   - Caso 1
```sh
    BLOCK COLLECTION:
       Key: Value
```

   - Caso 2 
```sh
    BLOCK COLLECTION 
       Key: 
          - Sequences
```
        
   - Caso 3
```sh
    BLOCK COLLECTION
       - Sequences 
```


## Actualizar el Archivo de Configuración 

Actualiza el archivo **config.yml** con la información del experimento.

Reglas generales:
1.  **No es recomendable** cambiar los nombres de los _BLOCK COLLECTION_. Si los cambias, tendrás que actualizar la siguiente línea de código del archivo **main.ipynb**.
``` sh
functions.create_new_template('config.yml', 'TEMPLATE_INPUT', 'COLUMNS_TEMPLATE', 'NEW_COLUMNS', 'SAMPLES_PER_PLOT', 'SAMPLE_IDENTIFIER', 'TEMPLATE_OUTPUT')
```

2.  **Puedes** modificar el nombre de cualquier _Key  item_. Adicionalmente, en algunos _BLOCK COLLECTION_ tienes que eliminar o agregar más _Key  items_ según la información del experimento.
3.  **Tienes** que actualizar el contenido de los _Value items_ con información del experimento. 
4.  **Tienes** que agregar, eliminar elementos de _Sequence items_ como sea necesario. 
5.  Asegúrate de mantener la identacion adecuada en cada  línea de código. Usa la barra espaciadora en lugar del la techa del tabulación.

#### TEMPLATE_INPUT

Indica la ruta y nombre del archivo de la Plantilla Base.

- Puedes modificar el nombre de los _Key ítems_.
- **Debes** actualizar el valor de los _Value ítems_. (ej. trialInformation_PPAC_soybean_M2_y22.csv) con el nombre de la Plantilla Base. 
```sh
TEMPLATE_INPUT: 
  Folder : ./input/
  Input_template_file_name : trialInformation_PPAC_soybean_M2_y22.csv
```

#### COLUMNS_TEMPLATE

Contiene los nombres de las columnas que serán seleccionadas de la Plantilla Base. 
- Incluso si quieres del mantener todas las columnas de la Plantilla Base, **tienes que** escribir sus nombres como _Sequence items_. Agrega o elimina todas los _Sequence items_ necesarios. 

```sh
COLUMNS_TEMPLATE:
  - Plot
  - Repetition
  - Genotype
```

#### NEW_COLUMNS

Permite escribir los nombres y valores de las columnas que se añadirán a la Nueva Plantilla.
- **Puedes** agregar, eliminar o modificar _Key items_ de acuerdo con la información de tu experimento. 
- **Tienes que** actualizar los _Value items_ de acuerdo de acuerdo con la información de tu experimento.

```sh
NEW_COLUMNS: 
  Experiment : ACRE-Biomass
  Season : y22
  Environment : Early planting date
  Measurment : Plant height
  Sampling_identifier : Sampling-2
```   

#### SAMPLES_PER_PLOT

Este bloque es usado para especificar el numero de veces que se repite en una medida en la misma unidad experimental (parcela, maceta, cámara de crecimiento, etc.). Esto creara una fila por cada submuestra de acuerdo con los _Sequence items_ que indique el usuario. 

- **Tienes que** especificar los _Sequence items_ con el nombre con el cual quieres identificar cada submuestra. Elimina, agrega o cambia las secuencias de acuerdo con las características de la medida para la que se creara la Nueva Plantilla. 

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

- **No debes** de agregar o eliminar _Key items_, pero puedes cambiar su nombre. El _Key item_ es el nombre de la columna que la Nueva Plantilla tendrá. 

- **Tienes que** actualizar los _Sequence items_ de acuerdo a la información del experimento. Puedes agregar tantos _Sequence items_ como sea necesario. Asegúrate que los _Sequence items_ existen como _Key items_ en los siguientes elementos: COLUMNS_TEMPLATE, NEW_COLUMNS y SAMPLES_PER_PLOT.

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
- **Tienes que** actualizar los _Sequences items_ de acuerdo con la información del experimento. Agrega o elimina tantos _Sequences items_ como sea necesario. Asegúrate que los _Sequence items_ existen como _Key items_ en el NEW_COLUMNS _item_.

```sh
TEMPLATE_OUTPUT: 
  - Measurment
  - Sampling_identifier
  - Experiment
  - Environment
  - Season
```

## Ejecuta las funciones de Python  

Abre el archivo **main.ipynb**  en  **Jupyter**, ejecuta los dos bloques de instrucciones. En nuevo Template creado se encontrara en la carpera_./output_.

## Contacto

Luis Vargas Rojas - [lvargasr@purdue.edu](lvargasr@purdue.edu)

Purdue University, Wang Lab [dianewanglab.com](https://www.dianewanglab.com/)