# We use *uv* for managing dependencies


## Installing 
### For lunix/mac
curl -LsSf https://astral.sh/uv/install.sh | sh
### For windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

## Initialize project 
uv init

## Create virtual env
uv venv --python 3.11

## Use venv
source .venv/bin/activate  # For Linux/Mac
.venv\Scripts\activate     # For Windows

## Installing Dependencies
uv pip install requests
uv pip install gensim -U
uv add pandas
uv add -r requirements.txt # if this file is available with libraries

conda install pyarrow # if issues with pyarrow