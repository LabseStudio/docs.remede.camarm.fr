---
description: Learn how to contribute to Remède !
---

# 🙏 Contributing

## How to contribute

**To contribute, you can:**

* Open an issue ([here](https://github.com/camarm-dev/remede/issues/new/choose))
* Choose an issue or an enhancement idea, fork the repository, resolve it and open a pull request ! ([complete guide](contributing.md#guide))
* Contact us to become part of our team (software@camarm.dev)
  * So you'll have access to this repository

## Guide

1. Open or choose an issue on our [issue page](https://github.com/camarm-dev/remede/issues)
2. Fork and clone the repository on your computer
3. Read [the documentation](https://docs.remede.camarm.fr), and contact us for more informations (at software@camarm.dev).
4. Make your changes, and separate your work in multiple commits
5. Open a pull request
6. Wait and make requested changes
7. You're now a contributor ! Thank you very much !

You can see some example fo enhancement ideas you can make above.

## Add words

Remède fetches words from the Wiktionary but sometimes, words are not in our list so, you can add custom words...

You can add custom or missing word in our wordlists with ease.

1. Check on the [french Wiktionary](https://fr.wiktionary.org) if your word exist (or the Wiktionary in the language you want to add the word).
   1. If it is not referenced on the Wiktionary, add it to `data/custom_words.json` as JSON (using Remède Document Schema). The `data/custom_words.json` file looks like `{ "you-word": { /* Remède document */}" }`
   2. Don't forget to cite your sources (link of your resources) in `sources` field.
2. Using the script `add_word.py`, quickly add you word to the database. It will also add it to the Dataset files.

```shell
python3 scripts/add_word.py my-word /its ipa notation/ 
```

Check also [Building database - About - Quickly add a word](https://docs.remede.camarm.fr/docs/database/build/about#quickly-add-a-word)

## Add sheets

Remède needs contributors who can add sheets (for french grammar) !

You can find a documentation about writing sheets [here](https://docs.remede.camarm.fr/docs/sheets)

## Translating

* Add a new translation for the interface
* Enhance a translation
* Or build a new database for a new language !

Full documentation at Translation

## More

You can browse the documentation on the left-side menu. Do not hesitate to contact me us at [software@camarm.dev](mailto:software@camarm.dev) for more information.
