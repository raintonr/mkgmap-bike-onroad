# mkgmap-bike-onroad

A basic style for mkgmap designed for on-road cycling.

This style is intended to remove many features not relevant and result in the smallest possible file for import into a simple cycling GPS such as Garmin's Edge 520.

For example, the principality of Andorra (468 km²):

- [OpenFietsmap](http://www.openfietsmap.nl/) 'lite' yields .img file of 480KB.
- [mkgmap-bike-onroad](https://github.com/raintonr/mkgmap-bike-onroad) yields .img file of 29KB (16x smaller).

## Usage

- Get maps from http://download.geofabrik.de/
- Get mkgmap from http://www.mkgmap.org.uk/

Example execution

```
java -Xms512m -Xmx4096m -jar mkgmap.jar -c mkgmap.options andorra-latest.osm.pbf
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
