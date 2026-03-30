# API Documentation

## Information

**Type:** BindableEvent\
**Location:** Product folder -> API\
**Execution example:**

```lua
API:Fire(CommandName, ...) -- additional parameters can be added if needed
```

## Commands

### QueueAd

Adds an advertisement to the queue of all devices. If advertisements fail the validation check, they will not be queued.

**Parameters:**

| Argument               | Description                                                                   |
| ---------------------- | ----------------------------------------------------------------------------- |
| Advertisement: `table` | The advertisement to queue (see code examples).                               |
| Prioritize: `boolean`  | Whether the advertisement should be added to the first position in the queue. |

**Code example 1:**

<pre class="language-lua"><code class="lang-lua">local API = workspace["Noren AdGlide Advertisement System"].API

API:Fire("QueueAd", {
	Name = "Example Advertisement",
	DecalId = "", -- Image ID, not Asset ID
<strong>	SoundId = "0", -- Sound to play when the ad is shown
</strong>	ScaleType = "Stretch", -- The scale type for the ad (Stretch | Fit)
	Orientations = { -- Compatible orientations (Landscape | Portrait | Banner)
		Landscape = "Decal id here",
		Portrait = "Decal id here",
		Banner = "Decal id here",
	}
}, true)
</code></pre>

**Code example 2:**

```lua
local API = workspace["Noren AdGlide Advertisement System"].API

API:Fire("QueueAd", {
	Name = "Example Advertisement",
	DecalId = "Decal id here", -- Image ID, not Asset ID
	SoundId = "0", -- Sound to play when the ad is shown
	ScaleType = "Stretch", -- The scale type for the ad (Stretch | Fit)
	Orientation = "Landscape" -- Compatible orientations (Landscape | Portrait | Banner)
}, true)
```

### SetTopbar

Sets the topbar text on all Portrait advertisement displays.

| Argument          | Description                           |
| ----------------- | ------------------------------------- |
| NewText: `string` | The new text to be set as the topbar. |

**Code example:**

```lua
local API = workspace["Noren AdGlide Advertisement System"].API

API:Fire("SetTopbar", "Hello world!")
```
