# Environment Tensorflow

Derived from base_ds.md, includes tensorflow and opencv

1. Create conda environment
```
conda create --name tf python=3.9
```

2. Activate environment
```
activate tf
```

3. pip install packages
```
pip install autopep8 plotly openpyxl statsmodels pandas-profiling pmdarima pycaret altair beautifulsoup4 bokeh bottleneck cloudpickle cython dask dill h5py ipympl ipywidgets matplotlib numba numexpr pandas patsy protobuf scikit-image scikit-learn scipy seaborn sqlalchemy statsmodels sympy widgetsnbextension xlrd notebook jupyter_contrib_nbextensions
```

3.1 pip install tensorflow (and other related) packages
```
pip install tensorflow opencv-python Pillow
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

6. Make .bat files for one-click-launch
```
@echo off
call C:\Anaconda3\condabin\activate tf
cd C:\Users\marcoscattolin
call jupyter notebook
pause
````
