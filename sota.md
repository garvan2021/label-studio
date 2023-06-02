# SOTA Label-Studio usage tutorial

## Prequisities

- [git](https://git-scm.com/downloads)
- [miniconda](https://docs.conda.io/en/latest/miniconda.html)

## How to Use

### 0. Make sure you have `mighty` environment

```shell
conda create -n mighty python=3.8
```

### 1. Install [label-studio](https://labelstud.io/) locally

- Get latest `label-studio`

```shell
git clone https://github.com/garvan2021/label-studio.git
git checkout zjw
cd label-studio
```

- Install `label-studio`

```shell
conda activate mighty
pip install -e .
python label_studio/manage.py migrate
python label_studio/manage.py collectstatic
```

- Activate `label-studio`

```shell
# Set max upload file size to 5GB
export DATA_UPLOAD_MAX_MEMORY_SIZE=$((5*1000*1024*1024))
python label_studio/manage.py runserver
```

### 2. Do annotation

[document](https://labelstud.io/guide/get_started.html#Quick-start)
