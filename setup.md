# Software Setup

In order to be able to execute the notebooks with the tutorials, you should configure your workspace following one of the options below. If you have trouble or need help setting the workspace up, you can contact the GW community at [ask.igwn.org](https://ask.igwn.org). **We encourage the participants to test the following steps beforehand of the hands-on sessions.**

The various options are listed in order of difficulty. However, whenever possible, we recommend the participants with some experience with Python environments to follow [Option 3](#option3), installing the requirements on their laptops and executing the tutorial notebooks from there. This has the advantage of avoiding any possible issue with online servers, including unstable internet connection or uneven memory and server availability, both on Colab and on MyBinder.

## Option 1: Run in mybinder

<img src='https://www.wispresort.com/uploadedImages/Winter/easy.png' width=20 /> Easy (No software installation; Works for any OS)

<img src='./share/video-icon.png' width=18 /> [Video instructions](https://drive.google.com/file/d/1QkjdG6IHeTWq2XtPreakLydaZMedJCrX/view?usp=sharing)

To run the notebooks, click the badge:  [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/gw-odw/odw-2022/HEAD)

This will build a Docker image (if not already present) with the dependency file `environment.yml`. Then a [JupyterHub](https://jupyterhub.readthedocs.io/en/latest/) server will be open hosting the contents of the `gw-odw/odw-2022` repo. To find the Tutorials, click the folders `Tutorials`, and then `Day 1`, `Day 2`, or `Day 3` to find the tutorials.

## Option 2: Google Colab

<img src='https://www.wispresort.com/uploadedImages/Winter/easy.png' width=20 /> Easy (No software installation; Works for any OS)

<img src='./share/video-icon.png' width=18 /> [Video instructions](https://drive.google.com/file/d/17jYkGoVIavJa1B_Fbi6xK2D3jCFQT-A7/view?usp=sharing)

1. To run the notebooks, click the badge:  [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gw-odw/odw-2022/blob/main/)   

2. Double click the notebook of your choice

3. At the top of the notebook, uncomment any `pip install` commands by removing the `#`

    `#! pip install -q 'gwosc==0.5.4`  <-- Remove the `#` and run

    **Warnings:** a couple of warning messages are likely to show up, both of them are harmless.
    
    - `Unrecognized runtime "igwn-py3#"; defaulting to "python3"`
       
      This pop-up simply notifies you that this notebook has been created with a Python environment different than the default one of Colab. That's not a big deal because you will install all the missing dependencies with the command above.
      
    - `WARNING: This notebook was not authored by Google.`

      Same as before. Just close the pop-up and go ahead without worrying too much.

4. Click `run all` from the `runtime` menu at the top

<div class="alert alert-info">If you are not familiar with google Colab, you can beforehand take a look at the guides offered by Google at  <a href="https://colab.research.google.com/notebooks/">this link</a>, in the "Examples" tab. In particular, it is recommended to have a certain understanding of the main features of notebooks, which you can learn in <a href="https://colab.research.google.com/notebooks/basic_features_overview.ipynb">this tutorial</a>.</div>

<a name="option3">

## Option 3: You have a Linux or Apple/Mac computer -- Use conda

</a>

<img src='https://www.wispresort.com/uploadedImages/Winter/intermediate.png' width=20 /> Intermediate (Some software installation; Will not work on Windows PC)

<img src='./share/video-icon.png' width=18 /> [Video instructions](https://drive.google.com/file/d/1YZcaY-35JiHXOH4unRe5ECSeDl8IZFZy/view?usp=sharing)

This workshop uses [Python version 3.9](https://www.python.org/downloads/release/python-390/). We recommend creating a [Python virtual environment](https://docs.python.org/3.9/tutorial/venv.html) and install all the package dependencies there. The official environment with all the required packages is [igwn-py39](https://computing.docs.ligo.org/conda/environments/igwn-py39/), available from the International Gravitational-Wave Observatory Network ([IGWN](https://computing.docs.ligo.org/guide/)) community website. 

This guide will walk you through the configuration of this environment with [Conda](https://www.anaconda.com/). 

1. Install miniconda:
   
    - Visit the website https://conda.io/en/latest/miniconda.html
    - Choose the version for Python 3.9
    - Follow the [installation instructions](https://conda.io/projects/conda/en/latest/user-guide/install/
) for your operating system: 
        - [Linux](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)
        - [macOS](https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html)
    
   You may need to restart your computer after installation.

2. To install the full [igwn-py39 environment](https://computing.docs.ligo.org/conda/environments/igwn-py39/) (recommended), download the YML dependencies file for the IGWN website:
   * [YML file for Linux](https://computing.docs.ligo.org/conda/environments/linux/igwn-py39.yaml)
   * [YML file for macOS](https://computing.docs.ligo.org/conda/environments/osx/igwn-py39.yaml)

3. Add the conda-forge channel

    `conda config --add channels conda-forge`

4. Create the environment. <br/>
   
   `conda env create --file igwn-py39.yaml`
   
5. Clone the workshop git repo 

    `git clone https://github.com/gw-odw/odw-2022.git`

6. Move into the directory with the workshop git repo 

    `cd odw-2022`
    
7. Activate the environment. <br/>

   `conda activate igwn-py39`
   
8. Build a custom [jupyter kernel](https://ipython.readthedocs.io/en/stable/install/kernel_install.html) using the command 

  `python -m ipykernel install --user --name igwn-py39 --display-name "Python (igwn-py39)"`
  
- For Windows users working with WSL, a change is needed to access the notebook.
Run `jupyter notebook --generate-config` to generate the file ~/.jupyter/jupyter_notebook_config.py, and in this file change the following line:
**#c.NotebookApp.use_redirect_file = True** to **#c.NotebookApp.use_redirect_file = False**

9. Start the Jupyter notebook server <br/>
  `jupyter notebook` and select the kernel `igwn-py39` if this is not done by default.

**Notebooks:**
If you are not familiar with Jupyter notebooks, google one of the many introductory guides available on the internet, like <a href="https://realpython.com/jupyter-notebook-introduction/">this one</a>. Also, taking a look at the <a href="https://colab.research.google.com/notebooks/basic_features_overview.ipynb">Examples</a> offered by Google Colab can be helpful.

## Option 4: Linux install on Windows 10 with dedicated app (Windows 10 only)

<img src='https://www.wispresort.com/uploadedImages/Winter/hard.png' width=20 /> Advanced (For Windows 10)

Install a Linux distribution on your Windows system. 
See instructions over [here](https://ask.igwn.org/t/run-the-workshops-under-windows-with-wsl/84).
Please indicate to us any problem or misunderstanding that you meet when following these steps. You can make comment directly on [ask.igwn.org](https://ask.igwn.org/)
