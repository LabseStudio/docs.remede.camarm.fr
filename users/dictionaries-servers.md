---
description: >-
  You can explore DICT servers with Remède. Let's see how to enable and use this
  functionality.
---

# 🌐 Dictionaries servers

{% hint style="warning" %}
Using Remède as a DICT client is **only available for Android devices**. See more : [#support](dictionaries-servers.md#support "mention").
{% endhint %}

### What is a dictionary server

The Dictionary Server Protocol (DICT) is a TCP based protocol which allows a client to access dictionary definitions from a set of dictionary databases. See [RFC2229](https://www.rfc-editor.org/rfc/rfc2229).

You can find a large amount of dictionary servers, that contains dictionaries about various topics.

### How to explore servers from Remède ?

You can browse dictionary servers from the "DICT Client" page in Remède. This page is more a testing purpose page than a way to browse dictionaries servers. It allows you to test servers connectivity and functionalities, with a logs page ect...

To use dictionaries servers as a search method in Remède, see [#how-to-set-a-dictionary-server-as-a-primary-dictionary](dictionaries-servers.md#how-to-set-a-dictionary-server-as-a-primary-dictionary "mention")

<details>

<summary>The server address field</summary>

On the DICT Client page, you can see two fields at the top of the page. The first one should indicate the DICT server address.\
![](<../.gitbook/assets/image (5).png>)

The left part contains the hostname; a domain name or an IP address; and the second part is the server port. The default port for the DICT Protocol is 2628.

You can select a server from your saved servers or the default server directory by clicking the compass icon.

</details>

<details>

<summary>The search field, and search options</summary>

Below the server address field, you can see the search field. Use it to make a query to the dictionary server.

![](<../.gitbook/assets/image (6).png>)

For more search options, click the filter icon at the right. You can now see the options page. You can select the dictionary to use (or choose to search in all dictionary), and the search method.

![](<../.gitbook/assets/image (8).png>)

* The DEFINE method will return the definitions of the words
* Whereas the MATCH method will return a list of word matching the requested pattern. The search pattern is what you enter into the search field.
  * The use of the MATCH method require a STRATEGY. The STRATEGY specify how do you want to match your pattern: REGular EXpression, starts with (preffix), ends with (suffixe) ect...

</details>

<details>

<summary>The logs page</summary>

For debugging purposes, you can open the logs page. It shows the raw transmission between Remède and the dictionary server.

![](<../.gitbook/assets/image (9).png>)



</details>



### How to set a dictionary server as a "primary" dictionary ?

Setting a dictionary server as "primary" will let you browse it directly from the home page and see a word's definitions.

{% stepper %}
{% step %}
### Go to the settings page

Using the menu, switch to the settings page. Then, click switch to the DICT servers page.

<div align="left"><figure><img src="../.gitbook/assets/image (1).png" alt="" width="206"><figcaption><p>App menu</p></figcaption></figure> <figure><img src="../.gitbook/assets/image (10).png" alt="" width="188"><figcaption><p>Settings page</p></figcaption></figure></div>
{% endstep %}

{% step %}
### Add a dictionary server

You can add your owns dictionary servers using the "Add a server button".

<div align="left"><figure><img src="../.gitbook/assets/image (11).png" alt="" width="188"><figcaption><p>DICT servers settings</p></figcaption></figure> <figure><img src="../.gitbook/assets/image (12).png" alt="" width="188"><figcaption><p>Add server modal</p></figcaption></figure></div>
{% endstep %}

{% step %}
### Enable "search from DICT servers" and turn on desired servers

<div align="left"><figure><img src="../.gitbook/assets/image (13).png" alt="" width="188"><figcaption><p>DICT server search enabled</p></figcaption></figure> <figure><img src="../.gitbook/assets/image (14).png" alt="" width="188"><figcaption><p>Wanted servers enabled</p></figcaption></figure></div>
{% endstep %}

{% step %}
### Select "DICT servers" as search source and start browsing dictionaries servers !

<div align="left"><figure><img src="../.gitbook/assets/image (15).png" alt="" width="188"><figcaption><p>Search source selection</p></figcaption></figure> <figure><img src="../.gitbook/assets/image (16).png" alt="" width="188"><figcaption><p>Browsing DICT servers from Remède !</p></figcaption></figure> <figure><img src="../.gitbook/assets/image (17).png" alt="" width="188"><figcaption><p>Simplified definition page</p></figcaption></figure></div>
{% endstep %}
{% endstepper %}

### Support

| Device                  | Support              | Method                                 |
| ----------------------- | -------------------- | -------------------------------------- |
| :green\_circle: Android | :white\_check\_mark: | Native TCP request client, with Java.  |
| :apple: iOS             | :x:                  | Future : With a proxy owned by Remède. |
| :desktop: Desktop       | :x:                  | Future : With a proxy owned by Remède. |

The support of this functionality is limited because the DICT protocol is based on the TCP protocol. Remède is powered by web technologies (Javascript, HTML, CSS), and Javascript does not allows us to use TCP Sockets. The only two methods are to write a TCP Socket client with native code (like we do for Android) or to send the request through a proxy server.

{% hint style="info" %}
The proxy server is owned and developed by Remède (see NO LINK YET)
{% endhint %}

