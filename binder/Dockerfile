FROM jupyter/base-notebook

USER root

RUN conda install -c conda-forge --quiet --yes \
    basemap=1.1.0=py36_4 \
    numpy \
    matplotlib \
    pyophidia && \
    conda clean -tipsy 

RUN  apt-get update &&\

     apt-get install -y libgl1-mesa-glx libx11-xcb1 qt5-default

ADD binder/Frost+Days.ipynb ~/home/jovyan/work/

ADD . ~/home/jovyan/work

RUN chown -R jovyan:users /home/jovyan/work/
