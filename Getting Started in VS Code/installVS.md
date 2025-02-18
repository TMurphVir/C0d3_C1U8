v# Installing VS Code

[VS Code](https://code.visualstudio.com/) can be installed by clicking the hyperlink and following the recommended install settings for your operating system. Of note, this guide is tailored towards mac OS users so some functional differences can be expected. VS Code is very well supported and has plenty of community support if any hiccups arise.

![VS Install Screen](./.images/VSInstall.png) |
:--:|
 *VS Code download screen*|

## **Note:**

After downloading and installing VS Code make sure it appears in your applications screen. Default downloads go to downloads folder which restricts VS Code's access. If it is in the downloads folder, simply drag and drop it into the applications folder. If set up properly, it should appear in the applications tab as below. It may be on another page but the important thing is that the icon becomes available.

![VS Application](./.images/VSapplication.png) |
:--|
*VS Code in application tab*|

When downloaded, VS Code will appear as an empty canvas. Note, in the image provided are additional plugins on the far left of the screen which I have installed and is not reflective of a *truly* fresh install.

![VS Fresh Install](./.images/VSFresh.png) |
:--:|
*VS Code fresh install*|

## Extensions

Every element of VS Code can be customized to fit your production goals and personal preferences. With that said, this can be a source of clutter and compatibility between extensions can lead to frustrations.

The default look of the extensions tab is depicted below. It contains elements for organizing and navigating project folders and a tab for downloading extensions(bottom of list in the figure)

![Extensions](./.images/VSExtentions.png)|
:--:|
*Default Extension Pane* |

### Extensions for R

The extensions installed for R in VS Code require additionall tweaking and programs to be fully operational. First and foremost, ensure that [R](https://www.r-project.org/) is installed and fully up-to-date. If on mac, make sure the [Homebrew package manager](https://brew.sh/) is intalled following the default settings. This program makes it easier to manage, update, and install programs on MacOS. Homebrew also acts as a crutch for early programmers to navigate installation and the chaotic environment that packages can create. With Homebrew installed, open a new terminal (located in Apps under 'Other' folder) and run the following code:

``` bash
cd / #Navigate to top of directory tree
brew install r
```

Homebrew does much of the heavy lifting to make sure R is installed and handled consistently. With the terminal still open, make sure the Homebrew has installed Python3. The preinstalled version of python is not supported in VS Code. Additonally, use homebrew to install pipx. This is a lot of installing of programs but each of these are neccessary for nearly any coding project.

```bash
brew install python
brew install pipx
```

There are two important extenstions for getting started with R in VS Code. The first is the [R Extension](https://marketplace.visualstudio.com/items?itemName=REditorSupport.r) and [R Debugger](https://marketplace.visualstudio.com/items?itemName=RDebugger.r-debugger). These extenstions provide VS Code the ability to integrate communicate and operate with R. Once these extensions are installed it is important to restart VS Code completely.

### Installing Dependencies

The next step is to install more dependencies. These dependencies further integrate R with VS Code and include many bells and whistles. These are listed in the Extension pages for the two extensions on VS Code. The first dependency is [Radian](https://github.com/randy3k/radian?tab=readme-ov-file). Radian is an alternate console for R and in simple terms it adds code highlighting and formmatting features when using R in the terminal.

```bash
pipx install radian
```

After installation is complete, take note of the filepath where radian is installed and copy it into a blank notepad. Next, type radian into the console to see if the terminal opens.

```bash
radian
```

if successfull it should appear as below. On the left side of the image is the default R terminal when launched, the right side of the image is the radian terminal. Of note, in the case of multiple installs of R, radian may interact with the wrong R version. Double check that radian is using the proper R version. Not to be confused with the version of radian.

![R and Radian](./.images/RTerminals.png)

Once confirmed that radian is installed and using the correct terminal, use the radian terminal to install the languageserver, styler, and vscDebugger. These provide further syntax and styling for using R in VS Code. The provided code uses base R install function and the 'c()' component allows for a list input to avoid needing to run the line twice. vscDebugger has problems being installed by base R and requires direct pathing to the repository.

```R
install.packages(c('languageserver','lintr','styler'))
install.packages("vscDebugger", repos = "https://manuelhentschel.r-universe.dev")

```

Finally, we need to provide VS Code with the file path to reach radian so that it becomes the default terminal within VS Code. This is done by navigating to extension settings in VS Code, selecting R, and in the default terminal path pasting the filepath for Radian. Take note that it is important to only add radian's file path to the R extenstion and not the debugging extension. A video is included below:

[Video](./.images/RadianTerminal.mp4)

After installation close the terminal completely and restart VS Code even if not using the terminal within the application.

### Checking Dependency Function

Once each of the dependencies are installed, we will move on to making sure each of them work. If you have not done so already, completely close out of VS Code and restart. Then, open a new terminal under the terminal tab at the top of the screen, as well as an empty document called 'test.R'.

#### Radian and Language Server

In the new text file paste the following line of code:

```R
function(){}
```

With your text cursor at the start or end of the line, hold the command key and press enter. This should run that line of code in the terminal. If successful, the terminal should open and execute the code by just printing it out. Make sure that the terminal is radian by seeing that the new terminal line has 'r$>'.

Next, copy the same code into the terminal and between the curly brackets{} press enter. If successful, a new line should be created. This indicates that radian is incorporating R syntax into VS Code terminal allowing for multi-line behavior.

![RadianCheck](./.images/radianCheck.png)

Then on the terminal section of the screen, select the 'output' tab. On the far right, select the 'R Language Server' from the drop down table. The textbox should fill up with random code which indicates that it is working.

![languageServerCheck](./.images/languageserveroutputCheck.png)

#### Formatting and Tooltips

The final major check is looking that R syntax and formatting works in the text editor. In the test.R file make sure that the 'function(){}' is copied exactly with no modifications. Right click and select 'Format Document' then see if the curly brackets in the code now have a space after the parentheses.

![Format](./.images/FormatCheck.png)

Next, we will make sure the tooltips work. If not already installed, install ggplot 2 with the following code.

```R
install.packages(ggplot2) #if not already installed
library(ggplot2)
```

With the ggplot2 library installed and loaded, begin typing any ggplot2 command. A dropdown table should appear with command options with each information regarding usage, syntax, and examples.

![tooltip](./.images/tooltipCheck.png)

### Debugging

this section will be added later

### Styling

With R downloaded and all the dependencies functional, you can now begin coding with R in VS Code! The interface for VS Code is very customizable. As an example, I styled mine to have my text editor in the top left, terminal bottom left. On the far left side of the extension bar, selecting R gives details on loaded packages and environmental varaibles. Furthermore, in the help tab all the package help guides can be found for easy reference. By default, R plots are genearted in a new tab. Other packages and customization can be used, notably httpgd.

![RSTudio](./.images/rstudioVibe.png)
