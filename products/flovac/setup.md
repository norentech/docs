# Setup

{% hint style="success" %}
This setup guide is only for flo Vehicle Access Control V2.2 and above. [Looking for Card Reader Pro's setup guide?](setup-crp.md)
{% endhint %}

***

## Our recommended setup

In this section, we'll guide you to set up your system with our recommended setup.

Our recommended setup uses:

* 1x Card Reader (DWProx/Card Reader Pro | optional)
* 1x LPR camera
* 1x Flex Gate (Normal/Folding)
* 1x Welcome Screen (optional)

Assuming you have already got your lane ready, follow the steps below.

{% stepper %}
{% step %}
### Position your Flex Gate

Position your Flex Gate to the left side of the lane like the picture below. To learn how to scale your gate, refer to the [#scaling-your-gates](setup.md#scaling-your-gates "mention") section.

<figure><img src="../../.gitbook/assets/image (27).png" alt="Vehicle lane with a Flex Gate on the left side." width="375"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Position your Welcome Screen

If you are not using a Welcome Screen, skip this step.

Position your Welcome Screen in front of your Flex Gate's hub and rotate it to face the driver when they approach. Your setup should now look like the picture below.

<figure><img src="../../.gitbook/assets/image (28).png" alt="Vehicle lane with Flex Gate and Welcome Screen on the left side." width="375"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Position your LPR camera

Position your LPR camera next to your Welcome Screen (if any) and ensure that it is not blocking the driver's view of the Welcome Screen.

After positioning your LPR camera, move and scale the `DetectionArea` part to the center of your lane and in front of your Flex Gate's barrier.

Your setup should now look like the picture below where the blue box is the detection area.

<figure><img src="../../.gitbook/assets/image (30).png" alt="Vehicle lane with Flex Gate, Welcome Screen, and LPR camera on the left side." width="375"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Position your card reader

Position the Card Reader to the left side of the lane and rotate it to face the driver's window. If you're using a Welcome Screen, ensure that the driver's view of the Welcome Screen isn't blocked. Optionally, also keep it out of the LPR camera's view to keep it realistic.

Your setup should now look like the picture below.

<figure><img src="../../.gitbook/assets/image (32).png" alt="Vehicle lane with Flex Gate, Welcome Screen, LPR camera and Card Reader on the left side." width="375"><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

***

## Scaling your gates

{% hint style="info" %}
This section may be difficult to understand. Please take your time to understand the what the step asks you to do.
{% endhint %}

In this section, we'll guide you on how to scale your Flex Gate's arm. As there are 2 different types of Flex Gates, please refer to the correct section for the Flex Gate you want to scale.

<table data-view="cards"><thead><tr><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Flex Gate</strong></td><td><a href="../../.gitbook/assets/noren_documentationNumber_1.png">noren_documentationNumber_1.png</a></td></tr><tr><td><strong>Folding Flex Gate</strong></td><td><a href="../../.gitbook/assets/noren_documentationNumber_2.png">noren_documentationNumber_2.png</a></td></tr></tbody></table>

***

### Flex Gate

To scale your Flex Gate's arm, follow the step-by-step guide below.

{% stepper %}
{% step %}
### Scale the arm

Select the `Arm` part and scale it to your desired length.

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### (Optional) Duplicate the stripes

Duplicate the stripes and move them to cover the entire arm.

If you like perfection, we recommend you to use the Archimedes plugin to help you duplicate the stripes.

<figure><img src="../../.gitbook/assets/image (34).png" alt="" width="146"><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

***

### Folding Flex Gate

To scale your Folding Flex Gate's arm, follow the step-by-step guide below.

{% stepper %}
{% step %}
### Move the folding arm

Select the `FoldArm` model in the Flex Gate, then move it until the grey attachment is positioned in the mid-point of your desired length.

<figure><img src="../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Scale the folding arm

Select the `Arm` part in the Flex Gate under the `FoldArm` model and scale it until it reaches the end of your desired length.
{% endstep %}

{% step %}
### Scale the arm

Select the `Arm` part in the Flex Gate under the `Barrier` model and scale it until it reaches the center of the grey attachment.

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### (Optional) Duplicate the stripes

Duplicate the stripes and move them to cover the entire arm.

If you like perfection, we recommend you to use the Archimedes plugin to help you duplicate the stripes.

<figure><img src="../../.gitbook/assets/image (34).png" alt="" width="146"><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

***

## Configuration

Each zone is configured separately. The configuration module can be found under the Network as `ZoneConfig`. All configurations have annotations to guide you.

<figure><img src="../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

### Authorization function

{% hint style="info" %}
Noren does not provide any scripting-related assistance for this configuration. If you suspect that there is a bug with this function, you can [contact us](https://app.gitbook.com/s/Rj5umFSPEKFhW4JqM6l9/support/contact) to report it.
{% endhint %}

In the configuration module, you'll find a function called `Authorization`.

The `Authorization` function can be customized to tell the system whether to open or not open any Flex Gates in the zone to allow a `Player` to enter.

To open the gate:

```luau
return true
```

To not open the gate:

```luau
return false
```

or

```luau
return "Reason why they were declined"
```
