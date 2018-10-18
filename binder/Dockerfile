FROM jupyter/base-notebook

USER root

RUN conda install -c conda-forge --quiet --yes \
    basemap=1.1.0=py36_4 \
    numpy \
    matplotlib \
    pyophidia && \
    conda clean -tipsy 

RUN  apt-get update && \
     apt-get install -y iputils-ping 

EXPOSE 8080/tcp
EXPOSE 8080/udp 

EXPOSE 80/tcp
EXPOSE 80/udp

EXPOSE 11732/tcp
EXPOSE 11732/udp 

COPY binder/Frost+Days.ipynb ~/home/jovyan/work/

RUN chown -R jovyan:users /home/jovyan/work/
