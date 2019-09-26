## Probabilistic Programming With PyMC3

Presentation on PyMC3 Sept. 26, 2019

### Viewing the presentation

The main presentation is in the ProbabilisticProgrammingPyMC3.pdf file, which refers to Jupyter Notebooks (in the .ipynb files). All of the elements of the presentation can be viewed directly from this github repository with a browser by double-clicking on the file of interest.

### Running the Jupyter Notebooks

Running the Jupyter Notebooks, which contain Python code, requires a Jupyter Notebook server and PyMC3, Arviz, RISE and their dependencies. It can be tricky getting everything to work (version mismatches are a typical problem). It is suggested that starting with a clean Python installation with only the necessary dependencies works best as it minimizes opportunities for conflicting version numbers among the dependencies.

#### Default installation

Basic directions are given on the respective websites:

https://pymc3.readthedocs.io/en/latest/#Installation
https://arviz-devs.github.io/arviz/
https://github.com/damianavila/RISE

#### Docker-based Jupyter Notebook Server



The Jupyter Notebooks are dependent on PyMC3, Aviz and the RISE presentation module, as well as on their dependencies. The easiest way to create a Jupyter Notebook server with the required software to run the notebooks is to pull a Docker image the author has created based on jupyter/datascience-notebook.

## Setting up a Jupyter Notebook server with PyMC3, Arviz and RISE

1. Make sure Docker is installed
2. From a terminal window, get a docker image from dockerhub:

      docker pull scalafan/pymc3-arviz:version_1  
      
3. From a terminal window, run the image you just pulled:
 
      docker run -p 8888:8888 -v /Users/yourhome/PyMC3Models:/home/jovyan scalafan/pymc3-arviz:version_1
 
4. Copy and paste the provided URL into your browser address bar.
   Any notebooks you create will be saved in the PyMC3Models directory.
   The host directory (PyMC3Models) must be shared in Docker, and user jovyan must have read and write privileges.
5. Enter Ctrl-C in the terminal window to shut down the notebook server.
6. You may wish to clean up the stopped Docker container:
  
      docker ps –a  
      
      docker rm containername
  
