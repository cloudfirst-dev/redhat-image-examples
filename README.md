# S2I Image Consumption
This repository will show different ways to consume the provided RHEL and UBI images without using the S2I functionality.  It will demonstrate how to leverage the benefits provided with the entrypoint and starter scripts and configure things such as user creation, and necessary permissions when running in a non-root container such as OpenShift.

## Example Structure

```
- language directory (ex. java)
-- app (source code of sample)
-- Dockerfile.rhel7 (dockerfile consuming RHEL7 base image)
-- Dockerfile.ubi (dockerfile consuming UBI base image)
``` 

## Running Examples
1. Change into the language of choice ex. `cd java`
1. Build the docker image with either docker or buildah the examples below show using the UBI image
    1. `docker build -t imagename -f Dockerfile.ubi .`
    1. `buildah `

## Examples
### [Java](./java)
This will show using a multistage dockerfile that will build a maven application and place it into a runtime container leveraging the benefits of the Java S2I image.  One thing that is noteworthy is setting up the garbage collection and min and max heap sizes appropriately based on the resource requests and limits defined for the pod.
