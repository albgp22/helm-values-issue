# Helm import values issue in v3.8.2

## Structure

- He have two charts: one application chart (*app1*) and one library chart (*library*). We import a value *service.port* from the library chart, changing its value from 80 to 81.

## Rendering the chart in Helm v3.8.1

```
$ helm381 template . | grep port
  ports:
    - port: 81
          ports:
              port: http
              port: http
```

## Rendering the chart in Helm v3.8.2

```
$ helm382 template . | grep port
  ports:
    - port: 80
          ports:
              port: http
              port: http
```

As we can see, the imported values is ommited in this helm version.

