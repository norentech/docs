---
icon: wrench
---

# The Basics

{% hint style="success" %}
This guide only applies to products covered by the [terms.md](terms.md "mention") (products purchased through Parcel/Packables).
{% endhint %}

Before you start using any Noren product, you need to go through the basics to make sure your product can function. Most tech products with licensing systems also require to do the same or similar steps in this guide.

## 1. Allow your game servers to send Http requests

Every Noren product uses a licensing module to perform checks. All our licensing modules require to interact with third-party APIs to perform these checks.

Follow the step-by-step guide below to learn how to allow Http requests to be sent from your game servers.

1.  Open Game Settings from the Ribbon.

    <figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
2.  Go to the Security tab.

    <figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>The Basic Info tab in Game Settings.</p></figcaption></figure>
3.  Enable "Allow HTTP Requests".

    <figure><img src="../.gitbook/assets/image (3).png" alt="" width="314"><figcaption></figcaption></figure>
4. Click Save at the bottom right of the Game Settings window, and you're done!

## 2. Ensure your product scripts have the necessary capabilities

{% hint style="info" %}
This section is only for those who have designated any `Model`, `Folder`, or `Script` as a sandboxed container in their **scripted** product. For more information, please [click here](https://create.roblox.com/docs/scripting/capabilities).
{% endhint %}

{% hint style="success" %}
Roblox may update their Creator Documentation at anytime, so the below steps may be inaccurate.
{% endhint %}

For every sandboxed container, here are a list of capabilities that we highly recommend allowing to ensure that your product can function correctly.

### Execution Control

* RunClientScript - [`LocalScript`](https://create.roblox.com/docs/reference/engine/classes/LocalScript) or [`Script`](https://create.roblox.com/docs/reference/engine/classes/Script) with a [`RunContext`](https://create.roblox.com/docs/reference/engine/classes/BaseScript#RunContext) value of [`Client`](https://create.roblox.com/docs/reference/engine/enums/RunContext#Client) is allowed to execute on the client
* RunServerScript - [`Script`](https://create.roblox.com/docs/reference/engine/classes/Script) with a [`RunContext`](https://create.roblox.com/docs/reference/engine/classes/BaseScript#RunContext) value of [`Server`](https://create.roblox.com/docs/reference/engine/enums/RunContext#Server) is allowed to execute on the server

### Instance Access Control

* AccessOutsideWrite - Script is allowed to fetch and receive instances from outside the sandboxed container

### Script Functionality Control

* AssetRequire - Script is allowed to call [`require`](https://create.roblox.com/docs/reference/engine/globals/LuaGlobals#require) with an asset ID
* CreateInstances - Script can create new instances using [`Instance.new`](https://create.roblox.com/docs/reference/engine/datatypes/Instance#new), [`Instance.fromExisting`](https://create.roblox.com/docs/reference/engine/datatypes/Instance#fromExisting), or [`Instance:Clone()`](https://create.roblox.com/docs/reference/engine/classes/Instance#Clone)

### Engine API Access Control

* Basic - Access to simple instances and essential building blocks
* Audio - Access to instances related to audio APIs
* Network - Access to HTTP networking APIs
* Physics - Access to instances related to physics
* UI - Access to instances related to user interfaces
* Environment - Access to instances related to the control of how the environment is displayed
* RemoteEvent - Access to instances for internal networking operations
