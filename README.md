# Grafana-Dashboard
JSON File for Grafana Dashboard Pulling directly from InfluxDB 

```bash 
{
  "annotations": {
    "list": [
      {
        "builtIn": 1,
        "datasource": {
          "type": "grafana",
          "uid": "-- Grafana --"
        },
        "enable": true,
        "hide": true,
        "iconColor": "rgba(0, 211, 255, 1)",
        "name": "Annotations & Alerts",
        "type": "dashboard"
      }
    ]
  },
  "editable": true,
  "fiscalYearStartMonth": 0,
  "graphTooltip": 0,
  "id": 35,
  "links": [],
  "liveNow": true,
  "panels": [
    {
      "datasource": {
        "type": "influxdb",
        "uid": "fdfg5thhknb40f"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisBorderShow": false,
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 0,
            "gradientMode": "none",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "insertNulls": false,
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "auto",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 0,
        "y": 0
      },
      "id": 5,
      "options": {
        "legend": {
          "calcs": [],
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": true
        },
        "tooltip": {
          "maxHeight": 600,
          "mode": "single",
          "sort": "none"
        }
      },
      "targets": [
        {
          "dataset": "iox",
          "datasource": {
            "type": "influxdb",
            "uid": "fdfg5thhknb40f"
          },
          "editorMode": "builder",
          "format": "table",
          "rawSql": "SELECT \"time\", \"track\" FROM \"adsbicaoNEW\" WHERE \"time\" >= $__timeFrom AND \"time\" <= $__timeTo ",
          "refId": "A",
          "sql": {
            "columns": [
              {
                "parameters": [
                  {
                    "name": "time",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "track",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              }
            ],
            "groupBy": [
              {
                "property": {
                  "type": "string"
                },
                "type": "groupBy"
              }
            ]
          },
          "table": "adsbicaoNEW"
        }
      ],
      "title": "Received Messages",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "influxdb",
        "uid": "fdfg5thhknb40f"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "custom": {
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 0,
        "y": 8
      },
      "id": 4,
      "options": {
        "basemap": {
          "config": {
            "showLabels": true,
            "theme": "auto"
          },
          "name": "Layer 0",
          "type": "carto"
        },
        "controls": {
          "mouseWheelZoom": true,
          "showAttribution": true,
          "showDebug": false,
          "showMeasure": false,
          "showScale": false,
          "showZoom": true
        },
        "layers": [
          {
            "name": "Layer 3",
            "opacity": 0.4,
            "tooltip": true,
            "type": "osm-standard"
          },
          {
            "config": {
              "showLegend": true,
              "style": {
                "color": {
                  "fixed": "dark-green"
                },
                "opacity": 0.4,
                "rotation": {
                  "fixed": 0,
                  "max": 360,
                  "min": -360,
                  "mode": "mod"
                },
                "size": {
                  "fixed": 5,
                  "max": 15,
                  "min": 2
                },
                "symbol": {
                  "fixed": "img/icons/marker/plane.svg",
                  "mode": "fixed"
                },
                "symbolAlign": {
                  "horizontal": "center",
                  "vertical": "center"
                },
                "textConfig": {
                  "fontSize": 12,
                  "offsetX": 0,
                  "offsetY": 0,
                  "textAlign": "center",
                  "textBaseline": "middle"
                }
              }
            },
            "location": {
              "mode": "auto"
            },
            "name": "Layer 4",
            "tooltip": true,
            "type": "markers"
          }
        ],
        "tooltip": {
          "mode": "details"
        },
        "view": {
          "allLayers": true,
          "id": "north-america",
          "lat": 40,
          "lon": -100,
          "zoom": 4
        }
      },
      "pluginVersion": "11.0.0-67977",
      "targets": [
        {
          "dataset": "iox",
          "datasource": {
            "type": "influxdb",
            "uid": "fdfg5thhknb40f"
          },
          "editorMode": "builder",
          "format": "table",
          "rawSql": "SELECT \"aircraft_id\", \"lat\", \"lon\", \"time\" FROM \"adsbicaoNEW\" WHERE \"time\" >= $__timeFrom AND \"time\" <= $__timeTo ",
          "refId": "A",
          "sql": {
            "columns": [
              {
                "parameters": [
                  {
                    "name": "aircraft_id",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "lat",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "lon",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "time",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              }
            ],
            "groupBy": [
              {
                "property": {
                  "type": "string"
                },
                "type": "groupBy"
              }
            ]
          },
          "table": "adsbicaoNEW"
        }
      ],
      "title": "Tracked Flights",
      "type": "geomap"
    },
    {
      "datasource": {
        "type": "influxdb",
        "uid": "fdfg5thhknb40f"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "custom": {
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 0,
        "y": 16
      },
      "id": 3,
      "options": {
        "basemap": {
          "config": {},
          "name": "Layer 0",
          "type": "default"
        },
        "controls": {
          "mouseWheelZoom": true,
          "showAttribution": true,
          "showDebug": false,
          "showMeasure": false,
          "showScale": false,
          "showZoom": true
        },
        "layers": [
          {
            "config": {},
            "location": {
              "mode": "auto"
            },
            "name": "Layer 1",
            "tooltip": true,
            "type": "osm-standard"
          },
          {
            "config": {
              "blur": 15,
              "radius": 5,
              "weight": {
                "fixed": 1,
                "max": 1,
                "min": 0
              }
            },
            "name": "Layer 2",
            "tooltip": true,
            "type": "heatmap"
          }
        ],
        "tooltip": {
          "mode": "details"
        },
        "view": {
          "allLayers": true,
          "id": "north-america",
          "lastOnly": false,
          "lat": 40,
          "layer": "Layer 1",
          "lon": -100,
          "zoom": 4
        }
      },
      "pluginVersion": "11.0.0-67977",
      "targets": [
        {
          "dataset": "iox",
          "datasource": {
            "type": "influxdb",
            "uid": "fdfg5thhknb40f"
          },
          "editorMode": "builder",
          "format": "time_series",
          "rawSql": "SELECT \"lat\", \"lon\", \"aircraft_id\", \"altitude\", \"time\" FROM \"adsbicaoNEW\" WHERE \"time\" >= $__timeFrom AND \"time\" <= $__timeTo ",
          "refId": "A",
          "sql": {
            "columns": [
              {
                "parameters": [
                  {
                    "name": "lat",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "lon",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "aircraft_id",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "altitude",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "time",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              }
            ],
            "groupBy": [
              {
                "property": {
                  "type": "string"
                },
                "type": "groupBy"
              }
            ]
          },
          "table": "adsbicaoNEW"
        }
      ],
      "title": "Heatmap Activity",
      "type": "geomap"
    },
    {
      "datasource": {
        "type": "influxdb",
        "uid": "fdfg5thhknb40f"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "custom": {
            "align": "auto",
            "cellOptions": {
              "type": "auto"
            },
            "inspect": false
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green"
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 0,
        "y": 24
      },
      "id": 2,
      "options": {
        "cellHeight": "sm",
        "footer": {
          "countRows": false,
          "enablePagination": true,
          "fields": "",
          "reducer": [
            "sum"
          ],
          "show": false
        },
        "showHeader": true
      },
      "pluginVersion": "11.0.0-67977",
      "targets": [
        {
          "dataset": "iox",
          "datasource": {
            "type": "influxdb",
            "uid": "fdfg5thhknb40f"
          },
          "editorMode": "builder",
          "format": "table",
          "rawSql": "SELECT \"callsign\", \"altitude\", \"lat\", \"lon\", \"time\" FROM \"adsbicaoNEW\" WHERE \"time\" >= $__timeFrom AND \"time\" <= $__timeTo ",
          "refId": "A",
          "sql": {
            "columns": [
              {
                "parameters": [
                  {
                    "name": "callsign",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "altitude",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "lat",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "lon",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              },
              {
                "parameters": [
                  {
                    "name": "time",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              }
            ],
            "groupBy": [
              {
                "property": {
                  "type": "string"
                },
                "type": "groupBy"
              }
            ]
          },
          "table": "adsbicaoNEW"
        }
      ],
      "title": "Last Seen Data",
      "type": "table"
    },
    {
      "datasource": {
        "type": "influxdb",
        "uid": "fdfg5thhknb40f"
      },
      "description": "This is the metric on which we determine your rewards.",
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green"
              },
              {
                "color": "purple",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 0,
        "y": 32
      },
      "id": 1,
      "options": {
        "colorMode": "value",
        "graphMode": "area",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "auto",
        "wideLayout": true
      },
      "pluginVersion": "11.0.0-67977",
      "targets": [
        {
          "dataset": "iox",
          "datasource": {
            "type": "influxdb",
            "uid": "fdfg5thhknb40f"
          },
          "editorMode": "builder",
          "format": "table",
          "rawSql": "SELECT COUNT(\"aircraft_id\") FROM \"adsbicaoNEW\" WHERE \"time\" >= $__timeFrom AND \"time\" <= $__timeTo ",
          "refId": "A",
          "sql": {
            "columns": [
              {
                "name": "COUNT",
                "parameters": [
                  {
                    "name": "aircraft_id",
                    "type": "functionParameter"
                  }
                ],
                "type": "function"
              }
            ],
            "groupBy": [
              {
                "property": {
                  "type": "string"
                },
                "type": "groupBy"
              }
            ]
          },
          "table": "adsbicaoNEW"
        }
      ],
      "title": "DeFli Score",
      "type": "stat"
    }
  ],
  "refresh": "10s",
  "schemaVersion": 39,
  "tags": [],
  "templating": {
    "list": []
  },
  "time": {
    "from": "now-5m",
    "to": "now"
  },
  "timeRangeUpdatedDuringEditOrView": false,
  "timepicker": {},
  "timezone": "browser",
  "title": "BUCKETID",
  "uid": "ASSIGNED",
  "version": 2,
  "weekStart": ""
}
 ```
