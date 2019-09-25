
FROM jupyter/datascience-notebook:1386e2046833

# Install PyMC3 and Arviz.
RUN conda install --quiet --yes \
    'mkl-service' \
    'pymc3' \
    'arviz' \
    && \
    conda clean --all -f -y && \
    fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER

# Install RISE for notebook presentations
RUN conda install -c damianavila82 rise