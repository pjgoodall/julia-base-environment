# julia-base-environment

A simplistic environment to run Julia in git tutorials reliably.

For easiest use you will need to add tutorials as [git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules), after you check-out this repository.

## The Problem

Providing a correct configuration of external libraries for a Julia system, on top of your working operating system environment is not trivial. A lot of time can be wasted, particularly for beginners trying to run tutorials in a [Jupyter(https://jupyter.org/)] notepad environment.

## A Solution

The Julia [PyCall.jl](https://github.com/JuliaPy/PyCall.jl) package allows [Julia environments](https://pkgdocs.julialang.org/v1.2/environments/) and [miniconda](https://docs.conda.io/en/latest/miniconda.html) to create a containing minimal Python virtual environment with its required Python prerequisites and libraries.

## Gallery of Rogues

```
PYTHON="" julia -i -e  'using Pkg; Pkg.activate("."); Pkg.build("PyCall");Pkg.add("IJulia"); Pkg.instantiate(); using IJulia,' 
```

```
PYTHON="" julia -e 'using Pkg; Pkg.activate("."); Pkg.instantiate(); Pkg.using("IJulia"); notebook(dir=pwd()) '
```
