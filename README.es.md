[![Wang lab logo](https://static.wixstatic.com/media/c544bf_0e3064b159ae42238c83dca23bc352e8~mv2.png/v1/crop/x_0,y_0,w_1918,h_2080/fill/w_91,h_100,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/lab_icon_3.png)](https://github.com/Purdue-LuisVargas/agrXdatec)



[![Python version](https://img.shields.io/pypi/pyversions/pandas)](https://www.python.org/)
[![JupyterLab](https://img.shields.io/badge/Jupyter-lab-orange)](https://jupyter.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![YAML 1.2](https://img.shields.io/badge/YAML-1.2-success)](https://yaml.org/)


_Read this in_ [English](README.md) 

Note: to open links in new tab use CTRL+click (Windows and Linux) or CMD+click (MacOS). 

### ¿Qué es agrXdatec?

**AGR**onomic E**X**periments **DA**ta **TE**mplate **C**reator son un conjunto de funciones escritas en Python que permiten crear plantillas personalizadas para colectar datos en la mayoría de los experimentos agronómicos comunes. También puede ser utilizada como plantilla para los archivos “Field” en la aplicación  [Field Book app](https://www.phenoapps.org/apps/). 

_Read this in_ [English](Readme.md) 

## Prerrequisitos

- Opción 1
  - Usando un ambiente de [Jupyter Hub](https://jupyter.org/try).
  - **Para miembros de Purdue University** 	Jupyter Hub está disponible en https://notebook.scholar.rcac.purdue.edu/. Requiere el uso de BoilerKey Two-Factor Authentication.

- Opción 2

Puedes hacer una [instalación](https://jupyter.org/install "jupyter.org") de **JupyterLab** o de **Jupyter Notebook**. También puedes instalar gestor de entornos como [conda](https://docs.conda.io/en/latest/), [mamba](https://mamba.readthedocs.io/), o [pipenv](https://pipenv.pypa.io/).


## Instalar paquetes

1. 1.	Instala las los paquetes requeridos usando el [pip package installer](https://pypi.org/project/pip/) de Python.

    - [PyYAML](https://pypi.org/project/PyYAML/)
    ```sh
        pip install pyyaml
    
    ```
    - [Pandas](https://pypi.org/project/pandas/)
    ```sh
        pip install pandas
    
    ```    

2. [Descarga](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) **agrXdatec** del repositorio de **Github** usando el siguiente enlace: [https://github.com/Purdue-LuisVargas/agrXdatec](https://github.com/Purdue-LuisVargas/agrXdatec).

    ```sh
        git clone https://github.com/Purdue-LuisVargas/agrXdatec.git
    
    ```

## Correr Jupyter Notebook

1. [Ejecutar Jupyter Notebook App](https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/execute.html)
2. Descomprime el folder, después copia (si estas usando Jupyter en modo local) o carga los archivos descargados (si esas usando Jupyter Hub) en tu folder de Jupyter Notebook. 
3. Crea el siguiente folder en dentro de tu directorio de trabajo en Jupyter Notebook  _./output_.

