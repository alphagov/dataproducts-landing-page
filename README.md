# dataproducts-landing-page
Landing page for various services offered by the Data Products team

## Render locally

Because this is a static site, you can view it by opening `index.html` in a
browser.

## Docker

Build the docker image.

```
docker build -t dataproducts-landing-page .
```

Run the container and then open http://localhost:8080/ in a browser.

```
docker run --name dataproducts-landing-page --publish=8080:8080 dataproducts-landing-page:latest
```

Tag the image.

```
docker tag dataproducts-landing-page europe-west2-docker.pkg.dev/data-services-product-hub/cloud-run-source-deploy/dataproducts-landing-page:latest
```

Push the image to the Artifact Repository.

```
docker push europe-west2-docker.pkg.dev/data-services-product-hub/cloud-run-source-deploy/dataproducts-landing-page
```

Deploy to Cloud Run (from the image in the Artifact Repository).

```
gcloud --project=data-services-product-hub run deploy dataproducts-landing-page --region=europe-west2 --no-allow-unauthenticated --image=europe-west2-docker.pkg.dev/data-services-product-hub/cloud-run-source-deploy/dataproducts-landing-page:latest
```

Deploy to Cloud Run (from the local directory).

```
gcloud --project=data-services-product-hub run deploy dataproducts-landing-page --region=europe-west2 --no-allow-unauthenticated --source .
```
