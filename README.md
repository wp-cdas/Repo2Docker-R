# Repo2Docker-R Example Repository

Please check here https://repo2docker.readthedocs.io/en/latest/ for the documentation of Repo2Docker.

This repository is a template for you to use when spawning your custom container on the DSP. Always reference the documentation for Repo2Docker as the primary source for using this tool but, by looking through the configuration files found here, you can get an idea of what is possible in your container.

The general idea of Repo2Docker on the DSP is that you can build the environment you want before logging in to work on the DSP. Through the use of various files in the repository you can include other files, install dependencies, other packages, and even clone external repositories. When you log on to the DSP you merely provide the GitHub URL and the DSP will do the rest and launch you into your custom container. You can even make changes to the files in your container and push them back to the original GitHub repository.

This is both simpler and harder than the Python version. Repo2Docker is primarily designed to get you working in JupyterLab but having the RStudio launcher from JupyterLab is a nice feature. Configuring this is simpler because there is only one configuration file (for libraries): environment.yml. It's harder because if you want to do anything else, you have to get into the Dockerfile. I have commented out a few example lines at the end of the Dockerfile if you want to do things like: install additional system packages (using apt), clone repositories, or copy extra files you've included in your Repo2Docker repo.

* Dockerfile - This is the main component to the repository. There is going to be a lot in this that may look advanced but it's all well documented by Docker. Check the end of the file for my (commented out) examples of changes you could make.  
* environment.yml - Uses Conda to install an environment that includes the packages you need for your project. Please check the Anaconda repository website to ensure you've named your libraries correctly.   
* /bin - This folder contains various scripts for getting JupyterLab running. Don't worry about these things.  
* /config - This folder contains the configuration file for the JupyterLab server. Don't worry about this either.  
