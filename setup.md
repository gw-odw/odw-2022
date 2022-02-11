# Software Setup

In order to be able to execute the notebooks with the tutorials, you should configure your workspace following one of the options below. **We encourage the participants to test the following steps beforehand of the hands-on sessions.**

The various options are listed in order of difficulty. However, whenever possible, we recommend the participants with some experience with Python environments to follow [Option 3](#option3), installing the requirements on their laptops and executing the tutorial notebooks from there. This has the advantage of avoiding any possible issue with online servers, including unstable internet connection or uneven memory and server availability, both on Colab and on MyBinder.

## Option 1: Google Colab

<img src='https://www.wispresort.com/uploadedImages/Winter/easy.png' width=20 /> Easy (No software installation; Works for any OS)

<img src='./share/video-icon.png' width=18 /> [Video instructions](https://drive.google.com/file/d/17jYkGoVIavJa1B_Fbi6xK2D3jCFQT-A7/view?usp=sharing)

1. Visit https://colab.research.google.com

2. Click the GITHUB tab

3. Enter "gw-odw/odw-2021" in the search bar, and click enter to search

4. Double click the notebook of your choice

5. At the top of the notebook, uncomment any `pip install` commands by removing the `#`

    `#! pip install -q 'gwosc==0.5.4`  <-- Remove the `#` and run

    **Warnings:** a couple of warning messages are likely to show up, both of them are harmless.
    
    - `Unrecognized runtime "igwn-py3#"; defaulting to "python3"`
       
      This pop-up simply notifies you that this notebook has been created with a Python environment different than the default one of Colab. That's not a big deal because you will install all the missing dependencies with the command above.
      
    - `WARNING: This notebook was not authored by Google.`

      Same as before. Just close the pop-up and go ahead without worrying too much.

6. Click `run all` from the `runtime` menu at the top

<div class="alert alert-info">If you are not familiar with google Colab, you can beforehand take a look at the guides offered by Google at  <a href="https://colab.research.google.com/notebooks/">this link</a>, in the "Examples" tab. In particular, it is recommended to have a certain understanding of the main features of notebooks, which you can learn in <a href="https://colab.research.google.com/notebooks/basic_features_overview.ipynb">this tutorial</a>.</div>

## Option 2: Run in mybinder

<img src='https://www.wispresort.com/uploadedImages/Winter/easy.png' width=20 /> Easy (No software installation; Works for any OS)

<img src='./share/video-icon.png' width=18 /> [Video instructions](https://drive.google.com/file/d/1QkjdG6IHeTWq2XtPreakLydaZMedJCrX/view?usp=sharing)

Just click the button below

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/gw-odw/odw-2021/master)

or visit [mybinder.org](https://mybinder.org/), paste in the "GitHub repository name or URL" cell the following address `https://github.com/gw-odw/odw-2021/`, and hit the `Launch` button. 

This will build a Docker image (if not already present) with the dependency file `environment.yml`. Then a [JupyterHub](https://jupyterhub.readthedocs.io/en/latest/) server will be open hosting the contents of the `gw-odw/odw-2021` repo. Check the Jupyter notebooks with the tutorials for the various days in the corresponding folders. 

<a name="option3">

## Option 3: You have a Linux or Apple/Mac computer -- Use conda

</a>

<img src='https://www.wispresort.com/uploadedImages/Winter/intermediate.png' width=20 /> Intermediate (Some software installation; Will not work on Windows PC)

<img src='./share/video-icon.png' width=18 /> [Video instructions](https://drive.google.com/file/d/1YZcaY-35JiHXOH4unRe5ECSeDl8IZFZy/view?usp=sharing)

This workshop uses [Python version 3.8](https://www.python.org/downloads/release/python-380/). We recommend creating a [Python virtual environment](https://docs.python.org/3.8/tutorial/venv.html) and install all the package dependencies there. The official environment with all the required packages is [igwn-py38](https://computing.docs.ligo.org/conda/environments/igwn-py38/), available from the International Gravitational-Wave Observatory Network ([IGWN](https://computing.docs.ligo.org/guide/)) community website. However, we make available also a *light-weight* version of this environment, with only the strictly necessary packages to execute the notebooks. Whenever possible, we recommend the full installation though

This guide will walk you through the configuration of this environment with [Conda](https://www.anaconda.com/). 

1. Install miniconda:
   
    - Visit the website https://conda.io/en/latest/miniconda.html
    - Choose the version for Python 3.8
    - Follow the [installation instructions](https://conda.io/projects/conda/en/latest/user-guide/install/
) for your operating system: 
        - [Linux](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)
        - [macOS](https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html)
    
   You may need to restart your computer after installation.

2. If you want to install the full [igwn-py38 environment](https://computing.docs.ligo.org/conda/environments/igwn-py38/) (recommended), download the YML dependencies file for the IGWN website:
   * [YML file for Linux](https://computing.docs.ligo.org/conda/environments/linux/igwn-py38.yaml)
   * [YAML file for macOS](https://computing.docs.ligo.org/conda/environments/osx/igwn-py38.yaml)

   Instead, for the *light-weight* environment, download the YML file corresponding to your operating system from this repository:
   * [YAML file for linux](./environment.yml)
   * [YAML file for macOS](./igwn-py38-lw-macOS.yaml)

   **Note:** the name of the *light-weight* environment is **igwn-py38-lw** to distinguish it from the official one, `igwn-py38`. In the following steps, remember to add the "`-lw`" subfix to the name.

3. Add the conda-forge channel

    `conda config --add channels conda-forge`

4. Create the environment. <br/>
   If you have downloaded the full environment, either on Linux or macOS:
   
   `conda env create --file igwn-py38.yaml`
   
   Otherwise, for the light-weight one: <br/>
   * On Linux: `conda env create --file environment.yml`
   * On macOS: `conda env create --file igwn-py38-lw-macOS.yaml`

5. Clone the workshop git repo 

    `git clone https://github.com/gw-odw/odw-2021.git`

6. Move into the directory with the workshop git repo 

    `cd odw-2021`
    
7. Activate the environment. <br/>
   **Note:** remember to add "`-lw`" to the name of the environment if you have installed the light-weight one.

   `conda activate igwn-py38`
   
   (Light-weight environment: `conda activate igwn-py38-lw`)

8. Build a custom [jupyter kernel](https://ipython.readthedocs.io/en/stable/install/kernel_install.html) using the command 

  `ipython kernel install --user --name=igwn-py38` 
  
  or equivalently 
  
  `python -m ipykernel install --user --name=igwn-py38`
  
  (Light-weight environment: `--name=igwn-py38-lw`)

9. Start the Jupyter notebook server <br/>
  `jupyter notebook` and select the kernel `igwn-py38` (`igwn-py38-lw`) if this is not done by default.

**Notebooks:**
If you are not familiar with Jupyter notebooks, google one of the many introductory guides available on the internat, like <a href="https://realpython.com/jupyter-notebook-introduction/">this one</a>. Also, taking a look at the <a href="https://colab.research.google.com/notebooks/basic_features_overview.ipynb">Examples</a> offered by Google Colab can be helpful.

**Troubleshooting:**
- The kernel `igwn-py38` should appear in the list returned by the command `jupyter kernelspec list` executed in a terminal
- If, when you run jupyter, you get the message: `Could not find kernel matching igwn-py38. Please select a kernel: Python 3`
this indicates the `igwn-py38` kernel is not installed properly. Make sure you executed step 9)
- Having the full environment and the light-weight one with two different names allows them to coexist. If you want to leave the same name and overwrtite one or the other, simply add `--force` option when you create it.

## Option 4: Linux install on Windows 10 with dedicated app (Windows 10 only)

<img src='https://www.wispresort.com/uploadedImages/Winter/hard.png' width=20 /> Advanced (For Windows 10)

Install a Linux distribution on your Windows system. 
See instructions here: https://docs.microsoft.com/en-us/windows/wsl/install-win10

We suggest you install Debian GNU/Linux, which is the closest distribution to what is 
used currently by LIGO/Virgo. Once you have Linux installed, follow the instructions 
in Option 3.

