# Setup for JSM ATM V3

***

## Installing the system

{% stepper %}
{% step %}
### Locate the Integrations folder

The Integrations folder can be found directly in the main "JSM | ATM V3" folder.
{% endstep %}

{% step %}
### Parent the system to the Integrations folder

Parent the ATM Robbery System folder to the `Integrations` folder like shown below.

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

## Setting up the proximity prompt

The system will require a part to display the proximity prompt for robbing for each ATM.

{% stepper %}
{% step %}
### Locate the ATM's `Body` model

<figure><img src="../../../.gitbook/assets/{FB1DC4EE-5292-4293-B80E-8C0A023FC290}.png" alt="The hierarchy of a JSM ATM SelfServ 28 model."><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Decide which part you want to use

You must only decide a part from the `Body` model. The system will not search for labeled parts outside of the `Bod`y model.
{% endstep %}

{% step %}
### Label the part

{% hint style="warning" %}
The system will fail to initialize if it cannot find the part. Make sure that the name is correct and it is parented to the ATM's Body
{% endhint %}

Rename the part you want to use to "PromptPart" (case-sensitive).

<figure><img src="../../../.gitbook/assets/{43B6AD95-23D0-419A-AEE5-7E500AFFAEE2}.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

***

## Setup is complete

Great! Now that you've completed all the previous steps, your setup is now complete. Don't forget to configure the system using the `SystemConfig` module in the ATM Robbery System folder.

You might want to know about **engaging** before you configure your ATM. See [engaging-an-atm.md](../engaging-an-atm.md "mention").
