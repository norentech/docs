# Setup

{% hint style="success" %}
This setup guide is only for ZURA Display Pack V2.0 and above.
{% endhint %}

## Adding a new GUI

Want to make ZURA display your own GUI? Follow this step-by-step guide. If you want this GUI to be displayed on every display in your zone, go to [Using an transmitter](setup.md#using-an-transmitter).

1. Have your GUI ready and make sure it is an `SurfaceGui`. The GUI's face should be `Front`.
2. Locate the Screen part in the display. It may be somewhere else in the display depending on your display's model.\
   ![](<../../.gitbook/assets/image (14).png>)
3. Parent your `SurfaceGui` to the Screen part.
4. The display should now display the GUI. Power it on and try it out!

## Using an transmitter

The ZURA HDMI Transmitter makes it easy for you to display the same GUI in every display that's in the zone.

1. Have your GUI ready and make sure it is an `SurfaceGui`. The GUI's Face should be `Front`.
2. Locate your transmitter.
3. Parent the GUI to the transmitter. \
   ![](<../../.gitbook/assets/image (15).png>)<br>
4. All displays in the zone should now be displaying your GUI.

{% hint style="warning" %}
Content below this warning is not compatible for ZURA displays which have not been upgraded to Version 2.0. Please replace the Controller scripts with the new versions to continue. Updates are included with no additional cost.
{% endhint %}

## Overriding the default UI name

UIs in displays are automatically given a randomized name depending on where it is originally parented to.

Transmitter: ZURA-HT-0000\
In the display's screen: INTEGRATED-0000

The last 4 zeros are randomized numbers.

1. To override the default names, start by creating a new attribute called "ZR\_DisplayName" in your GUI. Make sure that Type is set to `string`.\
   ![](<../../.gitbook/assets/image (16).png>)
2. Set the attribute to any name you want.

## Standalone displays

All ZURA Displays can be parented to anywhere, and they'll still work. While for the Config, it can also be parented to the display's Controller or in the zone's API.

To use the same Config for a group of displays:

1. Parent the display to a ZURA Displays zone folder.

**OR**

To configure a standalone ZURA Display's behaviour:

1. Duplicate the ZoneConfig module from a ZURA Displays zone folder.\
   ![](<../../.gitbook/assets/image (4).png>)
2. Parent the Config to a ZURA Display's Controller script and name it "Config".\
   ![](<../../.gitbook/assets/image (5).png>)

Below is the default configuration for a display which does not have a Config in it's Controller script and is not parented to a zone:

| Configuration                   | Default          |
| ------------------------------- | ---------------- |
| InitiallyPowerOn                | Disabled (false) |
| AutoAdjust (Monitor S2 only)    | Enabled (true)   |
| WhitelistEnabled (User & Group) | Disabled (false) |

