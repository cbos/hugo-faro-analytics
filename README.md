# Hugo analytics module with Grafana Faro

By default you can use Google Analytics with Grafana. But there are alternatives.   
This module integrates Grafana Faro observability library with Hugo.

This module is inspired by https://github.com/hugomods/plausible-analytics

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

## Add to a page header

```
{{ partial "faro-analytics/assets/js" . }}
```