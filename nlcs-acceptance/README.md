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
