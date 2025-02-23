---
description: >-
  This section contains documentation for related resources to Remède
  generation.
---

# About

## Api Définition

This API, written by [Frederic Gainza](https://api-definition.fgainza.fr/), scrap the [French Wictionary](https://fr.wiktionary.org/wiki/Wiktionnaire:Page_d%E2%80%99accueil).

For Remède, **it has been readapted** by [Labse Software](https://github.com/LabseSoftware/api-definition)

### Start with docker

This API's code is contained under the `api-definition` folder which is a **git submodule**.

In `api-definition` folder:

```shell
docker build -t remede-definition-api . && docker run -p 8089:80 remede-definition-api
```

## Quickly add a word

The script `scripts/add_word.py` let you add a word to the Remède database without rebuilding it totally.

It :

* Add your word in `data/mots.txt`
* Add your word's document in `data/remede.db`

{% hint style="info" %}
You must have an [api-definition](about.md#api-definition) instance running locally !
{% endhint %}

```shell
python3 scripts/add_word.py <word> <phoneme>
```

To add multiple words:

`wordlist.txt` (tabulation between word and IPA: `mot\t/ipa/`)

```
acupuncture /a.ky.pɔ̃k.tyʁ/
remède  /ʁəmɛd/
```

and execute

```shell
python3 scripts/add_word.py -f wordlist.txt
```

## Wordlist iterator

This script was created to iterate wordlists (text file with words separated by a newline) to add them to Remède...

The script `scripts/check_wordlist.py` iterate the given wordlist, find every word phoneme and add them to a `.words_to_add` file.

It adds all the **words that are not already in the database** to this file, them can be added with `scripts/add_word.py`. (referenced [just above](broken-reference))

Usage:

```shell
python3 scripts/check_wordlist.py <path to wordlist>
```
