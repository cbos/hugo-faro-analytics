# Hugo analytics module with Grafana Faro

By default you can use Google Analytics with Grafana. But there are alternatives.   
This module integrates Grafana Faro observability library with Hugo.

##
```shell
git submodule add https://github.com/cbos/hugo-faro-analytics.git themes/faro-analytics
```

## Enable module

```toml
[module]
[[module.imports]]
    path = 'faro-analytics'
```


```
{{ partial "faro-analytics/assets/js" . }}

```