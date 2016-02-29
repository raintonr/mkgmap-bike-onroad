# mkgmap-bike-onroad

A basic style for mkgmap designed for on-road cycling.

This style is intended to remove many features not relevant and result in the smallest possible file for import into a simple cycling GPS such as Garmin's Edge 520.

For example, the principality of Andorra (468 km²):

- [OpenFietsmap](http://www.openfietsmap.nl/) yields .img file of 480KB.
- [mkgmap-bike-onroad](https://github.com/raintonr/mkgmap-bike-onroad) yields .img file of 29KB (16x smaller).

## Usage

- Get maps from http://download.geofabrik.de/
- Get mkgmap from http://www.mkgmap.org.uk/

Example execution

```
java -Xms512m -Xmx4096m -jar mkgmap.jar -c mkgmap.options europe-latest.osm.pbf
```


