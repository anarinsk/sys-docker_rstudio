# Setup of RStudio-docker 

## How to activate 

This repo is to manage RStduio with docker setting. Usually, I run RStudio with docker-compose. 

```shell
sudo docker-compose up -d 
```

## Environment setting is as follows 

```
 rstudio:
        image: rocker/verse:latest
       #image: rocker/verse:4.0.2
        volumes:
            - /mnt/e/github:/home/rstudio/anari-github
        ports:
            - "8787:8787"
        environment:
            - ROOT=TRUE
            - PASSWORD=1022
        container_name: rstudio
```

Should-be customed parts are 

* In `volumes` 
  * `/mnt/e/github:/home/rstudio/anari-gihub`
  * "your-local-dir" : "your-docker-dir"

* In `environment`
  * `ROOT=TRUE` is to enable root in docker 
  * `PASSWORD=1022` is login password  


## Updated 

- `setup.sh`
  - Bootsup bash script 
  - If you see "sudo error", ignore it. 
