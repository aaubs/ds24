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


## Part 5: Codespaces using VS Code and TabNine

### Step 5.1: Install TabNine
 In your VS Code IDE, go to Extensions. Search for Tabnine Enterprise (Self-Hosted) and select it (don't mix it with the other Tabnine extension) and install the extension.

<img src="https://docs.tabnine.com/~gitbook/image?url=https%3A%2F%2F3436682446-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FY2qxVf5VTm3fmwP4B4Gx%252Fuploads%252Fgit-blob-b7381dba80646c164af243960b39dfad9663ab90%252Fvsc1.webp%3Falt%3Dmedia&width=768&dpr=2&quality=100&sign=f2f61826&sv=1" width="150">



### Step 5.2: Login to GitHubSpace Using TabNine
- Open the Command Pallet.
- Run: Tabnine: Sign in using auth token

<img src="https://docs.tabnine.com/~gitbook/image?url=https%3A%2F%2F3436682446-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FY2qxVf5VTm3fmwP4B4Gx%252Fuploads%252FVfFfzJ6QzB6QXOzwYER9%252Fsaas_auth_token_vsc_1.webp%3Falt%3Dmedia%26token%3D847e83ee-7861-4334-a419-da837895227e&width=768&dpr=2&quality=100&sign=b2a3b066&sv=1" width="150">


- The following popup will appear:

<img src="https://docs.tabnine.com/~gitbook/image?url=https%3A%2F%2F3436682446-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FY2qxVf5VTm3fmwP4B4Gx%252Fuploads%252FyxURDVNuC3hK2pJ6Vk6v%252Fsaas_auth_token_vsc_2.webp%3Falt%3Dmedia%26token%3Ded87d380-66a3-43dd-9c48-b972eb17e71a&width=768&dpr=2&quality=100&sign=936c359b&sv=1" width="150">

- If you already have an authentication token, click Sign in and skip to the relevant step below.
- If you don't already have a token, click Get auth token.
- The browser will open with the following screen for signing up, which includes a secret personal authentication token:
<img src="https://docs.tabnine.com/~gitbook/image?url=https%3A%2F%2F3436682446-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FY2qxVf5VTm3fmwP4B4Gx%252Fuploads%252FVL7SAZY9SuAMlvjOHzLy%252Fsaas_auth_token_jb_3.webp%3Falt%3Dmedia%26token%3D2df0c466-1eba-40c6-a848-9141c71b19f0&width=768&dpr=2&quality=100&sign=cbd18a65&sv=1" width="150">

- Copy the token and go back to your IDE.
- Paste your authentication token in the following popup and click Enter:

<img src="https://lh7-us.googleusercontent.com/YD9KAz4nlJYH8c5k1BCpQDqs-pnf-gqlJJv0MDZmnd8otSm7CvRZi32UaQxOF7wlWQZzv-G_XTUB7otAyqR7HRzPVwyVpgwHBsyoPEyspuWRPfV39ZlJ4s81sITxyes3Cqi1wRhPFkN3kiu5KwmVBgSAkw=s2048" width="150">
