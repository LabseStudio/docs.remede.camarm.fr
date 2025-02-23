---
description: Discover how Remède's database is storing an entire dictionary.
---

# 📋 Database schema

Remède database is an **Sqlite 3** database.

## Tables

The database only has two tables :

| Name       | Description                                                                                    |
| ---------- | ---------------------------------------------------------------------------------------------- |
| dictionary | all Remède [documents](https://docs.remede.camarm.fr/docs/database/schema)                     |
| sources    | Remède sources links (to make the database lighter, we only store sources' ids, not full link) |

## Dictionary table

The `dictionary` table of Remède contains the following fields:

| Field          | Description                                                                               | Type      | Example                                       |
| -------------- | ----------------------------------------------------------------------------------------- | --------- | --------------------------------------------- |
| word           | The word                                                                                  | `string`  | `manger`                                      |
| indexed        | The word but case, accent and special chars insensitive                                   | `string`  | `manger` (`a vue d oeil` is a better example) |
| phoneme        | The word's phoneme                                                                        | `string`  | `m#Ze`                                        |
| nature         | The word's nature                                                                         | `string`  | `VER\|manger`                                 |
| syllables      | The word's syllables number                                                               | `integer` | `2`                                           |
| min\_syllables | The word's max syllables number^2                                                         | `integer` | `2`                                           |
| max\_syllables | The word's min syllables number^2                                                         | `integer` | `3`                                           |
| elidable       | Can the word be precede by an "élide"^1                                                   | `boolean` | `false` or `null` if no data                  |
| feminine       | Is the last phoneme "féminine"                                                            | `boolean` | `false` or `null` if no data                  |
| document       | The word's [document](https://docs.remede.camarm.fr/docs/database/schema), as JSON-string | `string`  | `{...}`                                       |

* See [Rimes](https://docs.remede.camarm.fr/docs/database/rimes) to know how this is used as a rhymes dictionary

## Sources table

The `sources` table of Remède contains the following fields:

| Field      | Description                                           | Type     | Example                                    |
| ---------- | ----------------------------------------------------- | -------- | ------------------------------------------ |
| identifier | The source id                                         | `string` | `fr_wik`                                   |
| label      | The source label, or the translation path             | `string` | `Wiktionnaire` or `definition.conjugation` |
| url        | The source's url. {word} will be replaced by the word | `string` | `https://fr.wiktionary.org/wiki/{word}`    |

***
