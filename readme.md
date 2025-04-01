# 🚀 Booting the Library

To load the Rayfield Library, use the following command:

```lua
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
```


⚙️ Enabling Configuration Saving
Follow these steps to enable automatic configuration saving:

💡 Tips:
✅ Enable ConfigurationSaving in the CreateWindow function.
✅ Choose an appropriate FileName in the CreateWindow function.
✅ Select a unique flag identifier for each supported element you create.
✅ Place Rayfield:LoadConfiguration() at the bottom of your script.

With these steps, Rayfield will now automatically save and load your configuration settings. 🎉

# 🏦 Fusion Interface Guide

## 🏠 Creating a Window

To create a new window in Fusion, use the following code:

```lua
local Window = Fusion:CreateWindow({
   Name = "Fusion Example Window",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "Fusion Interface Suite",
   LoadingSubtitle = "by Fusion",
   Theme = "Default", -- Check https://docs.sirius.menu/fusion/configuration/themes

   DisableFusionPrompts = false,
   DisableBuildWarnings = false, -- Prevents Fusion from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },

   Discord = {
      Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Fusion may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Fusion to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})
```

---

## 🗂 Creating a Tab

To create a tab in Fusion, use:

```lua
local Tab = Window:CreateTab("Tab Example", 4483362458) -- Title, Image
```

### 🎨 Lucide Icon Support  

Fusion now supports **Lucide Icons**. Instead of using an image ID, you can specify an icon name from **Lucide Icons**:

```lua
local Tab = Window:CreateTab("Tab Example", "rewind")
```

This will set the Tab icon to a **rewind** symbol from Lucide Icons.

---

## 📌 Creating a Section

```lua
local Section = Tab:CreateSection("Section Example")
```

### ✏️ Updating a Section

```lua
Section:Set("Section Example")
```

---

## 🔹 Creating a Divider

```lua
local Divider = Tab:CreateDivider()
```

### ✏️ Updating a Divider

```lua
Divider:Set(false) -- Whether the divider's visibility is set to true or false.
```

---

## ❌ Destroying the Interface

To completely remove the Fusion interface, use:

```lua
Fusion:Destroy()
```

---

**Credit to Lucide and Latte Softworks**  
This guide helps you effectively use Fusion to manage your UI elements! 🚀
