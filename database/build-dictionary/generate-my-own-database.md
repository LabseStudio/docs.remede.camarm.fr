---
description: Learn how to generate your own Remède database !
---

# Generate my own database

Please read [Lifecycle](the-building-lifecycle.md) before.

See also [Quickly add a word](about.md#quickly-add-a-word).

## 1 - Generate required ressources

```shell
python3 scripts/pre_generate_ressources.py
```

## 2 - Start parsing words

You need to start [api-definition](about.md#api-definition) in local, so our generation script can get definitions of Wiktionary.

Start `generate.py`

```shell
python3 scripts/generate.py
```

This operation take few days !

{% hint style="warning" %}
Generating a new database will erase the current one ! Make sure to save it before ! For example, make a copy of it; `cp data/remede.db data/remede.07-06-2024.db`
{% endhint %}

## 3 - Enjoy your own database !

The database situated at `data/remede.db` has been generated successfully, and you can now serve it with the API ! Congratulations !

## Troubleshooting

A generation is very long ! Sometimes it crashes or freeze... The `generate.py` script handle crashes (or in cas of freeze, the KeyboardInterrupt that you can trigger by pressing <kbd>ctrl-c</kbd> in your terminal to end the process) and saves its progression:

* `data/remede.db`; the database, not fully generated
* `data/missing-wordlist.txt`; the list of words that should have been added

To **resume the generation**, execute

```shell
python3 scripts/generate.py --resume
```

_It will automatically resume the process with the saved files_
