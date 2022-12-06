[![Wang lab logo](https://static.wixstatic.com/media/c544bf_0e3064b159ae42238c83dca23bc352e8~mv2.png/v1/crop/x_0,y_0,w_1918,h_2080/fill/w_91,h_100,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/lab_icon_3.png)](https://github.com/Purdue-LuisVargas/agrXdatec)



[![Python version](https://img.shields.io/pypi/pyversions/pandas)](https://www.python.org/)
[![JupyterLab](https://img.shields.io/badge/Jupyter-lab-orange)](https://jupyter.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![YAML 1.2](https://img.shields.io/badge/YAML-1.2-success)](https://yaml.org/)

Lee la versión en [español](Readme.es.md)

### What is agrXdatec?

**AGR**onomic E**X**periments **DA**ta **TE**mplate **C**reator is a set of functions written in python that allow you to create custom templates to collect data for most of the typical agronomic experiments. It also can be used as template to load a "field" in the [Field Book app](https://www.phenoapps.org/apps/). 


## Prerequisites 

- Option 1
  - Using a [Jupyter Hub](https://jupyter.org/try) enviroment.
  - **For Purdue University members only** Jupyter Hub is available at https://notebook.scholar.rcac.purdue.edu/. It requires the use of BoilerKey Two-Factor Authentication.

- Option 2

You should make a simple **[installation](https://jupyter.org/install "jupyter.org")** of either **JupyterLab** or **Jupyter Notebook**, or you also can install an environment management such as [conda](https://docs.conda.io/en/latest/), [mamba](https://mamba.readthedocs.io/), or [pipenv](https://pipenv.pypa.io/).


## Installing Packages

1. Install the requiered libraries using the [pip package installer](https://pypi.org/project/pip/) for Python.

    - [PyYAML](https://pypi.org/project/PyYAML/)
    ```sh
        pip install pyyaml
    
    ```
    - [Pandas](https://pypi.org/project/pandas/)
    ```sh
        pip install pandas
    
    ```    

2. [Clone or download](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) **agrXdatec** from the **Github** repository: [https://github.com/Purdue-LuisVargas/agrXdatec](https://github.com/Purdue-LuisVargas/agrXdatec).

    ```sh
        git clone https://github.com/Purdue-LuisVargas/agrXdatec.git
    
    ```
## Running the Jupyter Notebook

1. [Launch Jupyter Notebook App](https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/execute.html)
2. Copy (if running locally ) or upload the downloaded files (if using the hub environment)  in your notebook folder. 
3. Create the following folder ./output.
    
## Upload your base template file

Upload your base template file to the _./output_ folder. It should be a CSV format file and it has to contain the information that changes for each plot and that you want to maintain in the template, such as plot number, repetition number, genotype name, etc. The table below is an example of columns and rows that a base template could have:

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


## Understanding the config.yml file

The **config.yml** file is a [YML file](https://yaml.org/ "yaml.org") that could be edited using **Jupyter** or you also can use use a code editor such as [Visual Studio Code](https://code.visualstudio.com/) or [Sublime Text](https://www.sublimetext.com/). The file is divided into six blocks of configurations, where each block is identified with uppercase letters. A _block collection_ could have _keys_, _values_ and/or _sequences_.


For instance, the following data structure contains the most common items in the config.yml file. 

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


The data structures in the config.yml file could have one of the following structures.


   - Case 1
```sh
    BLOCK COLLECTION:
       Key: Value
```

   - Case 2 
```sh
    BLOCK COLLECTION 
       Key: 
          - Sequences
```
        
   - Case 3
```sh
    BLOCK COLLECTION
       - Sequences 
```



## Update the config.yml file

You need to update the **config.yml** with your experiment and variable information from where you will collect data. One template should be created for each variable and for each time you collect the same variable.

**General rules**
1. It is **NOT** recommendable to change _BLOCK COLLECTION_ name items. If you change them, you should update the new name in the following line code on the _main.ipynb_ Jupyter file:
``` sh
functions.create_new_template('config.yml', 'TEMPLATE_INPUT', 'COLUMNS_TEMPLATE', 'NEW_COLUMNS', 'SAMPLES_PER_PLOT', 'SAMPLE_IDENTIFIER', 'TEMPLATE_OUTPUT')
```
2. **You can** modify the name of any _Key_ item. Additionally, for some _BLOCK COLLECTION_ items, you should delete or add more depending on your experiment and variable information. 


3. **You should** update _Value_ items with your experiment and variable information, but you cannot add more than one item per _Key_.


4. **You should add, delete or modify** _Sequences_ items as needed.  


5. Be sure to keep the correct indentation.


#### TEMPLATE_INPUT
Defines the locations and name of the file that contains the basic information about the experiment.

- You can modify the name of the _Key_ items.


- **You should** update the _Value_ items (e.g. trialInformation_PPAC_soybean_M2_y22.csv) from the _Input_template_file_name Key_ with your file base template name.

```sh
TEMPLATE_INPUT: 
  Folder : ./input/
  Input_template_file_name : trialInformation_PPAC_soybean_M2_y22.csv
```

#### COLUMNS_TEMPLATE
Contains the column names that will be selected from the input template. 

- Even if you want to keep all the columns that your base template file has, **You should** specify the _Sequences._ whit the column names of your template. Add or delete as many _Sequences_ as necessary. 

```sh
COLUMNS_TEMPLATE:
  - Plot
  - Repetition
  - Genotype
```

#### NEW_COLUMNS
It has the names and values for the new columns that will be added to the current template to create the new file.

- **You should** add, delete or modify _Key_ items based on your experiment information.


- **You should** update the _Value_ items based on your experiment information.

```sh
NEW_COLUMNS: 
  Experiment : ACRE-Biomass
  Season : y22
  Treatment_1 : Early planting date
  Measurment : Plant height
  Sampling_identifier : Sampling-2
```

#### SAMPLES_PER_PLOT
This section is used to specify the number of repetitions of measurement on each plot. It would create a row for each sample name that the user identifies.

- **You should** specify the _Sequences._ with the name that you want to identify each sample. Add or delete as many _Sequences_ as necessary. 

```sh
SAMPLES_PER_PLOT:
  Sample_name: 
    - A
    - B
    - C
    - D
```

#### SAMPLE_IDENTIFIER
It contains the names of the columns with the values that will be used to create a unique identifier for each sample (row).

- **You should NOT** add o delete _Key_ items, but you can change its name. The _Key_ name is the name of the column that your final template will have.


- **You should** update the _Sequences_ items according to your experiment and variable information. Add or delete as many _Sequences_ as necessary. **Be sure** that the _Sequences_ names exist as _key_ in the items COLUMNS_TEMPLATE, NEW_COLUMNS and _SAMPLES_PER_PLOT._

```sh
SAMPLE_IDENTIFIER :
  id_sample:
    - Plot
    - Sample_name
    - Experiment
    - Treatment_1
    - Season
    - Measurment
    - Sampling_identifier
```

#### TEMPLATE_OUTPUT
Column names which values will be used to create the name for the output file.

- **You should** update the _Sequences_ items according to your experiment and variable information. Add or delete as many _Sequences_ as necessary. **Be sure** that the _Sequences_ names exist as _key_ in the NEW_COLUMNS item.

```sh
TEMPLATE_OUTPUT: 
  - Measurment
  - Sampling_identifier
  - Experiment
  - Treatment_1
  - Season
```
## Run the python functions 

Open the **main.ipynb** file in **Jupyter**, execute the two block of instructions. You would find your new file in the _./output_ folder.

## Contact

Luis Vargas Rojas - [lvargasr@purdue.edu](lvargasr@purdue.edu)

Purdue University, Wang Lab [dianewanglab.com](https://www.dianewanglab.com/)

Project Link: [https://github.com/Purdue-LuisVargas/agrXdatec](https://github.com/Purdue-LuisVargas/agrXdatec)