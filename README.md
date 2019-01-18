# AI in Trading NanoDegree (AITND)
This repository contains code for Udacity's [AI in Trading NanoDegree](https://udacity.com/course/ai-for-trading--nd880).

## Repository File Structure
    .
    ├── data/                # Data needs to extracted from the project workspaces in the classroom
    ├── project/             # Code for projects in the classroom
    ├── quiz/                # Code for quizzes in the classroom
    ├── helper.py            # A helper file shared across projects and quizzes
    ├── requierments.txt     # Common packages used for projects and quizzes
    └── tests.py             # Common test functions for unit testing student code in projects and quizzes

## No Data
We don't have a licence to redistribute the data to you. We're working on alternatives to this problem.

## My Repo
This repo is a fork of the udacity repo that complements the AI Trading Nanodegree.

### Braches
The master branch can be cloned and provides enhancements to allow for a clean windows install and instructions for obtaining required input data.
The solutions branch contains all solved projects.

### Installation

For windows:
```
git clone
conda env install requirements\aitnd_windows.yml
python -m ipykernel install --user --name aitnd
```
The last line allows you to run jupyter notebooks using the just installed aitnd python kernel. To check, run
```python
import sys
sys.executable
```
from the command line, as well as a jupyter notebook. Both should return an expresssion equivalent to ```'...\\Anaconda3\\envs\\aitnd\\python.exe'```. You might have to change the kernel used by each notebook manually to aitnd (Kernel -> Change kernel).

### Data
#### For Udacity students
To obtain the input files for project 1-3, open each project's notebook and run
```python
import numpy as np
df = pd.read_csv('../../data/project_x/eod-quotemedia.csv')
df.to_csv('eod-quotemedia.csv')
```
where you have to replace `x` with `1,2 or 3`. Now, you are able to download the just created file. Create the `data/project_x` folders in the top directory of your local repo and place the files there. 

For part 4, you need data for both the exercises and the project. 
First, add the following code to the workbook below the introductory video '12. Zipline Pipeline':
```python
import os,zipfile
zf = zipfile.ZipFile("Part4.zip", "w")
for dirname, subdirs, files in os.walk(os.path.join(os.getcwd(), '..', '..','data')):
    zf.write(dirname)
    for filename in files:
        zf.write(os.path.join(dirname, filename))
zf.close()
```
Then, download the zip file from your jupyter tree. Extract the files into the quiz directory of your local copy of this repo.
Repeat the process from the workspace in the subsequent '13. Zipline Coding Exercises'. The quiz/data folder now contains the folder project_4_eod. In order to do project 4, you need to copy this folder inthe the data folder in the repo root, as well.

#### For others
For non-Udacity students, or if you want to use zipline on other data, you need to create a free quandl account [here](https://www.quandl.com/sign-up-modal).