---
title: "Frequently asked questions"
weight: 4
---

Below you can find some frequently asked questions about the interface.

---

## Why doesn't the map work on HTTPS?

FiveM doesn't (when writing this, anyways) provide security libraries on the server.
This means, the websocket cannot create a secure connection to the interface.

To get this working properly, you need to search up how to set up a "reverse websocket proxy" to the FiveM server.
The proxy should have the SSL certificates installed and reverse the connection to the insecure websocket on the FiveM server.
If this sounds like giberish, then keep the interface on HTTP.

- [For nginx users](https://www.nginx.com/blog/websocket-nginx/)
- [For apache users](https://httpd.apache.org/docs/2.4/mod/mod_proxy_wstunnel.html)


---

## Why can't I see players?

This is the most difficult question to answer on a FAQ.
The only thing I can do is give you a checklist to try and help out.

1. Do you have an exception in your firewall?
   1. If you have this hosted through a provider, ask them if they have a firewall and to add an exception if they can.
2. Have you port-forwarded?
   1. Mainly aimed at home users.
3. Have you put the **public** IP in the config?
   1. Or domain name, if you have that set up.
4. Is your website using HTTPS?
   1. See [why doesn't the map work on HTTPS](#why-doesnt-the-map-work-on-https)

---

## Why won't the interface work with v2.3.0+ of the resource?

Make sure **all** your servers have a `socketPort` and it points to the same socket as the resource.
The following is the bare minimum to get the interface to work with v2.3.0 and above.

```json
"servers": {
    "Default": {
        "ip": "127.0.0.1",
        "socketPort": 30120
    }
}
```