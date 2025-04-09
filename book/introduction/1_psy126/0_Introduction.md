---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# <i class="fa-solid fa-download"></i> Installation

For the upcoming semester, we need to use functions from the R programming languae, which we will use within Python through the `rpy2` package.

You should have the following installed from last semester already:

- Anaconda (miniconda)
- Code editor (e.g. Visual Studio code)

If not, please re-visit the installation instructions from the [psy111](https://mibur1.github.io/psy111/book/introduction/1_Setup/0_Introduction.html) module.

As we need many new packages (and even a new programming language) this semester, we start by setting up a new conda environment for the course. 

In the Miniconda prompt (later, we'll see how to access Conda from the VS Code terminal), let's first ensure that we install the necessary dependencies from an up-to-date and reliable source. We’ll do this by adding the conda-forge channel and setting it as the default with strict priority.

```bash
conda config --add channels conda-forge
conda config --set channel_priority strict
```

Now we can create a new Conda environment, which this time not only contains Python but also R:


```bash
conda create -n psy126 python r
conda activate psy126
```

If the environment now shows up as `(psy126)`, you are ready to install the required Python packages for the semester:

```bash
pip install matplotlib pandas numpy rpy2 ipykernel statsmodels
```

Finally, we can install the required R packages.


````{tab-set}
```{tab-item} Windows
~~~bash
R.exe -e "install.packages(c('Gifi', 'mirt', 'psych', 'MPsychoR', 'polycor', 'admisc', 'ltm', 'eRm'), repos='https://cran.uni-muenster.de')"
~~~
```

```{tab-item} Linux/MacOS
~~~bash
R -e "install.packages(c('Gifi', 'mirt', 'psych', 'MPsychoR', 'polycor', 'admisc', 'ltm', 'eRm'), repos='https://cran.uni-muenster.de')"
~~~
```
````

Once these installations are succesful, you are ready to start.

```{dropdown} **Potential Issues**

If any of the R packages fail to install, you can use the pre-compiled conda packages as a backup. However, please note that they are not the newest version (this should be fine here but could generally lead to errors). This works by using `conda install` and putting an `r-` in front of the package name, all in lower case, e.g.:

```bash
conda install r-mpsychor
```

Alternatively, you can of course always install R packages through e.g. R Studio if you have it installed:

```bash
install.packages(c('Gifi', 'mirt', 'psych', 'MPsychoR', 'polycor', 'admisc', 'ltm', 'eRm'), repos='https://cran.uni-muenster.de')
```