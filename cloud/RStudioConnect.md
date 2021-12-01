# RStudio Connect Notes

[RStudio Connect](https://www.rstudio.com/products/connect/) is a Platform as a Service (PaaS) that publishes a teams data products with the push of a button. This supports common data science workflows to get iteractive dashboards or APIs out to decision makers quickly.

## What is needed to get started

* RStudio Connect server instance running for your team

* Shiny/Dash/Flask/FastAPI application to be hosted

* API key 

* `rsconnect` CLI tool or other options to deploy

## How to deploy a Dash app

```sh
# Setup variables
# rstudio connect api token
export CONNECT_API_KEY=<KEY HERE>

# Create server with credentials
rsconnect add --server <SERVER URL> --name <NAME> --api-key $CONNECT_API_KEY

# Deployment bundle
rsconnect deploy dash -n <NAME> --entrypoint app:app .

```

## Potential issues

To allow your dash app to find the assets (javascript/css) you could use the url_base_pathname parameter (after you get your connect id):

```python
url_base = os.environ.get('URL_BASE', '/content/<CONNECT ID>/')

...

app = dash.Dash(__name__,
                url_base_pathname=url_base,
                ...
                )
```

## Links

[RStudio Connect Dash docs](https://docs.rstudio.com/connect/user/dash/)