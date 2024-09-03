# Semmtech

## LD Viewer configuration and deployment project

Details about this setup for the Linked Data Viewer:

- Client: 
- Description: A Viewer for Demo Purposes


### Configuring the LD Viewer

The viewer is loading the configurations from the folders [/app/viewer/client](./app/viewer/client) and [/app/viewer/server](./app/viewer/server) respectively.

Update the `volume` section within the [docker-compose.yml](./app/docker-compose.yml) file to ensure your configuration files are picked up by the LD Viewer.


### Local testing

Run the following command from within the [/app](./app) directory:

```bash
docker-compose up
```

### Configuring for AWS deployment

Once the application has been properly set up and the client- and server configuration files have been tested, make sure to update the `build.xml`. This file is used during building and deploying and should be updated with the appropriate values.

Open the `build.xml` file, and update the following parameters:

- **viewer.name**: Short name of the viewer instance (used in naming AWS resources)
- **viewer.version**: Version identifier (only used in naming AWS resources - so not in-app or Docker image selection)
- **viewer.hostname**: The (full) URL of the viewer, like `https://semmtech.ldviewer.com` (no trailing slash)
- **environment.id**: The ElasticBeanstalk environment ID, e.g. `e-awv7bm4k55`
- **environment.name**: The ElasticBeanstalk environment name, e.g. `semmtech-viewer-env`


### Uploading version to AWS

This step is only intended for setting up the application environment directly in AWS and is inteded for admins only.

In order to upload a Elastic Beanstalk application version to AWS, run the following command. 

```bash
aws-vault exec PROFILE -- ant upload
``` 

Should you also directly want to update a running environment, you could instead use:

```bash
aws-vault exec PROFILE -- ant update
```

Make sure you have properly set up the AWS Vault and have the necessary permissions on the AWS semmtech-io account. Check with IT if you have any doubts. 
