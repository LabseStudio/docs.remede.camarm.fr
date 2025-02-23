---
description: The roots of Remède...
---

# 📦 Dataset

The `data` folder is destined to the linguistics resources used by Remède.

* Folder `fr/`
  * `words.txt`: List of \~1 000 000 words, semi separated
  * `ipa.json`: For a key 'word', returns his IPA
    * Generated from `data/IPA.txt`: a text file of format `[word]\t[ipa]` by `scripts/pre_generate_ressources.py`
* The sames resources, for each locale are situated in the folders `en` ect...

{% hint style="info" %}
The `data/remede.db` file is not included in git files, see Setup to download it.
{% endhint %}

* `data/remede.schema.json`: JSON schema of Remède document
* `data/custom_words.json`: File to add custom words... The words documents must follow the Remède Document Schema
  * `data/custom_words.schema.json`: its JSON schema
* `data/remede.db`: A sqlite database ([reference](document-schema.md)) (french)&#x20;
* `data/remede.[locale].db`: A sqlite database ([reference](database-schema.md)) (for locale, eg `remede.en.db`)&#x20;
* `data/drime.db`: The [Open Lexicon](http://lexique.org/shiny/openlexicon/) french database rewrote by the project [drime](https://a3nm.net/git/drime/files.html). Useful to get precise word metadata like syllables.
