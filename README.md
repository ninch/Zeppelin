# Zeppelin
Personal Zeppelin memo

## Do you have Docker installed?
1. You can download Docker from [HERE](https://www.docker.com/community-edition#/download)
2. Goto [Docker Store](https://store.docker.com/) to create a new account

## Download Zeppelin Docker Image from Docker Store
Login to docker\
`docker login`

Pull docker image\
`docker pull apache/zeppelin`

> If the latest tag doesn't work, try other [tags](https://store.docker.com/community/images/apache/zeppelin/tags)\
> For example, `docker pull apache/zeppelin:0.7.3`

## Run it
Start docker container with persistent logs and notebook directories\
`docker run -p 8080:8080 --rm -v $PWD/logs:/logs -v $PWD/notebook:/notebook -e ZEPPELIN_LOG_DIR='/logs' -e ZEPPELIN_NOTEBOOK_DIR='/notebook' --name zeppelin apache/zeppelin:0.7.3`

On another terminal, you can confirm image and container\
```
$ docker image ls
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
apache/zeppelin     0.7.3               393fb4938510        5 months ago        2.42GB
```

```
docker container ls
CONTAINER ID        IMAGE                   COMMAND                  CREATED             STATUS              PORTS                    NAMES
5185cc34372d        apache/zeppelin:0.7.3   "/usr/bin/tini -- bi…"   About an hour ago   Up About an hour    0.0.0.0:8080->8080/tcp   zeppelin
```

Get into the container\
`docker exec -it zeppelin bash `

Install python packages\
`$ pip install flask`

Install R packages\
`R -e "install.package('knitr', repos='http://cran.us.r-project.org')"`


## Welcome to Zeppelin
[OPEN ZEPPELIN](http://localhost:8080/)
