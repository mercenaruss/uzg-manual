# ZigStar UZG - Universal ZigBee Gateway Documentation

This subfolder contains the [uzg.zig-star.com](https://uzg.zig-star.com) documentation.
It is based on [Mkdocs](https://www.mkdocs.org/) & [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

You are very welcome to help on improving documentation.

## Directory-Structure

* `docs`: The actual documentation.
* `overrides`: MkDocs enhancements.
* `mkdocs.yaml`: MkDocs config file
* `init_setup.sh`: Prepare venv enviroment 
* `requirements.txt`: Mkdocs requirements

## Mkdocs installation

```bash
# Install MkDocs dependencies Linux
bash init_setup.sh
```

Manual installation:
```bash
# Install MkDocs dependencies Windows
python3 -m venv venv
. venv/Scripts/activate
pip install mkdocs-material
```

## Live preview of changes

From documentation folder run next commands:
```bash
# Enter in virtual enviroment
. venv/bin/activate ##For Linux
. venv/Scripts/activate  ## For windows
# Run mkdocs serve command to generate live preview
mkdocs serve
```

## Requirements:

- Python 3.8+
- pip