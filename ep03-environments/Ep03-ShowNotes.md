# Episode 3 Show Notes -- Environments


<a href="https://www.youtube.com/watch?v=WHWsABk4Ejk&list=PLaMu-SDt_RB51u2kyttt3tDvXCp-KMw4A&index=5"><img src="Ep03-ShowNotes_figures/ep3.png" width=300></a>




There are many ways we can set up a virtual environment: Virtualenv, Anaconda, miniconda, Mini-forge, and several others. 

Here, we are going to focus on miniconda and conda-forge.



## A note about Miniconda vs Mini-forge

You can think of Miniconda as a *mini* version of the Anaconda, which is a Python distribution that comes with many packages pre-installed. The main tool in Anaconda & Miniconda is the so-called `conda` environment and package manager. It is a tool for creating new virtual environments and installing packages. 

Now, Mini-forge is a community-maintained repository for conda-compatible packages. Using either miniconda or conda-forge is fine as the `conda` commands are identical. 

William happily uses Miniconda while Sebastian prefers mini-forge, but as mentioned above, both William and Sebastian use the exact same `conda` commands.



## Installing Miniconda



We recommend visiting the [official Miniconda website](https://docs.conda.io/en/latest/miniconda.html) to find the latest information on installing Miniconda for your machine and operating system. For example, as of this writing, Sebastian would select one of the two following options to install Miniconda on his MacBook, which has an ARM-based M1 chip:

<img src="Ep03-ShowNotes_figures/installer.png" width=800>

Note that you can either choose the `pkg` or `bash` file installer. The `pkg` installer guides you through an interactive UI whereas the `bash` installer requires you to install Miniconda from your command line terminal. 

- If you download the `pkg` file, just double-click the downloaded file and follow the instructions.
- If you download the `bash file, go to your terminal, type 

```bash
bash Miniconda3-py39_4.12.0-MacOSX-arm64.sh
```

and follow the instructions that will be shown in the terminal. Note that the exact file name may differ based on which version of the bash installer you downloaded. Also, make sure you `cd`ed into the folder containing the installer file for this to work.



**Checking the installation**

After installing Miniconda, you can open a new terminal and check if it was successfully installed by running ` conda --version`. If it was correctly installed, you should see the current version number of conda, for example, as shown below:

<img src="Ep03-ShowNotes_figures/conda-version.png" width=600>

## Useful conda & pip commands



1) **Check** what environments are currently installed on your computer:

```bash
conda env list
```



2. **Create** a new environment called `course_1`:

```bash
conda create --name course_1 python=3.7
```



3. **Activate** an environment:

```bash
conda activate course_1
```

Tip: the active environment is usually indicated at the beginning of the terminal prompt as shown in the screenshot below:

<img src="Ep03-ShowNotes_figures/active-env.png" width=600>





4. **List** all packages currently installed in the active environment:

```bash
pip freeze
```



To save the requirements list to a `requirements.txt` file, you can use the `>` symbol:

```bash
pip freeze > requirements.txt
```





5. **Install new** packages with pip

```bash
pip install pytorch-lightning
```

Alternatively, installing directly with conda would look like as follows:

```bash
conda install pytorch-lightning -c conda-forge
```



6. **Install** packages from a **`requirements.txt`** file:

   ```bash
   pip install -r requirements.txt
   ```

   

## Bonus: exporting an environment using conda



Instead of using `pip freeze`, you can also use `conda` to snapshot your environment. For instance, you can run the following command to create a environment.yml YAML file:

```bash
conda env export > environment. yml
```

Then, you can share the `environment. yml`, and someone with the file can recreate the environment using the following command:

```bash
conda env create --file environment.yml 
```

Alternatively, you want to install the packages from `environment.yml` into an existing environment, you can use the `update` command as follows:

```bash
conda env update --file environment.yml 
```



## Bonus: Checking your current environment in Jupyter notebooks



When you create a new environment, it is a good idea to install Jupyter Notebook/Lab into that environment as well -- this ensures that you don't accidentally launch a Jupyter Notebook/Lab instance attached to a different environment. 

To conveniently check your current computer specs, conda environment, and the installed packages, Sebastian developed the handy [watermark](https://github.com/rasbt/watermark) extension.

After installing watermark as follows

```bash
pip install watermark
```

you can get various information about your computer and environment as shown in the screenshots below:


<img src="Ep03-ShowNotes_figures/watermark.png" width=700>

---



## Questions or Suggestions?

If you have questions or suggestions, please don't hesitate to reach out to William ([@_willfalcon](https://twitter.com/_willfalcon)) and Sebastian ([@rasbt](https://twitter.com/rasbt)) on Twitter or join our [Slack Channel](https://pytorch-lightning.slack.com/archives/C03GS6MTCCQ). For more episodes, also check out the [Lightning Bits: Engineering for Researchers](http://pytorchlightning.ai/edu/engineering-class).
