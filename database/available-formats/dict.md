---
description: The format created by the DICT Development Group.
---

# DICT

The DICT format is used by the `dictd` software. A dictionary is divided in two files: a `.index` file and a `.dict` file. For further information, see&#x20;

### Download

You can download the `.index` and `.dict` format for each dictionary directly from the [Github Releases](https://github.com/camarm-dev/remede/releases/).

### How to convert

To convert Remède dictionaries databases to the DICT format, there is a `prepare.py` script.

First, execute the script

```
python3 dictd/prepare.py
```

Then, switch to the `convert/dictionaries` directory. Using `dictfmt` , generate the `.index` and `.dict` files.

```
dictfmt -e --utf8 --allchars -s "Remède Français" remede < remede.txt
dictfmt -e --utf8 --allchars -s "Remède English" remede.en < remede.en.txt
```

_Remède database are now available in the DICT format at `convert/dictionaries` ._
