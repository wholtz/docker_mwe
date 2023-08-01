FROM mambaorg/micromamba:1-jammy AS test

USER root

RUN apt-get update --fix-missing && \
    apt-get install -y libgl1-mesa-dev ffmpeg libsm6 libxext6 curl && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER $MAMBA_USER

RUN micromamba install -y -n base -c conda-forge numpy

ARG MAMBA_DOCKERFILE_ACTIVATE=1

RUN python -c "import numpy"

RUN micromamba list
