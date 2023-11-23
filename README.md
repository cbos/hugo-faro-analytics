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

## Site Configuration TOML

| Parameter   | type   | required | description                                                                                  |  
|-------------|--------|----------|----------------------------------------------------------------------------------------------|
| endpoint    | string | yes      | Url of the Faro collector like https://faro-collector-prod-eu-west-2.grafana.net/collect/xxx | 
| name        | string | yes      | Name of the application                                                                      |
| version     | string | no       | Version to report, can be used to make distinction between releases                          | 

Environment like `production` or `development` is automatically added, as [hugo.Environment](https://gohugo.io/functions/hugo/environment/) variable is used.

```toml
[params]
[params.faro_analytics]
    endpoint = "https://faro-collector-..."
    name = "name"
    version = "1.0.0"
```

## Page Configuration TOML

If you want to exclude a page from analytics, you can configure that per page.

| Parameter   | type    | required | description                                                           |  
|-------------|---------|----------|-----------------------------------------------------------------------|
| enabled     | boolean | no       | By default analysis for a page is abled. Make it `false` to disable it | 

```yaml
faro_analytics:
  analyze: true
```