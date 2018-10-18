FROM jupyter/base-notebook
RUN conda install -c conda-forge --quiet --yes \
    basemap=1.1.0=py36_4 \
    numpy \
    matplotlib \
    pyophidia && \
    conda clean -tipsy 
USER root
RUN  apt-get update &&\

     apt-get install -y libgl1-mesa-glx libx11-xcb1 qt5-default
RUN chown -R jovyan:users /home/jovyan/work/

WORKDIR ~/home/jovyan/work

