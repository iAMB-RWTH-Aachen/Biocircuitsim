# BioCircuitSim
---

Welcome to BioCircuitSim! This repository is part of the seminar 'synthetic microbiology' for the Biology and Biotechnology
study at the RWTH Aachen University. The aim of this practical class is twofold: 
 1. Teach you how to access and use published code, data and software using git
 2.  Give a basic introduction into boolean logic for the design of genetic circuits

## 1. Using git to access published work
This small git tutorial is based on a course given by the [BioNT](https://carpentries-incubator.github.io/fair-research-software/index.html)
Git is a very commonly used version control system for text-based documents such as code. Git makes it easy to collaborate and 
keep track of changes in a document. In the beginning it is difficult to grasp all the terms related to the version control system.
For this tutorial, we will use the following terms:
 - **repository** (short:repo): a project folder system on a git server. Actually, this is a repository
 - **remote**: The version of a repository on the git server
 - **fork**: a copy of the repository of user1 by user2
 - **clone**: a copy of the repository of user2 on the computer of user2, under the control of git and connected to the remote

If you are interested in how git works, please check out 
[this](https://carpentries-incubator.github.io/fair-research-software/04-version-control.html) webpage.

FYI: git is the system, GitHub and GitLab are different servers for storing all the files. Most computational biotechnology
work is shared on GitHub, but GitLab has more features. For your own work, we recommend using the [RWTH GitLab server](https://git.rwth-aachen.de/),
as this server is located in Germany and thus compliant with the German Act on data protection.

### i. Install the requirements
Before you start with working in this repository, please install the following requirements correctly on your system:

- [Command line tool](https://carpentries-incubator.github.io/fair-research-software/installation-instructions.html#command-line-terminal) (such as Bash, Zsh or Git Bash)
- [Git version control program](https://carpentries-incubator.github.io/fair-research-software/installation-instructions.html#git-version-control-tool)
- [GitHub account](https://carpentries-incubator.github.io/fair-research-software/installation-instructions.html#github-account)
- [Python 3.9](https://carpentries-incubator.github.io/fair-research-software/installation-instructions.html#python-3-distribution) (or any python version >3.9)
- [Visual Studio Code (VS Code)](https://carpentries-incubator.github.io/fair-research-software/installation-instructions.html#visual-studio-code), or any other integrated development environment (IDE)

### ii. Fork and clone this repository
If you find an interesting repository on GitHub or GitLab, you want to get it on your local machine. There are multiple options
to do this, but if you want to do modifications to the code and provide feedback to the developer (e.g. bugfixes), best 
practice is to create a fork of the repository.


This tutorial will guide you through forking this repository on GitHub and cloning it to your local machine using the command line.

#### Step 1: Fork the repository
1. Go to the GitHub repository: [https://github.com/iAMB-RWTH-Aachen/Biocircuitsim](https://github.com/iAMB-RWTH-Aachen/Biocircuitsim)
2. Click the **Fork** button (top-right corner of the page).
3. This creates a copy of the repository under your own GitHub account.

#### Step 2: Clone the forked repository
1. Open a terminal 
        - Windows: Command Prompt or PowerShell
        - MacOS/Linux: Terminal
2. Navigate to the directory where you want to store the project:
   ```sh
   cd path/to/your/directory
   ```
3. Copy the URL of your forked repository from GitHub (it should look like `https://github.com/your-username/repository-name.git`).
4. Run the following command to clone it:
   ```sh
   git clone https://github.com/your-username/repository-name.git
   ```
5. Navigate into the cloned repository:
   ```sh
   cd repository-name
   ```


#### (Optional Step 3: Set up the original repository as an upstream)
This step can be skipped, but is very useful if you work on a repository which is regularly updated.
To keep your fork updated with the latest changes from the original repository:
```sh
git remote add upstream https://github.com/original-author/repository-name.git
```
You can check if it was added correctly by running:
```sh
git remote -v
```


#### Step 4: Open the project in your IDE
- If using **VS Code**, open the repository by running:
  ```sh
  code .
  ```
- If using **PyCharm**, open it manually or use:
  ```sh
  open -a "PyCharm" .
  ```
  
## 2. Understand and use boolean logic in genetic circuit design
Now you are ready for start working with Python. Before you start, you do need to install all requirements.

### i. Installing all the dependencies in a virtual environment
Python is a widely used programming language. One of the main reasons for its success is the large amount of available
code in the form of packages. Python packages are small bundles of scripts which enable the user to use code from other in
a simple way. For example, there are packages for handling tables (pandas) or to implement scientific and statistical methods (scipy).
These packages are maintained by members of the community and are constantly updated. This can cause a problem for reproducibility: functionalities
and implementations might change or be removed from one version to another. Therefore, researchers created isolated environments
where they specify the versions of the packages required to run their code. These virtual environments (venv) in Python 
are isolated workspaces where you can install packages without affecting the global Python installation. This helps in 
managing dependencies for different projects, and ensures that you can transfer projects easily to other users. It ius therefor
a good practice to create a single venv for each project you open in Python. More information about how to use venvs in Python
can be found on [this webpage from the software incubators](https://carpentries-incubator.github.io/fair-research-software/05-reproducible-dev-environment.html).

#### Creating a Virtual Environment

1. Open a terminal or command prompt.
2. Navigate to your project directory:
   ```sh
   cd /path/to/your/project
   ```
3. Create a virtual environment:
   ```sh
   python -m venv venv
   ```
   This creates a folder named `venv` that contains the isolated environment.

#### Activating the Virtual Environment

- **Windows:**
  ```sh
  source venv\Scripts\activate
  ```
- **Mac/Linux:**
  ```sh
  source venv/bin/activate
  ```

After activation, your terminal prompt should change to indicate that you are inside the virtual environment.

#### Installing Packages

Once activated, you can install packages using `pip`. Most software projects have a file called `requirements.txt`
where all requirements are listed for your convenience.

```sh
pip install requirements.txt
```

#### Deactivating the Virtual Environment
To exit the virtual environment, simply run:

```sh
deactivate
```

#### Removing a Virtual Environment

If you no longer need the virtual environment, you can delete the `venv` folder:

```sh
rm -rf venv  # Mac/Linux
rd /s /q venv  # Windows
```

Using virtual environments ensures that dependencies are project-specific and prevents conflicts between different projects. 🚀



### ii. Launching the jupyter notebook
If you have virtual studio code installed, you can directly open jupyter notebooks. Otherwise you need to open the notebook
in the browser.This command will open the jupyter notebook landing page in your browser. 
Please navigate to the `BioCircuitSim.ipynb` notebook.

```sh
jupyter notebook
```

## Licensing and citation
This repository is made for teaching at the RWTH Aachen University. It is open for reuse by other teaching facilities, 
but citation of our work using the citation button in GitHub (or use the CITATION.cff file) is required. 

The code in this repository is subjected to a **MIT license**. All non-code content is licensed under **CC BY 4.0**.