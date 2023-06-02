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

- get latest `label-studio`

```shell
git clone https://github.com/garvan2021/label-studio.git
git checkout zjw
cd label-studio
```

- install `label-studio`

```shell
conda activate mighty
pip install -e .
python label_studio/manage.py migrate
python label_studio/manage.py collectstatic
```

- activate `label-studio`

```shell
# Set data root
export LABEL_STUDIO_LOCAL_FILES_SERVING_ENABLED=true
export LABEL_STUDIO_LOCAL_FILES_DOCUMENT_ROOT=/home/jawen
python label_studio/manage.py runserver
```

### 2. build project

Follow [official guidence](https://labelstud.io/guide/setup_project.html).

### 3. Import coco

- convert coco json file to label-studio format

```shell
label-studio-converter import coco -i coco-anno.json -o output.json
```

> after script finished, you will get `output.json` and `config.xml`

- Import bellow files to project

  - raw images
  - config.xml
  - output.json
