# py-julia-optimization
Code for integrating Julia/JuMP optimization function with Python code

- Base language: Python
- Language being integrated: Julia (1.0.3)
- Purpose: optimization using JuMP
- Solvers: open-source solvers like Cbc, GLPK etc.

A collection of ipynb notebooks with python code, which calls .jl files.
The constants are declared/initialized in the *_python code_* and then *_julia code_* (with JuMP optimiztion routine) is called to solve the optimization problem.

Detailed installation and virtual environment creation instructions are provided in **installation_steps.md** file.
