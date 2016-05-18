# GeoJSON Object Schema
GraphQL schema

## Notes:
- Specifications available at: http://geojson.org/geojson-spec.html
- Test data taken from: http://geojsonlint.com 


## Implementations:
- [graphql-geojson-go](https://github.com/sogko/graphql-geojson-go)
- [data-gov-sg-graphql-go/schema/geojson](https://github.com/sogko/data-gov-sg-graphql-go/tree/master/lib/schema/geojson)


## Example of queries

```json
{
  data {
    type
    ... Geometry
    ... Feature
    ... FeatureCollection
    ... GeometryCollection
  }
  fragment Geometry on GeoJSONGeometryInterface {
    type
    coordinates
  }
  fragment Feature on GeoJSONFeature {
    geometry {
      ... Geometry
    }
  }
  fragment FeatureCollection on GeoJSONFeatureCollection {
    features {
      ... Feature
    }
  }
  fragment GeometryCollection on GeoJSONGeometryCollection {
    geometries {
      ... Geometry
    }
  }

```
