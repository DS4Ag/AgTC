[![Wang lab logo](https://static.wixstatic.com/media/c544bf_0e3064b159ae42238c83dca23bc352e8~mv2.png/v1/crop/x_0,y_0,w_1918,h_2080/fill/w_91,h_100,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/lab_icon_3.png)](https://github.com/Purdue-LuisVargas/AgTC)



[![Python version](https://img.shields.io/pypi/pyversions/pandas)](https://www.python.org/)
[![JupyterLab](https://img.shields.io/badge/Jupyter-lab-orange)](https://jupyter.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![YAML 1.2](https://img.shields.io/badge/YAML-1.2-success)](https://yaml.org/)


[![DOI](https://zenodo.org/badge/680893453.svg)](https://zenodo.org/badge/latestdoi/680893453)

_Lee la versión en_ [español](README.es.md)

Note: to open links in new tab use CTRL+click (Windows and Linux) or CMD+click (MacOS). 

### What is AgTC?

**Ag**ronomic Experiments Data **T**emplate **C**reator  is a set of functions written in python that allow you to create custom templates to collect data for most of the typical agronomic experiments. It also can be used as template to load a "field" in the [Field Book app](https://www.phenoapps.org/apps/). 

## How to run AgTC?

- Option 1
  - Using a [Jupyter Hub](https://jupyter.org/try) enviroment.
  - **For Purdue University members only** Jupyter Hub is available at https://notebook.scholar.rcac.purdue.edu/. It requires the use of BoilerKey Two-Factor Authentication.

- Option 2

  - You should make a simple **[installation](https://jupyter.org/install "jupyter.org")** of either **JupyterLab** or **Jupyter Notebook**, or you also can install an environment management such as [conda](https://docs.conda.io/en/latest/), [mamba](https://mamba.readthedocs.io/), or [pipenv](https://pipenv.pypa.io/).


## Prerequisites

Install the requiered libraries using the [pip package installer](https://pypi.org/project/pip/) for Python.

- [PyYAML](https://pypi.org/project/PyYAML/)
    ```sh
        pip install pyyaml
    
    ```
- [Pandas](https://pypi.org/project/pandas/)
    ```sh
        pip install pandas
    
    ```    

## Clone or download AgTC from the GitHub repository
    
- [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) option
    1. Open a new Jupyter Notebook Terminal
    
    New > Terminal 
    
    2. Clone the GitHub repository 
    
    ```sh
        git clone https://github.com/Purdue-LuisVargas/AgTC.git
    
    ```
-  **Download** option

    1. [Download](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) **AgTC** from the **Github** repository: [https://github.com/Purdue-LuisVargas/AgTC](https://github.com/Purdue-LuisVargas/AgTC).
    2. Unzip the entire folder, then copy (if running Jupyter locally) or upload the downloaded files (if using the Jupyter Hub environment) in your Jupyter Notebook directory.
    
## Upload the Initial Template file

Upload the Initial Template file to the _./input_ folder. It should be a CSV format file and it has to contain the information that changes for each plot and that you want to maintain in the New Template, such as plot number, repetition number, genotype name, etc. The table below is an example of columns and rows that a Initial Template could have:

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


## Understanding the Configuration File

The **config.yml** file is a [YML file](https://yaml.org/ "yaml.org") that could be edited using **Jupyter** or a text editor. The file is divided into six blocks of configurations, where each block is identified with uppercase letters. A _BLOCK COLLECTION_ could have _keys_, _values_ and/or _sequences_.


For instance, the following data structure contains the most common items in the **config.yml** file. 

```sh
TEMPLATE_INPUT: 
  Folder : ./input/
  Sample_name: 
    - A
    - B
```
Where: 


TEMPLATE_INPUT = **BLOCK COLLECTION**

Folder = **Key**

Sample_name = **Key**

./input/ = **Value**

A, B = **Sequences**


The data structures in the **config.yml** file could have one of the following arranges.


   - Case 1
```sh
    BLOCK COLLECTION:
       Key: Value
```

   - Case 2 
```sh
    BLOCK COLLECTION:
       Key: 
          - Sequences
```
        
   - Case 3
```sh
    BLOCK COLLECTION:
       - Sequences 
```



## Update the Configuration File

You need to update the **config.yml** file using information about the experiment.  

**General rules**
1. It is **NOT** recommendable to change _BLOCK COLLECTION_ name items. If you change them, you should update the new name in the following line code on the _main.ipynb_ Jupyter file:
``` sh
functions.create_new_template('config.yml', 'TEMPLATE_INPUT', 'COLUMNS_TEMPLATE', 'NEW_COLUMNS', 'SAMPLES_PER_PLOT', 'SAMPLE_IDENTIFIER', 'TEMPLATE_OUTPUT')
```
2. **You can** modify the name of any _Key_ item. Additionally, for some _BLOCK COLLECTION_ items, you should delete or add more depending on the experiment information. 


3. **You should** update _Value_ items with the experiment information, but you cannot add more than one item per _Key_.


4. **You should delete, add or modify** _Sequences_ items as needed.  


5. Be sure to keep the correct indentation. Use the spacebar instead tab key.


#### TEMPLATE_INPUT
Used to define the path and name of the Initial Template file.

- You can modify the name of the _Key_ items.


- **You should** update the _Value_ items (e.g. trialInformation_PPAC_soybean_M2_y22.csv from the _Input_template_file_name Key_) with your file Initial Template name.

```sh
TEMPLATE_INPUT: 
  Folder : ./input/
  Input_template_file_name : trialInformation_PPAC_soybean_M2_y22.csv
```

#### COLUMNS_TEMPLATE

It allows to specify the column names that will be selected from the Initial Template File. 

- Even if you want to maintain all the columns from the Initial Template file, **you should** write their names as _Sequences_. Add or delete as many _Sequences_ as necessary. 

```sh
COLUMNS_TEMPLATE:
  - Plot
  - Repetition
  - Genotype
```

#### NEW_COLUMNS

It allows to write the names and values for the new columns that will be added to the New Template.

- **You can** add, delete or modify _Key_ items based on your experiment information.


- **You should** update the _Value_ items based on your experiment information.

```sh
NEW_COLUMNS: 
  Experiment : ACRE-Biomass
  Season : y22
  Environment : Early planting date
  Measurment : Plant height
  Sampling_identifier : Sampling-2
```

#### SAMPLES_PER_PLOT

This section is used to specify the number of repetitions of a measurement on the same experimental unit (plot, pot, growth chamber, etc.). It would create a row for each subsample name that the user indicates.

- **You should** specify the _Sequences_ with the name that you want to identify each subsample. Modify, delete, or change the _Sequences_ according to the measurement characteristics for which the Template will be created. 

```sh
SAMPLES_PER_PLOT:
  Sample_name: 
    - A
    - B
    - C
    - D
```

#### SAMPLE_IDENTIFIER

It allows to specify the names of the columns with the values that will be used to create a unique identifier for each subsample (row).

- **You should NOT** add o delete _Key_ items, but you can change its name. The _Key_ name is the name of the column that the New Template will have.


- **You should** update the _Sequences_ items according to the experiment  information. Add or delete as many _Sequences_ as necessary. **Make sure** that the _Sequences_ names exist as _key_ in the items COLUMNS_TEMPLATE, NEW_COLUMNS and _SAMPLES_PER_PLOT._

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

It allows to specify the column names which values will be used to create the New Template file name.

- **You should** update the _Sequences_ items according the experiment information. Add or delete as many _Sequences_ as necessary. **Make sure** that the _Sequences_ names exist as _key_ in the NEW_COLUMNS item.

```sh
TEMPLATE_OUTPUT: 
  - Measurment
  - Sampling_identifier
  - Experiment
  - Environment
  - Season
```
## Run the Python functions 

Open the **main.ipynb** file in **Jupyter**, execute the two block of instructions. You would find your New Template in the _./output_ folder.

## Contact

Luis Vargas Rojas - [lvargasr@purdue.edu](lvargasr@purdue.edu)

Purdue University, Wang Lab [dianewanglab.com](https://www.dianewanglab.com/)
