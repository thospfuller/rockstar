#
# This script sets up rocker/rstudio with rJava, RJSONIO, JDK 11, drat, and packrat.
#
# See: quay.io
#
# ----- Build -----
#
# docker build docker/rocker/rstudio/ -t rockstar/rstudio[:v2]
#
# ----- Testing begins -----
#
# docker stop $(docker ps -aq) && docker rm $(docker ps -aq) && docker rmi $(docker images -q)
#
# docker stop $(docker ps -aq)
# docker rm $(docker ps -aq)
# docker rmi $(docker images -q)
# docker build ./docker
#
# -----
#
# docker run -d -p 8787:8787 -e PASSWORD=password --name rsrstudio -i -t [id]
# docker exec -it rsrstudio /bin/bash
#
# library(rJava)
# rJava::.jinit()
# rJava::.jnew('java/lang/Object')
#
FROM rocker/rstudio:latest

RUN su -
RUN apt-get update
RUN sudo apt-get install -y git
RUN sudo apt-get -y install apt-utils
RUN sudo apt-get -y install nano
RUN sudo apt-get -y install openjdk-11-jre openjdk-11-jdk

RUN R CMD javareconf

COPY Rprofile /home/rstudio/.Rprofile
COPY welcome.txt /home/rstudio/.welcome.txt
COPY bash_profile /home/rstudio/.bash_profile

RUN sudo chown -R rstudio:rstudio /home/rstudio/.Rprofile
RUN sudo chown -R rstudio:rstudio /home/rstudio/.welcome.txt
RUN sudo chown -R rstudio:rstudio /home/rstudio/.bash_profile

RUN chown rstudio:rstudio /usr/local/lib/R/
RUN chown -R rstudio:rstudio /usr/local/lib/R/

# Not working:
#
# RUN R -e 'install.packages("rJava")'
#
# So we use apt-get instead.
#
# See: https://stackoverflow.com/questions/3311940/r-rjava-package-install-failing
#
RUN sudo apt-get -y install r-cran-rjava

RUN R -e 'install.packages("drat")'
RUN R -e 'install.packages("RJSONIO")'
RUN R -e 'install.packages("packrat")'
RUN R -e 'install.packages("rJava")'

RUN sudo apt-get update

RUN chown -R rstudio:rstudio /usr/local/lib/R/site-library/*

RUN cd /home/rstudio/
