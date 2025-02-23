---
description: >-
  You are looking for a free and open dictionary for a project ? Use Remède; it
  is free, open and simple to integrate to any project !
---

# 📌 Remède for your project

**There are multiple methods to integrate Remède to your project**

{% tabs %}
{% tab title="Sqlite " %}
We provide a Sqlite database for each dictionary. You can download them on [our website](https://remede.camarm.fr/download).

For further informations, see

{% content-ref url="database/database-schema.md" %}
[database-schema.md](database/database-schema.md)
{% endcontent-ref %}

{% content-ref url="database/document-schema.md" %}
[document-schema.md](database/document-schema.md)
{% endcontent-ref %}
{% endtab %}

{% tab title="API" %}
You can easily integrate Remède everywhere using our API.

{% content-ref url="../developers/api.md" %}
[api.md](../developers/api.md)
{% endcontent-ref %}
{% endtab %}

{% tab title="DICT" %}
Remède is compatible with the DICT Protocol (accordingly to the [RFC2229](https://www.rfc-editor.org/rfc/rfc2229)). We provide a DICT server available at dict.remede.camarm.fr

You can download the DICT compatible files (`.index` , `.dict` & `.txt` files) from the [release section](https://github.com/camarm-dev/remede) on Github.
{% endtab %}

{% tab title="XDXF" %}
The **XML Dictionary eXange Format** (XDXF) is a dictionary format created in 2006 whose goal is to unite all existing open dictionaries format.

You can download the Remède dictionaries in the XDXF format (`.xdxf` files) from the [release section](https://github.com/camarm-dev/remede) on Github.
{% endtab %}

{% tab title="JSON files (Depreciated)" %}
You can download the JSON files on our [Github Repository](https://github.com/camarm-dev/remede/tree/1.2.3/data).

{% hint style="warning" %}
JSON files are depreciated since <kbd>1.3.0</kbd> and removed by <kbd>1.4.0</kbd>. See [Remède Next](../project/remede-next.md) for more informations
{% endhint %}
{% endtab %}
{% endtabs %}



Even if it is depreciated, you can also read our blog post "[Utiliser les données Remède](https://remede.camarm.fr/2023/11/19/Utiliser-les-donnees-Remede.html)".
