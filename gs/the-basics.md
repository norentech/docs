---
icon: wrench
---

# The Basics

{% hint style="info" %}
This guide only applies to Noren products purchased from **Parcel**.
{% endhint %}

Before you start using any Noren product, make sure that your game provides our products the necessary permissions to function.

Most tech products with licensing systems like Noren also require the same or similar steps in this guide.

***

## HTTP requests & API services

Noren products communicate with our licensing systems to enforce our Terms of Use and prevent unlicensed use. Our licensing module is required to interact with third-party APIs.

Noren products may also require to interact with Roblox API services to function.

Follow the step-by-step guide below to allow HTTP requests and access to Roblox API services.

{% stepper %}
{% step %}
### Open Experience Settings from File

Hover over "File" from the top left of Roblox Studio and you'll find "Experience Settings".

<figure><img src="../.gitbook/assets/{F01E47FE-DA6A-4FA5-A7F8-D5E973FC09C4}.png" alt="" width="414"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Go to the Security tab

<figure><img src="../.gitbook/assets/{BF7502FC-B8AD-43FA-BE6B-673E518E1536}.png" alt="" width="563"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Enable "Allow HTTP requests" and "Enable Studio Access to API Services"

{% hint style="success" %}
You will spot a warning from Roblox warning you of third party attacks by allowing HTTP requests. Noren will never attempt to attack or backdoor your game in any way.
{% endhint %}

<figure><img src="../.gitbook/assets/{5B9B4274-66BE-4C76-8874-06E2D9E92A2A}.png" alt="" width="563"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Save your settings

Click "Save" at the bottom of the Game Settings window and you're all good to go!
{% endstep %}
{% endstepper %}
