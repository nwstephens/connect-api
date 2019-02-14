# Deploying content using the RStudio Connect API

Programmatic deployment with the RStudio Connect API. See the [user guide](https://docs.rstudio.com/connect/user/cookbook.html#cookbook-deploying) for more information.

### The deployment process

Deployments involve describing the development environment then recreating the environment on RStudio Connect. 

1. Describe the environment
    * `Rscript -e 'rsconnect::writeManifest()'`
2. Upload the bundle
    * `tar` -- Bundle all the files
    * `POST /content` -- Retrieve a guid
    * `POST /upload` -- Upload the bundle 
3. Recreate the environment
    * `POST /deploy`
