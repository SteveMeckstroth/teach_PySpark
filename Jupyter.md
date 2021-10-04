# Using Jupyter
Since this tutorial is about actually using Python, Spark, and Jupyter
we can skip the process of downloading/installing python, java, and all
the dependencies by simply using a Docker image someone else put together.


The pull command will only download a copy of the image.  It does not run 
the image as a container.
```
docker pull jupyter/pyspark-notebook
```
If you would like information on the available jupyter images you can view the [documentation](https://jupyter-docker-stacks.readthedocs.io/en/latest/index.html).

After downloading, then run the image.

```
docker run -it --rm -p 8888:8888 jupyter/pyspark-notebook
```
A quick breakdown of this command.
```docker run``` tells Docker to run an image as a container.
```-it``` Runs the container with an Interactive Terminal so we can see the debug messages from Jupyter.
```--rm``` Delete the container after it exists.  By default Docker will save a copy of every container just in case you wanted to restart it.
```-p 8888:8888``` Exposes the container's port 8888 to the host pc's port 8888.  If your host PC is already using port 8888, you can map it to any other available port your would like such as 12345 by amending the command to ```-p 8888:12345```.
There are many, many more options available in the Docker run command.  For a complete list visit the [Documentation](https://docs.docker.com/engine/reference/commandline/run/)

When it starts you will see quite a bit of text printed to the terminal window.  At the bottom you should see a link that looks something like http://127.0.0.1:8888/?token=651626542999e384023e1b9f06a73d5826cf65e4eabf8be4.  Your token will be different everytime you start a notebook.  Just copy the full link, and paste it in your browser.

![img_2.png](img_2.png)