# Setup

{% hint style="success" %}
This setup guide is only for ParkingPal V2.0 and above.
{% endhint %}

## Setting up an parking sensor

Firstly.. If you have not made the outlines for parking spots yet, you can use the premade parking spot outline which is already set up together with the sensor. To make your life easier, we recommend you use the Archimedes plugin to make rows of parking spots.

To use Archimedes to make rows:

1. Select the parking sensor.
2. Set the direction to Z.
3. Select/deselect Swap Sides depending on your preferences.
4. Set the Alignment to Middle.
5. Set the Amount to the amount of spots you want in the row.

<figure><img src="../../.gitbook/assets/image (24).png" alt="" width="188"><figcaption><p>Archimedes configuration</p></figcaption></figure>



And if you'd like, you can put some Parking Info Signs around so your customers can know the amount of parking spots available.

## Setting up a info sign with multiple zones

There are 2 types of info signs that come with ParkingPal. One that shows parking information for the current zone, and the other with the capability to show up to 3 zones.

This section is for setting up the info sign that can display up to 3 zones.

1. Locate the Configuration instance in the info sign.\
   ![](<../../.gitbook/assets/image (6).png>)
2. You will find 3 `ObjectValue`s for each zone. Choose a zone display to set up.\
   ![](<../../.gitbook/assets/image (7).png>)
3. Set the Value property to the Zone folder you wish to set it to.\
   ![](<../../.gitbook/assets/image (9).png>)
4. Done!

## Parking sensor states

Parking sensors have a CurrentState attribute which you can use to find out whether a parking sensor is open/occupied/unavailable.

Your parking sensor's CurrentState attribute will automatically update to "Open" or "Occupied" automatically when a vehicle parks/leaves.

You can also set your parking sensor's CurrentState to "Unavailable", which will make the parking sensor's light blink orange depending on your configuration. This is used to indicate that a parking spot is unavailable. Your parking sensor won't detect for vehicles when unavailable, and it will never automatically become Unavailable.

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption><p>The attributes in a Parking Sensor.</p></figcaption></figure>
