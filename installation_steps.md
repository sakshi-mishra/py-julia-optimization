## Installation instructions for Python calling Julia to solve optimization problem in JuMP 

### Step 1: Anaconda Installation
- Download the Python (64-bit(x86)) installer from

     `https://www.anaconda.com/download/#linux`

- In bash terminal, type the command:

     `bash Anaconda-latest-Linux-x86_64.sh`

- Follow the prompts on the installer screens
- To make the changes take effect, close and then re-open your Terminal window.

### Step 2: Download and install Julia
- Download the Julia version 1.0.3  (64-bit Generic Linux Binaries for x86) installer from 

     `https://julialang.org/downloads/`

- Then, extract the .tar.gz file downloaded in the previous step to a folder on your computer
- Next step is to add Julia's bin folder to your system PATH environment variable , go to your home directory and open .bashrc file.
- Add the following line to the .bashrc file:

     `export PATH="$PATH:/path/to/julia/folder/julia-1.0.3/bin"`

- Open a new terminal window and install Julia using:

      `sudo apt install julia`
  
### Step 3: IJulia and JuMP Installation

- Open a terminal and launch julia with the command: `julia`
- Install IJulia with the following commands

     `using Pkg`
     `Pkg.add("IJulia")`

- Further help on IJulia notebook:  [here](https://github.com/JuliaLang/IJulia.jl)
  
- Install JuMP with the following commands (in the terminal where julia was launched):

     `Pkg.add("JuMP")`
     
- Install PyCall
     `Pkg.add("PyCall")`


### Step 4: Installing Solvers
- Execute the following set of commands:

     `Pkg.add("Cbc")`
     `Pkg.add("GLPK")`
     `Pkg.add("MathOptInterface")
     `Pkg.add("Interface")`
     

     #### Step 4.1 If you do not have svn already installed on your machine then execute the following commands:
     `sudo apt-get update`

     `sudo apt-get install subversion`

     #### Step 4.2 If you do not have fortran compiler already installed on your machine then execute the following command:

    `sudo apt-get install gfortran`


### Step 5: Creating virtual environment for Julia in  **Python**

- In a new bash terminal, run the following command to create a new virtual environment named *ju_py* 
    `conda create --name ju_py`

- Activate the newly created python virtual environment using the command:
    `source activate ju_py`

- Install python's julia package for calling julia functions in python
    `conda install -c conda-forge julia`
    `python2 -m pip install julia`

- Adding the python virtualenv (_ju_py_)  to the ipython notebook, run the following set of commands:
    `pip install ipykernel`
    `ipython kernel install --user --name=ju_py`

- In Julia >= 0.7, above two paths to `libpython` have to match exactly
  in order for PyJulia to work.  To configure PyCall.jl to use Python
  interpreter "/path/to/anaconda3/envs/ju_py/bin/python",
  run the following commands in the Julia interpreter (to get to Julia interpreter, open a new terminal and type `julia`) and then type the following commands:

    `ENV["PYTHON"] = "/path/to/anaconda3/envs/ju_py/bin/python"`
    `using Pkg`
    `Pkg.build("PyCall")`

### Step 6: Installing **Julia Plugin** for PyCharm

- If you are using PyCharm IDE for running your python code, then install the Julia plugin 

- go to File $$\to$$ Settings $$\to$$ Plugins $$\to$$ towards the end $$\to$$ Browse Repositories... $$\to$$ search "Julia"

- install the Julia plugin and restart Pycharm

  #### Step 6.1: Setting up project interpreter for running Julia file inside PyCharm

- go to File $$\to$$ Settings $$\to$$ Languages & Frameworks $$\to$$ Julia

- In _*Julia executable*_ field, enter the path to the julia executable:

     `/path/to/your/downloaded/julia/folder/julia-1.0.3/bin/julia`
