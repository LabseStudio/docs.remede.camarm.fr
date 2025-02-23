---
description: The Remède dictionary for english-speaking people !
---

# 🇬🇧 English database

{% hint style="info" %}
The english database is **very unstable** and still in **early development stage**.
{% endhint %}

## Generation

We will understand how to generate the Remède English database, situated at `data/remede.en.db`.

_The generation is working exactly as described in Database - Generation - Lifecycle_.

But some resources changes:

* `data/fr/IPA.txt` is `data/en/IPA.txt` and the generated resources from this file are
  * `data/fr/words.txt` is `data/en/words.txt`
  * `data/fr/ipa.json` is `data/en/ipa.json`

Also, it uses the english version of api-definition.

To start an english generation, just run

```shell
python3 scripts/generate.en.py
```
