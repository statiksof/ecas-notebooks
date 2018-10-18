FROM jupyter/base-notebook

# create user with a home directory
ARG NB_USER
ARG NB_UID
ENV USER ${NB_USER}
ENV HOME /home/${NB_USER}

RUN adduser --disabled-password \
    --gecos "Default user" \
    --uid ${NB_UID} \
    ${NB_USER}
WORKDIR ${HOME}

RUN conda install -c conda-forge --quiet --yes \
    basemap=1.1.0=py36_4 \
    numpy \
    matplotlib \
    pyophidia && \
    conda clean -tipsy 

USER root
RUN  apt-get update &&\

     apt-get install -y libgl1-mesa-glx libx11-xcb1 qt5-default

ADD ./Frost+Days.ipynb ~/home/jovyan/work/

RUN chown -R jovyan:users /home/jovyan/work/
