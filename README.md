# Leaflet Measure Path

A plugin to show measurements on paths (polylines, polygons and circles currently supported).

[Leaflet Measure Path demo](http://www.liedman.net/leaflet-measure-path/)

## Usage

Load `leaflet-measure-path.js` and `leaflet-measure-path.css`. Then, to enable measurements on a path:

```js
var polygon = L.polygon([ ... ])
    .addTo(map)
    .showMeasurements();
```

To later hide measurements:

```js
var polygon = L.polygon([ ... ])
    .addTo(map)
    .hideMeasurements();
```

## API

The plugin adds the methods listed below to Leaflet's `L.Polyline`, `L.Polygon` and `L.Circle` classes.

### showMeasurements(options)

Enables measurements. You can also overide the defaults by passing an options object.

#### Options

* `showOnHover: Boolean` (default `false`): if `true`, the measurements will only show when the user hovers the cursor over the path
* `minDistance: Number` (default `30`): the minimum length a line segment in the feature must have for a measurement to be added
* `formatDistance: Function`: allows to override the built-in function that formats a distance in meters to the string shown in the map
* `formatArea: Function`: allows to override the built-in function that formats an area in square meters to the string shown in the map

### hideMeasurements()

Disables measurements.

### updateMeasurements()

Updates the measurements displayed. Normally, this method is called automatically if the path's geometry is changed using `setLatLngs`, `spliceLatLngs` or when the map is zoomed. If the geometry is somehow changed by other means, this method can be called to force the measurements to update.

