# How to run jwst on niagara super computer
## 0. Requirements
a. account on compute canada
b. Ask permission to use SciNet (niagara)
    
## 1. Create jwst environment and installation
a. Once connected to niagara, load python version (3.8 in this example)
```shell
module load python/3.8
```
b. Create environment
```shell
virtualenv --no-download ~/your_environment_name
```
