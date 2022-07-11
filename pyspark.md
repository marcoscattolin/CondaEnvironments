# Environment pyspark

Derived from base_ds, includes pyspark

## Prerequisites
### Java 8 Runtime environment
Check with:
```
java -version
```
```
## Expected
java version "1.8.0_281"
Java(TM) SE Runtime Environment (build 1.8.0_281-b09)
Java HotSpot(TM) Client VM (build 25.281-b09, mixed mode)
```


### Download spark
https://spark.apache.org/downloads.html
<br>Pay attention to selected spark and hadoop version

### Download hadoop winutils.exe
https://github.com/kontext-tech/winutils
<br>Select correct version of hadoop depending on selected spark version

**Note**: as of today hadoop the following has been tested
- spark packages with hadoop 3 are not working when writing parquet files
- spark packages with hadoop 2.7 are working
- No delta lake support is provided for spark 3.3

### Unpack and create following directories

- Unpack downloaded spark archive into (example for spark 3.2.1)<br>
`C:\spark\spark-3.2.1-bin-hadoop2.7`

- Create directory (example for hadoop 2.7.7)<br>
`C:\spark\hadoop-2.7.7\bin`<br>
and copy winutils.exe inside it

- Create directory<br>
`C:\zz_spark_temp\spark_scratch`


## Installation
1. Create conda environment
```
conda create --name pyspark python=3.9
```

2. Activate environment
```
activate pyspark
```

3. pip install packages
```
pip install autopep8 plotly openpyxl statsmodels pandas-profiling pmdarima pycaret altair beautifulsoup4 bokeh bottleneck cloudpickle cython dask dill h5py ipympl ipywidgets matplotlib numba numexpr pandas patsy protobuf scikit-image scikit-learn scipy seaborn sqlalchemy statsmodels sympy widgetsnbextension xlrd notebook jupyter_contrib_nbextensions 
```

3.1 pip install pyspark and sparksql packages
```
pip install pyspark sparksql-magic
```

4. conda install pytables
```
conda install pytables
```

5. Install jupyter notebooks extensions and activate modules
```
jupyter contrib nbextension install --user
jupyter nbextension enable spellchecker/main --user
jupyter nbextension enable collapsible_headings/main --user
jupyter nbextension enable exercise2/main --user
jupyter nbextension enable highlight_selected_word/main --user
jupyter nbextension enable scratchpad/main --user
jupyter nbextension enable tree-filter/index --user
jupyter nbextension enable autoscroll/main --user
jupyter nbextension enable execute_time/ExecuteTime --user
jupyter nbextension enable export_embedded/main --user
jupyter nbextension enable scroll_down/main --user
jupyter nbextension enable snippets/main --user
jupyter nbextension enable toc2/main --user
jupyter nbextension enable varInspector/main --user
jupyter nbextension enable contrib_nbextensions_help_item/main --user
jupyter nbextension enable freeze/main --user
jupyter nbextension enable jupyterlab-plotly/extension --user
jupyter nbextension enable nbextensions_configurator/tree_tab/main --user
jupyter nbextension enable printview/main --user
jupyter nbextension enable snippets_menu/main --user
jupyter nbextension enable table_beautifier/main --user
jupyter nbextension enable code_prettify/autopep8 --user
jupyter nbextension enable datestamper/main --user
jupyter nbextension enable exercise/main --user
jupyter nbextension enable nbextensions_configurator/config_menu/main --user
jupyter nbextension enable toggle_all_line_numbers/main --user
```
6. Set following environment **User** variables
Adjust depending on dowloaded packages and paths

- HADOOP_HOME = C:\spark\hadoop-2.7.7
- PYSPARK_DRIVER_PYTHON = C:\Anaconda3\envs\pyspark\Scripts\jupyter-notebook.exe
- PYSPARK_PYTHON = C:\Anaconda3\envs\pyspark\python.exe
- SPARK_HOME = C:\spark\spark-3.2.1-bin-hadoop2.7
- SPARK_LOCAL_DIRS = C:\zz_spark_temp\spark_scratch

7. Add to **User** variable Path:
- %SPARK_HOME%\bin
- %HADOOP_HOME%\bin


8. Make delta_lake.bat file for one-click-launch
```
@echo off
call C:\Anaconda3\condabin\activate pyspark
cd C:\Users\marcoscattolin
call pyspark --packages io.delta:delta-core_2.12:1.2.1 --conf "spark.sql.extensions=io.delta.sql.DeltaSparkSessionExtension" --conf "spark.sql.catalog.spark_catalog=org.apache.spark.sql.delta.catalog.DeltaCatalog"
pause
```
