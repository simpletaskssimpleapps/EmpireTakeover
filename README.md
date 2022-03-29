# EmpireTakeover

## Installation

1. Install docker desktop from https://hub.docker.com/editions/community/docker-ce-desktop-mac
2. Change directory to the `empiretakeover` folder
```
cd path/to/project/empiretakeover
```
3. Build mkdocs image.

Execute the following command in the terminal using the current directory
```
docker build -t et-mkdocs-img .
```
4. Serve your local environment.

Execute the following command in the terminal after the docker image creation.
```
docker run --name `et-mkdocs-wiki` -p 9090:9090 --volume="$PWD:/app" et-mkdocs-img:latest
```

>**Note:** Use the `-d` flag in the above command to detach your terminal from the running container.

5. Start working. Open http://localhost:9090 to see all your changes.

## Stop mkdocs

1. Open docker's dashboard.
2. Locate the `et-mkdocs-wiki` container and stop it.
Wait until the terminal process stops

## Restart mkdocs

1. Open docker's dashboard
2. Locate the `et-mkdocs-wiki` container and start it

## Create static site

Execute the following command
```
docker run --rm --volume="$PWD:/app" -it et-mkdocs-img:latest mkdocs gh-deploy
```
