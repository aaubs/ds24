---
title: "- Welcome Students!"
weight: 1
disableToc: true
draft: false
---

![](https://raw.githubusercontent.com/aaubs/ds-master/main/data/Images/Intro_BSD_M1.jpg)


This session will introduce you to the fundamentals of data science, with a focus on Python. We will cover the Python data science stack, essential tools and platforms, software setup, semester overview, and Python 101. 

## Session 1: Welcome Students!

This session sets the stage for your data science journey:

* Python Data Science Stack: Dive into Python's core data science libraries and frameworks. We've got you covered!

* Ecosystem Deep Dive: Familiarize yourself with essential tools and platforms, such as Github, UCloud, Google Colab, and Jupyter. These will be integral to your studies and projects.

* Software Setup: We'll guide you through installing the crucial software. And don't worry, our Teaching Assistants are here to assist with any challenges.

* Semester Overview: Get a glimpse of what the upcoming weeks hold for you.

* Python 101: We'll ensure everyone is up to speed with Python basics.


## Notebooks

* {{< awesome fas fa-laptop-code >}} [How to build a development environment using Colab, Google Drive, GitHub, and Kaggle!](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1_Colab_GitHub_Drive_Kaggle_v2.ipynb)
* {{< loom d93d46ef95db482099b530c5f1168b82 >}} 

* 🚀 **[Notebook: Python 101](https://colab.research.google.com/github/aaubs/ds-master/blob/main/notebooks/M1-Python-101.ipynb)**

<!-- 
## Slides


{{<gslides src="https://docs.google.com/presentation/d/1FuYxsmobCmcxlUPui6_2uRAo1JHWuooSCM06NvbNL2c/edit#slide=id.g275bf9313ce_3_190">}} -->


## Part 4: Cloning and Pushing to GitHub Using VS Code

This tutorial provides step-by-step instructions on how to install Visual Studio Code and Git, and how to use them to clone and push to a GitHub repository. The instructions cover both macOS and Windows.

### Step 4.1: Install Visual Studio Code

#### For macOS:
1. Visit the [VS Code official website](https://code.visualstudio.com/) and download the stable build for macOS.
2. Open the downloaded `.zip` file and extract VS Code.
3. Drag `Visual Studio Code.app` to the `Applications` folder, making it available in the Launchpad.

#### For Windows:
1. Visit the [VS Code official website](https://code.visualstudio.com/) and download the stable build for Windows.
2. Run the downloaded `.exe` file and follow the installation prompts.
3. Ensure you select “Add to PATH” during installation to enable launching from the command line.

### Step 4.2: Install Git

#### For macOS:
1. Download the latest Git for macOS from the [Git website](https://git-scm.com/download/mac).
2. Follow the instructions to install Git. If you download a `.dmg` file, open it and follow the prompts to install Git.

#### For Windows:
1. Download the latest Git for Windows installer from the [Git website](https://git-scm.com/download/win).
2. Run the downloaded `.exe` file and follow the setup instructions.
3. Make sure to choose the recommended settings, especially for adjusting your PATH environment.

### Step 4.3: Configure Git

Open a terminal (macOS) or command prompt/Git Bash (Windows) and set your user name and email address with the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Step 4.4: Clone a Repository Using VS Code

1. Open VS Code.
2. Access the Command Palette by going to the View menu and clicking on `Command Palette`
3. Type `Git: Clone` in the Command Palette and select it.
4. Enter the URL of the GitHub repository you want to clone and press `Enter`.
5. Select the directory where you want to save the repository and click `Select Repository Location`.
6. After the repository has been cloned, VS Code will ask if you want to open the cloned repository. Click `Open`.

### Step 4.5: Make Changes and Push to GitHub

1. Open the folder of the cloned repository in VS Code.
2. Make your desired changes to the files or add new files.
3. Commit your changes by entering a commit message in the message box and then clicking the checkmark icon at the top of the Source Control sidebar.
4. Push your changes to GitHub by clicking the `...` button in the Source Control sidebar, selecting `Push` from the dropdown menu.

### Notes

- Ensure that you have the necessary permissions to push to the repository if it is not owned by you.
- If you are pushing to GitHub for the first time, you may be prompted to authenticate with your GitHub credentials.

