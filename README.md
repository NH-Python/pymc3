## Probabilistic Programming With PyMC3

Presentation given Sept. 26, 2019

### Viewing the presentation

The main presentation is in the ProbabilisticProgrammingPyMC3.pdf file, which refers to Jupyter Notebooks (in the .ipynb files). All of the elements of the presentation can be viewed directly from this github repository with a browser by double-clicking on the file of interest.

### Running the Jupyter Notebooks

Running the Jupyter Notebooks, which contain Python code, or creating your own, requires a Jupyter Notebook server and PyMC3, Arviz, RISE and their dependencies. It can be tricky getting everything to work (version mismatches are a typical problem). It is suggested that starting with a clean Python installation with only the necessary dependencies works best as it minimizes opportunities for conflicting version numbers among the dependencies.

#### Default installation

Basic directions are given on the respective websites:

PyMC3:  https://pymc3.readthedocs.io/en/latest/#Installation  
Arviz:  https://arviz-devs.github.io/arviz/  
RISE:   https://github.com/damianavila/RISE

#### Docker-based Jupyter Notebook Server

The Jupyter Notebook server used for the presentation is available as a Docker image on DockerHub.  It adds PyMC3, Arviz and RISE to the excellent jupyter/datascience-notebook image maintained by the Jupyter Docker Stacks project. Docker is software that manages containers, which are isolated Linux instances that are similar to virtual machines but much more resource efficient. Data created in the containers is frequently saved by mounting a directory on the host on a directory inside the container.

The following directions are written for Mac OSX, and are likely very similar for other platforms.

## Setting up a Jupyter Notebook server with PyMC3, Arviz and RISE

1. Create a directory in your host home directory for your data (I've used PyMC3Models), and give everyone read-write access to only that directory.  If you are concerned about giving _everyone_ write access to that directory, you can create a user named jovyan and give jovyan read-write access. The Jupyter server inside the container runs as jovyan, as defined by the Jupyter Docker Stacks project.

2. Click the green "Clone or Download" button above, and download this repository as a zip file. Extract the files and place them in your PyMC3Models directory.

3. Make sure Docker Desktop is installed and running (https://www.docker.com/products/docker-desktop)

4. From a terminal window, get the PyMC3 docker image from dockerhub:

      docker pull scalafan/pymc3-arviz:version_1
      
5. Verify that you have the image using:
      
      docker images
       
6. From a terminal window, run the image you just pulled (do not change the /home/jovyan part):
 
      docker run -p 8888:8888 -v /Users/yourhome/PyMC3Models:/home/jovyan scalafan/pymc3-arviz:version_1
 
7. Copy and paste the provided URL into your browser address bar.
   Any notebooks you create will be saved in the PyMC3Models directory on the host.
   
8. Enter Ctrl-C in the terminal window to shut down the notebook server.

9. You may wish to clean up the stopped Docker container:
  
      docker ps –a  
      
      docker rm containername
  
