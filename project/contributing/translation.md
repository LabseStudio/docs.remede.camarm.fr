---
description: >-
  Remède is translated in multiple languages ! Let's learn how to translate
  Remède !
---

# 🌐 Translation

Remède has introduced a **translation system** since `1.3.0`. Remède uses [**i18n**](https://vue-i18n.intlify.dev/) for Vue as a translation system.

## Translating

The translations by languages are inside the `app/src/data/translations/[locale].json`.

For example, `en.json` (section "home")

```json
{
    "home": {
        "wordOfDay": "Word of day",
        "randomWord": "Random word",
        "myBookmarks": "My bookmarks",
        "forYou": "For you",
        "seeAll": "See all",
        "askToAddAWord": "Ask to add a word",
        "report": "Report",
        "searchWord": "Search a word...",
        "changelog": "Changelog"
    }
}
```

You can see that there are multiple translation in english.

## Add a language

1. Add his `app/src/data/translations/[locale].json` file
2. Define it in `app/src/i18n.ts`

```typescript
import yourNewLanguageTranslations from "@/data/translations/en.json"

const globalizationList = {
    fr: frenchTranslations,
    en: englishTranslations,
    yourLocale: yourNewLanguageTranslations
}

```

3. Define your language name in `app/src/functions/locales.ts`

```typescript
const locales = {
    en: "English",
    fr: "Français",
    yourLocale: "New language",
    dialects: {
        en: [
            "en-GB",
            "en-US",
            "en-CA",
            "en-AU",
            "en-NZ"
        ]
    }
} 
```

If your language has specific dialects for the correction service, add its dialects... See [Languagetool API documentation](https://languagetool.org/http-api/swagger-ui/#!/default/post_check), the field "language" in the check function.

And you're done !

## And about the database ?

Remède serve a **French database**, but we are working on internationalization of the database.

**How it works ?** We re-use as many code as possible across generation scripts and uses different scrapping services to build our databases.

To serve multiple databases, we define it inside `server.py`

```python

@app.get('/')
def root():
    return {
        "version": version,
        "message": "Check /docs for documentation",
        "dictionaries": DICTIONARIES
    }
    

if __name__ == '__main__':
    DICTIONARIES = {
        "remede": {
            # Definition of French dict
        },
        "remede.en": {  # Woaaaw ! Serving a new dictionary
            "name": "Remède (EN) Beta",
            "slug": "remede.en",
            "total": get_stats('data/remede.en.db'),
            "hash": md5(open('data/remede.en.db', 'rb').read()).hexdigest()[0:7],
            "valid": False,
            "schema": "",
            "size": f"{int(os.path.getsize('data/remede.en.db') * 10e-7)}Mb"
        }
    }
```

See [internationalization](../../database/database/internationalization/ "mention") docs for more information about a specific language.
