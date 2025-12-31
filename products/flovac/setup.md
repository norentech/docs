# Setup

{% hint style="success" %}
This setup guide is only for flo Vehicle Access Control V2.2 and above. [Looking for Card Reader Pro's setup guide?](setup-crp.md)
{% endhint %}

## Our recommended setup

In this section, you'll learn how to set up your system using our recommended setup.

Firstly, you'll need:

* Card Reader (DWProx or Card Reader Pro)
* LPR camera
* Flex Gate (Normal or Folding)
* Welcome Screen (optional)

Assuming you already have your lane built, follow the steps below.



1. First, move your Flex Gate to the left side of the lane like the picture below. To know how to scale your gate, refer to the [Scaling your gates](setup.md#scaling-your-gates) section.<br>

<figure><img src="../../.gitbook/assets/image (27).png" alt="Vehicle lane with a Flex Gate on the left side." width="375"><figcaption></figcaption></figure>

2. Position your Welcome Screen in front of the gate hub and rotate it to face the driver when they approach. Refer to the picture below. (Optional)

<figure><img src="../../.gitbook/assets/image (28).png" alt="Vehicle lane with Flex Gate and Welcome Screen on the left side." width="375"><figcaption></figcaption></figure>

3. Next, position your LPR camera in front of the Welcome Screen if any, while ensuring that it is not blocking the driver's view of the Welcome Screen. After positioning it, move the DetectionArea part to the center of your lane and in front of the Flex Gate's barrier. Refer to the picture below.

<figure><img src="../../.gitbook/assets/image (30).png" alt="Vehicle lane with Flex Gate, Welcome Screen, and LPR camera on the left side." width="375"><figcaption></figcaption></figure>

The blue box in the picture above is the outline of the DetectionArea part.

4. Position the card reader to the left side of the lane as well, but keep it facing the driver's window. Ensure it doesn't block the view of the Welcome Screen, but optionally also keep it out of the "LPR camera's view" to keep it realistic. Refer to the picture below.

<figure><img src="../../.gitbook/assets/image (32).png" alt="Vehicle lane with Flex Gate, Welcome Screen, LPR camera and Card Reader on the left side." width="375"><figcaption></figcaption></figure>

## Scaling your gates

In this section, you'll learn how to scale your gate's arm. As there are 2 different Flex Gates, refer to the section for the gate you're trying to scale.

{% hint style="info" %}
This section may be difficult to understand. Please take your time to understand the what the step asks you to do.
{% endhint %}

[Flex Gate](setup.md#flex-gate)\
[Folding Flex Gate](setup.md#folding-flex-gate)

### Flex Gate

To scale your Flex Gate, follow these steps:

1. First, select the Arm part and scale it to the length you want.

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

2. Next, duplicate the stripes and move them to cover the entire arm if you'd like. Optionally, it's easier to use the Archimedes plugin.

<figure><img src="../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

### Folding Flex Gate

To scale your Folding Flex Gate, follow these steps:

1. Select the FoldArm model in the gate, then move it till the grey attachment is in the middle of the length you want.

<figure><img src="../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

2. Select the Arm part which is under the Barrier model then scale it until it reaches the center of the grey attachment in the FoldArm.

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

3. Optionally, you can duplicate the stripes in Barrier and FoldArm to cover the entire arm. It's easier to duplicate the stripes using the Archimedes plugin.

<figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

## Configuration

The ZoneConfig module for the whole zone can be found under the Network. All configurations have annotations beside them.

<figure><img src="../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

## Authorization function

In the ZoneConfig module, you can find a function called "Authorization".

The Authorization function can be customized to execute any code you'd like before the gate opens for the player. In the function, you can also decline the player entry by adding "return false" or returning a string ("") instead to tell the player why they were declined.

{% hint style="info" %}
Using this configuration requires basic developer knowledge.
{% endhint %}
