# Interactive Widgets

Jupyter widgets enable interactive data visualization in the Jupyter notebooks.

icon to represent multiple notebooksNotebook Widgets
Notebooks come alive when interactive widgets are used. Users can visualize and control changes in the data. Learning becomes an immersive, plus fun, experience. Researchers can easily see how changing inputs to a model impacts the results.

ipyleaflet

Geo-spatial analytics

bqplot

2-D interactive data visualization

pythreejs

3-D data visualization

ipyvolume

3-D plotting

nglview

3-D interactive molecular visualization

BeakerX

tables, plotting, forms

jupyter-gmaps

Data visualization on Google Maps

cookiecutter

Template widget project

ipyleaflet
Binder GitHub
A library for creating simple interactive maps with panning and zooming, ipyleaflet supports annotations such as polygons, markers, and more generally any geojson-encoded geographical data structure.

Example
from ipyleaflet import Map

Map(center=[34.6252978589571, -77.34580993652344], zoom=10) +
−
Leaflet | Map data (c) OpenStreetMap contributors
Installation
With conda:
conda install -c conda-forge ipyleaflet
With pip:
pip install ipyleaflet
jupyter nbextension enable --py --sys-prefix ipyleaflet
