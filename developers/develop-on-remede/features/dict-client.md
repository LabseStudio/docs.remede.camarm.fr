---
description: Remède supports the DICT protocol and can be used as a DICT client.
---

# 🧰 DICT Client

Remède is able to communicate with dictionaries servers. The DICT protocol was created in 1997; it has been described in the [RFC2229](https://www.rfc-editor.org/rfc/rfc2229). It is based on TCP/IP.

### How it works

The codebase contains a Dict Client view, which is able to explore dictionaries server.

{% hint style="info" %}
Because Javascript is not able to send TCP requests, we must use native code to send TCP request through sockets. Thanks to [Capacitor Plugins](https://capacitorjs.com/docs/android/custom-code), we can easily call native Java code from our Typescript codebase.
{% endhint %}

<details>

<summary>The Capacitor "TCPClient" plugin</summary>

The plugin native code is located at `app/android/app/src/main/java/dev/camarm/remede/TCPClient.java` and it is defined in the Vue codebase at `app/src/functions/plugins/tcpClient.ts`.

TODO: Not finished

</details>

<details>

<summary>The DICT Client view</summary>

TODO: Not finished

</details>

<details>

<summary>The "Searching using DICT servers" feature</summary>

TODO: Not finished

</details>

