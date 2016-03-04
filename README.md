# mkgmap-bike-onroad

A basic style for mkgmap designed for on-road cycling.

This style is intended to remove many features not relevant and result in the smallest possible file for import into a simple cycling GPS such as Garmin's Edge 520.

For example, the principality of Andorra (468 km²):

- [OpenFietsmap](http://www.openfietsmap.nl/) 'lite' yields .img file of 480KB.
- [mkgmap-bike-onroad](https://github.com/raintonr/mkgmap-bike-onroad) yields .img file of 29KB (16x smaller).

## Usage

- Get maps from http://download.geofabrik.de/
- Get mkgmap from http://www.mkgmap.org.uk/

### Example execution

```
java -Xms512m -Xmx4096m -jar mkgmap.jar -c mkgmap.options andorra-latest.osm.pbf
```

## Large Areas

Using this style mkgmap requires OSM data as input, but at this time it's unclear as to if a subset of this data (eg: just those elements such as roads, etc) is available so full OSM data is used as input.

Unfortunately large areas cannot be processed with mkgmap unless there is a *lot* of RAM availbale to the JVM. However, a large Garmin output file can still be created by processing OSM data in chunks and then merging the created images. In order to do this simple use of the *mapname* command line argument is required (otherwise all maps are output with the default name and merging is not possible due to this overlap).

Note that the author has been unable to have mkgmap successfully merge multipe image outputs but [GMapTool](http://www.gmaptool.eu/) has been found to work.

### Merging Execution

For example, merge three Southern French departments:

```
java -Xms512m -Xmx4096m -jar mkgmap.jar -c mkgmap.options --mapname=1 aquitaine-latest.osm.pbf
java -Xms512m -Xmx4096m -jar mkgmap.jar -c mkgmap.options --mapname=2 midi-pyrenees-latest.osm.pbf
java -Xms512m -Xmx4096m -jar mkgmap.jar -c mkgmap.options --mapname=3 languedoc-roussillon-latest.osm.pbf
gmt -j 1.img 2.img 3.img -o gmapsupp.img
```

## Example renders

Below are example renders (with [QMapShack](https://bitbucket.org/maproom/qmapshack)) of Andorra using Openfietsmap & mkgmap-bike-onroad for comparison:

mkgmap-bike-onroad:
![Eg1](/examples/eg1.bike-onroad.jpg?raw=true)

Openfietsmap:
![Eg1](/examples/eg1.openfietsmap.jpg?raw=true)

mkgmap-bike-onroad:
![Eg2](/examples/eg2.bike-onroad.jpg?raw=true)

Openfietsmap:
![Eg2](/examples/eg2.openfietsmap.jpg?raw=true)

mkgmap-bike-onroad:
![Eg3](/examples/eg3.bike-onroad.jpg?raw=true)

Openfietsmap:
![Eg3](/examples/eg3.openfietsmap.jpg?raw=true)
