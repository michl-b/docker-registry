# docker registry
> run a own private docker registry in a container with a web-frontend

## run
```bash
# clone git repository
git clone https://github.com/michl-b/docker-registry.git

# create volume folder for regitry backend services
cd docker-registry
mkdir volume

# run both containers detached
docker-compose up -d
```
## stop
```bash
# run both containers
docker-compose stop
```

## usage
### push a image
```bash
# First, make sure you have the "ubuntu" repository:
docker pull hello-world

# Then, find the image id that corresponds to the ubuntu repository
docker images
hello-world   latest  48b5124b2768  2 months ago  1.84 kB

# Almost there!
# Tag to create a repository with the full registry location.
# The location becomes a permanent part of the repository name.
docker tag 48b5124b2768 localhost:5000/hello-world

# Finally, push the new repository to its home location.
docker push localhost:5000/hello-world
```

### pull a image
```bash
# load the image 'hallo-world' from your private registry
docker pull localhost:5000/hello-world
```
