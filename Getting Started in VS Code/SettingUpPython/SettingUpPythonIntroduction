# Getting Started with Python in VS Code

## Overview

Python is among the most popular programming languages in the world. It is **free**, **open source** and has a tremendous amount of supporting packages for practically any project. Python can seem intimidating, particularly when considering its depth, but getting started with python programming in VS Code is a smooth process.

## Installing Python

VS Code has a slight python problem, at least on Mac OS. If you have not already done so, read the [Extensions Section](/Getting%20Started%20in%20VS%20Code/SwitchingFromR/installVS.md) to install python via home brew. Using the pre-installed python on Mac OS will work fine in its most simple form however, for VS Code extensions to be fully operational with Python you will want the homebrew installed version. Multiple installs can be problematic so it is important when using python, especially outside of VS Code, that you specify the python source and version you want to use.

## Downloading VS Code Extensions for Python

Once python is installed via homebrew, the remaining downloads, aside from packages, are VS Code extensions. Some of the extensions download more extensions by default so your extensions tab will increase in complexity. In the VS Code navigation tab download the following in order:

1. [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
2. [Python Environments](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-python-envs)
3. [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
4. [Python Indent](https://marketplace.visualstudio.com/items?itemName=KevinRose.vsc-python-indent)
5. [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)

After installing the extensions completely close out of VS Code and relaunch.

### Checking Dependency Function

#### Python Environments

When VS Code relaunches, start a new project directory. On the extensions pane, open the 'Python Projects' extension.

![pythonProjects](/.images/GettingStartedinVSCode/SettingUpPython/pythonProjectsExtension.png)

It should be a whole lot of... nothing. Notice the directory name under the python projects tab, along with the global and venv tabs under environment managers. If these are all present then the extension has been installed.

#### Python

Next, click on the drop down arrow for the directory under the python projects tab. Check to see what version of python, if any, shows up. It should be the latest version of python (3.13 as of Feb. 2025) and homebrew should be next to the version number. This indicates that VS Code recognizes the homebrew install of python and this is now the default.

![homebrewInstall](/.images/GettingStartedinVSCode/SettingUpPython/brewPython.png)

When coding in python, it is important to consider package managment. There are many ways to do this but by default in VS Code it uses VENV. Other notably package managers are conda/ anaconda. These can also be used if you desire. Personally, I do not care for conda, bioconda, or anaconda and use virtual environments (more on these later) to separate packages. This method requires manual upkeep but it avoids putting too many unknowns into your code base. Not to mention the dead space these packages managers will use up. In the future I will go in depth on this matter as it is very important, but for now follow my lead.

Under the environment managers tab you should see two additonal tabs. These are the global and venv tabs. Take note of their icons. Global, is the overarching python environment installed on the operating system. Virtual environments (venv) are isolated from the global environment and vice versa. when clicking on the venv tab it should be empty. Click on the '+' and a drop down table will appear at the top of the screen. Select the latest python version with the homebrew tag next to the title.

![venvSelect](/.images/GettingStartedinVSCode/SettingUpPython/venvSelect.png)

There will be several prompts after selecting the python version. Hit enter to skip through them (don't do this in the future although it is readily solved) and several things will happen.

1. The Python environments extension tab will now have much more going on
2. The default explorer pane will now have a new folder called .venv

![exploreVenv](/.images/GettingStartedinVSCode/SettingUpPython/exploreVenv.png)

What this has done is created a virtual environment within your project folder. Again, I am being vague here for simplicity but this effectively isolates your project coding environment from the rest of the computer. For better or for worse.

Navigate back to the python environments tab, and again go to the venv,.venv tab and hover over it. There will be a small icon that looks like a cardboard box. Click on this and a new dropdown menu at the top of the screen will appear with the options for installing and uninstalling packages. If you have used RStudio before then this will be a familliar system to you. Click the install packages, and search for pandas. Check the box for pandas and hit okay then it should install automatically including dependencies.

![venvPackage](/.images/GettingStartedinVSCode/SettingUpPython/venvPackage.png)

Go back to the explorer tab and create a new file called test.py.

![venvTest](/.images/GettingStartedinVSCode/SettingUpPython/testpyVenv.png)

In the text file we are going to import the pandas library, run a test code, and check that jupyter notebook functions.Copy and past the following code into the text file. Hover over the pd.DataFrame and ensure that a tooltip box appears with information on the command. This is checks that other python VS Code dependencies are working. Next, highlight everything and right click. Then select run in interactive window. This will open a new window in VS Code for jupyter. There will be initial errors but the !!

```Python
import pandas as pd
df = {'A':[1,2,3],'B':['A','B','C']}
pd.DataFrame(df)
```
In the new jupyter window, the top right of the pane will have some sort of python version. Select this and another drop down table will appear. Choose 'Select another kernel', 'python environments' and then choose the .venv(3.13)(Python 3.13) option. This option is the venv we created for this project folder. We want to use this option because it is where out project packages are. The .venv specifies a local pathing for finding python. If it doesnt automatically prompt another package install, run the code from test.py in the interactive window again then download the package. Once again, completely restart VS Code and relaunch the project folder. Select the code, right click to run in interactive window and it should run. Note: you may need to reselect the python environment again.

![venvCode](/.images/GettingStartedinVSCode/SettingUpPython/venvCode.png)

If everything works properly then the code will run and display a dataframe.

This is the most basic set up of python in VS Code and more details on navigating and utilizing it will be a part of other tutorials!

[Home](/README.md) [Previous](/Getting%20Started%20in%20VS%20Code/SwitchingFromR/installVS.md) [Next](/Getting%20Started%20in%20VS%20Code/AdditionalExtensions/)
