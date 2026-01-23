# Setup

{% hint style="success" %}
This setup guide is only for ParkingPal V2.0 and above.
{% endhint %}

***

## Setting up a parking sensor

{% stepper %}
{% step %}
### Get your parking spots ready

If you do not have your parking spots yet, you can use the pre-made parking spot which is already set up together with the sensor. It is easier to duplicate it with Archimedes.

To use Archimedes to duplicate the pre-made parking spots:

1. Select the pre-made parking spot.
2. Set the direction to Z.
3. Select/deselect Swap Sides depending on your preferences.
4. Set Alignment to Middle.
5. Set Amount to the amount of spots you want in the row.

<figure><img src="../../.gitbook/assets/image (24).png" alt="" width="188"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Set up your parking sensor

Move the parking sensor to your desired position. Then, scale the `DetectionArea` part and ensure that it covers the entire parking spot, excluding the outlines.
{% endstep %}
{% endstepper %}

***

## Setting up an information sign for multiple zones

In this section, we will guide you on how to set up the information sign that has the capability to display up to 3 zones.

{% stepper %}
{% step %}
### Locate the configuration

Locate the `Configuration` instance in the information sign.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Locate the configuration values

You will find 1 `ObjectValue` for each zone display on the information sign. Choose a value to set up.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Set the value

Set the `Value` property of the zone display's `ObjectValue` to your desired zone folder.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

***

## Parking sensor states

Parking sensors have a `CurrentState` attribute which you can use to find out whether a parking spot is open, occupied, or unavailable.

Your parking sensor's `CurrentState` attribute will automatically update to "Open" or "Occupied" automatically when a vehicle enters/leaves.

You can also set your parking sensor's `CurrentState` to "Unavailable", which will make the parking sensor's light blink orange depending on your configuration. This is used to indicate that a parking spot is unavailable. Your parking sensor won't detect for vehicles when unavailable, and it will never automatically become Unavailable.

{% hint style="warning" %}
Never modify the DeviceType attribute! The system will not recognize the parking sensor if you do so.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>
