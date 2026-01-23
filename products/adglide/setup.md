# Setup

***

## Immersive Ads

If your game is eligible for Immersive Ads, it's recommended that you enable Immersive Ads on your system to maximize your revenue. However, enabling Immersive Ads on your AdGlide system comes with some pros and cons.

### **Pros**

* Earn ad revenue from your advertisement displays.
* Automatically serve image advertisements when immersive advertisements aren't being served.

### **Cons**

* Animations will not apply to image advertisements.
* Image advertisements will not have sound.
* The `ScaleType` configuration will not be applied.

***

## Resolutions

For your information, the advertisement displays are designed to be used with these resolutions (width x height).

* Landscape: 1920px x 1080px
* Portrait: 1080px x 1920px
* Banner: 1500px x 1000px

***

## Adding an advertisement

{% hint style="info" %}
Adding an advertisement may require basic scripting knowledge.
{% endhint %}

Here's 2 examples of ways you can add an advertisement to be displayed.

### **Example Ad Format 1**

```lua
['Example Advertisement'] = {
		DecalId = "", -- Image ID, not Asset ID
		SoundId = "0", -- Sound to play when the ad is shown
		ScaleType = "Stretch", -- The scale type for the ad (Stretch | Fit)
		Orientations = { -- Compatible orientations (Landscape | Portrait | Banner)
				Landscape = "Decal id here",
				Portrait = "Decal id here",
				Banner = "Decal id here",
		}
},
```

### **Example Ad Format 2**

```lua
['Example Advertisement'] = {
		DecalId = "Decal id here", -- Image ID, not Asset ID
		SoundId = "0", -- Sound to play when the ad is shown
		ScaleType = "Stretch", -- The scale type for the ad (Stretch | Fit)
		Orientation = "Landscape" -- Compatible orientations (Landscape | Portrait | Banner)
},
```

### Step-by-step guide

{% stepper %}
{% step %}
### Find the right format for your advertisement

The format that should be used depends on your advertisement. Please see below.

Multiple orientations: [#example-a-d-format-1](setup.md#example-a-d-format-1 "mention")\
Single orientation: [#example-a-d-format-2](setup.md#example-a-d-format-2 "mention")

Once you have found the right format for your advertisement, copy and paste it into `SysConfig.Advertisements.`

{% hint style="info" %}
It's recommended to keep each advertisement separated by a newline.
{% endhint %}
{% endstep %}

{% step %}
### Name your advertisement

Set your advertisement's name to a name _**unique**_**&#x20;from other advertisements** by modifying "Example Advertisement".

{% hint style="warning" %}
Your advertisement's name will be underlined with red if it is sharing the same name as another advertisement. Watch out for red bars on the scrollbar!
{% endhint %}
{% endstep %}

{% step %}
### Set the advertisement's decal ID

{% hint style="info" %}
Due to Roblox limitations, you can only set your advertisement's decal ID to an asset ID of an **image**. This is different from a **decal**.
{% endhint %}

If your advertisement has multiple orientations, add the asset ID of the **images** in the `Orientations` table. Remove the orientations that you will not be using from the `Orientations` table.

If your advertisement is for a single orientation, enter the asset ID of the **image** in `DecalId`.
{% endstep %}

{% step %}
### Set the advertisement's sound ID

{% hint style="warning" %}
Make sure that you have permission to use the `Sound`  that you're setting for your advertisement. The `Sound` will not be played if you do not have permission.
{% endhint %}

{% hint style="info" %}
The `Sound` may take some time to load before it can be played when your advertisement is displayed.
{% endhint %}

{% hint style="info" %}
If you have `RandomizeAds` and `AutomaticallySync` enabled, all displays will wait if one or more displays are displaying advertisements with sound until it's done.
{% endhint %}

If you'd like a `Sound` to be played when your advertisement is displayed, enter the sound ID in `SoundId`.
{% endstep %}

{% step %}
### Set the advertisement's scale type

Set the `ScaleType` of your advertisement to be either "Stretch" or "Fit" (case-sensitive). Here's the difference:

* Stretch: Stretches your advertisement's image to maximize space on the screen.
* Fit: Resizes your advertisement's image to maximize space on the screen while maintaining its aspect ratio.
{% endstep %}
{% endstepper %}
