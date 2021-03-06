# Islandora Simple Map KML

Islandora Simple Map submodule that provides functionality for passing KML files (via URL) to Islandora objects or
collections for display on a map.

## Overview


## Requirements

* [Islandora](https://github.com/Islandora/islandora)
* [Islandora Simple Map](https://github.com/Islandora-Labs/islandora_simple_map)

Install as usual, see [this](https://drupal.org/documentation/install/modules-themes/modules-7) for further information.

KML data is currently only shown if the 'map type' option for Islandora Simple Map is set to 'Google Maps'.

## Configuration

This module allows you to specify optional XPath selectors for extracting KML data from MODS or DDI datastreams.
However, the functionality to display this data on the map is still in development.

Admin settings are available at `admin/islandora/tools/islandora_simple_map/kml`.

## API

`hook_islandora_simple_map_kml_get_kml(AbstractObject $object)`

Implementations of this hook should return an array of publicly-available URLs to KML files.
These are merged with all other implementations.

`hook_islandora_simple_map_kml_get_kml_alter(array &$kml, AbstractObject $object)`

Implementations of this hook can alter the data provided by other implementations. The first argument is the array
of KML files returned by all implementations.

## Maintainer

* [Mark Jordan](https://github.com/mjordan)
* [Jared Whiklo](https://github.com/whikloj)

## To do

* Use a KML parsing library to convert the KML data to GeoJSON and add it to maps, instead of using Google Maps' JS API
  KmlLayer() method, which uses a hosted service and hence requires publicly-available URLs.
* Decide on the approach for collections - extract KML from each object's datastreams in the collection, or just the
  collection's?

## Development and feedback

Pull requests are welcome, as are use cases and suggestions.

## License

* [GPLv3](http://www.gnu.org/licenses/gpl-3.0.txt)

