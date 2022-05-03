# Getting Started
Hello and welcome to the ML Ops course! Follow these steps to get your environment set up and review basic terminal skills. At the end you'll have your first project set up and ready to go.

## Quick Review
0. We will be using some terminal commands, so let's make sure you know what they are and what they do:

| Command      | Stands For |  Description |
| ----------- | ----------- | -------------|
| `ls`      | long listing       | lists all files and directories in the present working directory |
| `cd {dirname}`      | change directory       | to change to a particular directory |
| `mkdir {dirname}`   | make directory        | create new directory in present working directory or at specified path |
| `pwd`      | print work directory       | prints out your current working directory path |
| `touch {filename}.{ext}`   | touch        | create new empty file |
| `mv {filename} {newfilename}`   | move        | renames the file to new filename |
| `clear`      | clear       | clears the terminal screen |

We will also be using a few tools such as `git`, `conda`, and `pip`.

### Git
Git is a free and open source distributed version control system designed to handle everything from small to very large projects. These are the commands we will be using with `git`:

`git clone` -> clone a remote repository to your local computer

`git add` -> add files to a commit

`git commit -m {message}` -> commit changes with a message

`git push` -> push commit to remote repository

### Conda & Pip
Conda is an open-source, cross-platform, language-agnostic package manager and environment management system. We will use `pip` within `conda` environments to manage our package installations. `pip` is Python's package management system. `conda` comes with Anaconda. And Anaconda is a convenient way to set up your Python programming environment since it comes with a enviornment management tool (`conda`) and comes with extra packages that are commonly used in data science and ML.

Some commands we will use in this lesson when it comes to `conda` and `pip`:

`conda create --name mlops-course python=3.8 pip` -> This creates a virtual environment. A virtual environment is a Python environment such that the Python interpreter, libraries, amnd scripts installed into it are isolated from those installed on other environments and any libraries installed on the system. So basically, this allows you to keep all your project's code/dependencies/libraries separated from other projects. You are specifically saying to create said environment with the name `mlops-course`, use `python` version 3.8, and use `pip` as your package manager. The command `conda` invokes the underlying logic to actually make the virtual environment  and manages said environments for you.

`conda activate mlops-course` -> This activates the virtual environment you made with the above command for your current terminal session.

`pip install numpy pandas matplotlib` -> This installs the three packages mentioned - `numpy`, `pandas`, and `matplotlib`. `numpy` is used for scientific computing, `pandas` is used for data analysis, and `matplotlib` is used for data graphics. `pip` is the Python package manager and you are telling it to `install` the listed packages to your environment.

## Environment Set Up
1. Install [Anaconda](https://www.anaconda.com/products/individual).

If planning to use WSL, please install Anaconda in WSL. To do so, follow these steps in WSL:

```
> cd /home/{user}
> wget https://repo.continuum.io/archive/Anaconda3-2021.11-Linux-x86_64.sh
> bash Anaconda3-2021.11-Linux-x86_64.sh
```

Go through the prompts and select yes when asked to continue. Then after installation select yes to initalize conda. Lastly, close and reopen your prompt - you should now be able to run `conda`.

2. Install [Git](https://git-scm.com/downloads).
3. Install [VS Code](https://code.visualstudio.com/download).

## Github Set Up
4. If you don't already have one, make an account on [Github](https://github.com/). Then login and navigate to the top right user icon, click it, go to repositories, 
   
![github_repositories_button](https://user-images.githubusercontent.com/37101144/165583216-0ab7c17b-561e-45d8-a6c7-f138399d1e3b.JPG)

and then click "New" (the green button).

![github_new_repository_button](https://user-images.githubusercontent.com/37101144/165583414-86b59c04-f28b-4e19-94f9-225dfbc7a84b.JPG)

5. Create the repository by inputting the following:
* Repo name
* Repo description
* Make repo public
* Add a README
* Add .gitignore (Python template)
* Add license (choose MIT)

Then hit "Create Repository".

![github_create_repo](https://user-images.githubusercontent.com/37101144/165583457-ee74f1a4-8517-4487-80de-fb592c45b33a.JPG)

6. Now that you have a repo, go to the code section and copy the HTTPS address so you can clone your repo to your local computer.

![github_clone](https://user-images.githubusercontent.com/37101144/165583522-0f4c4350-412a-4c60-9d07-d324da65c087.JPG)

## Clone Your Repo
7. Open your terminal and navigate to a place where you would like to make a directory to hold all your files for this class using the command `cd`. Once there, make a top level directory using `mkdir`. `cd` into it and make another directory called `code`. `cd` into it and run your `git clone {address}` command. `cd` into your repository and type `code .` to open up your repositiory in VS Code. This should pop up a VS Code window with your repository open.

## Add To Your Project
8. Next we will review some terminal commands and make some additions to our repo. Do these in your terminal where your current working directory is your repo.
   * Check your current working directory: `pwd`
   * Create a new file: `touch hello_world.py`
   * Create new directory: `mkdir app`
   * Move file to directory: `mv hello_world.py app/hello_world.py` 
   * Check that the move command worked: `cd app` and then `ls`, you should see your `hello_world.py` file
   * Lastly, lets clear our terminal screen: `clear`

9. Now let's jump into VS Code and write ourselves a `hello world` program! 

## Hello World #1
10. Head over to `hello_world.py` and type the following into the file:
    ```
    print("hello world! let's do some ml ops!")
    ```

    Save. And now go to the integrated terminal by clicking `CTRL + ~`. In the terminal run your first program of the class by doing `cd app` -> `python hello_world.py`. Congrats, we are off to a great start!

## Set Up Virtual Environment
11. Now since this is an advanced class, let's do our next `hello_world` a bit different. First, let's make a virtual environment. To do so, run this command: `conda create --name mlops-course python=3.8 pip`. This will create a virtual environment named "mlops-course" (feel free to change the name).
12. Next, lets activate our newly created virtual envioronment by running `conda activate mlops-course`. Now everything we `pip install` will be packaged inside our virtual environment.
13. Let's install our packages so we can write our `advanced hello world` program. Run this command to install Numpy, Pandas, and Matplotlib: `pip install numpy pandas matplotlib`.

## Hello World #2
14. Create a new file under `app` named `hello_world.ipynb`. This is a notebook extension so in VS Code you'll be able to interact with your code via a notebook instead of a vanilla Python file. You might need to select your kernel in the top right of the notebook file, if so, choose the one we just created.
15. In the first cell of `hello_world.ipynb` lets do our imports. 

    ```
    import pandas as pd
    import numpy as np
    import matplotlib.pyplot as plt
    ```
16. Run the cell by either clicking the play button or by doing `CTRL + ENTER`. 
17. Create a new cell and in that put the following code:
    ```
    np.random.seed(0)

    values = np.random.randn(100) # array of normally distributed random numbers
    s = pd.Series(values) # generate a pandas series
    s.plot(kind='hist', title='Normally distributed random values') # hist computes distribution
    plt.show()   
    ```
18. Run the cell and you should see your histogram plot! Well done. 

![coding_histogram](https://user-images.githubusercontent.com/37101144/165583572-f9f6ae4f-33fb-4d19-9c13-f9fe3743e72a.JPG)


## Push Changes To Repo
19. Now let's commit this to our remote repository. This can be done one of two ways - either through the terminal or through VS Code's GUI. I'll explain both ways and you can choose which you'll use.

* VS Code GUI
  * Click `Source Control` on the left icon bar.
  * Click the plus button under changes to add your files to this commit.
  * Add a message to your commit by typing in the message field. 
  * Hover over `Source Control` dropdown and click the checkmark.
  * Click the elipse in `Source Control` and click `Push`.

* Terminal
  * Navigate to root of project using `cd`.
  * Type `git add .` to add all changed files to the commit.
  * Type `git commit -m "your message here"` to add a message to your commit.
  * Do `git push` to push to your remote repository.

Through all this you might need to set up your Git credentials if you haven't already. When prompted follow the prompts. 

One last note is that this was done pushing straight to the `main` branch which is usually bad practice as we would usually want to create a `feature branch` first and do a merge request. For now, it is okay the way we did it. If you are unfamiliar with what a `feature branch` is or a `merge request`...bring it up now!

20. Navigate to your Github repo code page in your browser. You should see the code changes we made live after you push. 

## Troubleshooting
* for Mac users terminal by default does not run code (getting started - step#7). Found a fix: Launch Visual Studio Code.
Press Cmd ⌘ + Shift ⇧ + P to open the Command Palette.
Type in shell command and select the Shell command: Install ‘code’ command in PATH to install it
