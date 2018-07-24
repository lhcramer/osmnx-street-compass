### description

This is a retooling of Geoff Boeing's fun [notebook](https://github.com/gboeing/osmnx-examples/blob/master/notebooks/17-street-network-orientations.ipynb) showing how to generate a visualization of street network orientations using osmnx, pandas, and matplotlib. Read his full article about the concept: https://geoffboeing.com/publications/osmnx-complex-street-networks/. 

The code has been refactored to accept a polygon shapefile (e.g. neighborhood boundaries), and can be run straight from the command line. You can also input a set of places stored in JSON (as before, though now in a separate `.json` file).

Any feedback or tickets are welcome!

### use

You'll need `matplotlib`, `numpy`, `pandas`, `geopandas`, and `osmnx` in your Python environment. The code has been tested with Python 3.6, but it should work with earlier releases. All file output will be placed in a new `images` directory.

    python generate_street_orientations.py example/ZillowNeighborhoods-LA-nolasliver.shp -l Name -t "Some New Orleans Neighborhoods"
    
will produce

[]

where the `-l/--label_field` argument is the name of the shapefile field that is used to label the graph of each feature and `-t/--title` is the super title of the final image and the name of the file. One graph is made for every feature in the shapefile.

    python generate_street_orientations.py example/lacities.json -t "Some Louisiana Cities"

will produce

[]

#### other options

`--save_network_images` will also export png images of the network that is usedto make each graph.

`--weight_by_length` will give more weight to longer streets in the compass visualization

`--timestamp` will add a timestamp to the output file name