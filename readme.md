# 🚀 Booting the Library

To load the Fusion Library, use the following command:

```lua
local Fusion = loadstring(game:HttpGet('https://github.com/kdfuzzy/FusionUI/blob/main/source.lua'))()
```


⚙️ Enabling Configuration Saving
Follow these steps to enable automatic configuration saving:

💡 Tips:
✅ Enable ConfigurationSaving in the CreateWindow function.
✅ Choose an appropriate FileName in the CreateWindow function.
✅ Select a unique flag identifier for each supported element you create.
✅ Place Fusion:LoadConfiguration() at the bottom of your script.

With these steps, Fusion will now automatically save and load your configuration settings. 🎉

# 🏦 Fusion Interface Guide

## 🏠 Creating a Window

To create a new window in Fusion, use the following code:

```lua
local Window = Fusion:CreateWindow({
   Name = "Fusion Example Window",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "Fusion Interface Suite",
   LoadingSubtitle = "by Fusion",
   Theme = "Default", -- Check https://github.com/kdfuzzy/FusionUI/blob/main/Themes.md

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

# 🎨 **USING THEMES IN FUSION**  

To apply a theme, you can either run:  

```lua
Window.ModifyTheme("ThemeIdentifier")
```
  
Or, when creating a window, add an argument named `Theme` and set its value (string) to the desired **Theme Identifier**:  

```lua
local Window = Fusion:CreateWindow({
   Name = "Fusion UI",
   Theme = "DarkBlue" -- Example Theme Identifier
})
```

---

# 🌈 **THEMES AVAILABLE**  

| **Theme Name**   | **Theme Identifier** |
|------------------|---------------------|
| Default         | `Default`           |
| Amber Glow     | `AmberGlow`         |
| Amethyst       | `Amethyst`          |
| Bloom         | `Bloom`             |
| Dark Blue     | `DarkBlue`          |
| Green         | `Green`             |
| Light         | `Light`             |
| Ocean         | `Ocean`             |
| Serenity      | `Serenity`          |

---

# 🎨 **CUSTOM THEMES**  

Fusion also allows you to use **custom themes** as of version **1.53**.  

To create a custom theme, replace the **Theme Identifier** in `ModifyTheme` or `CreateWindow` with a **table** containing theme properties.  

## **EXAMPLE CUSTOM THEME TABLE**  

```lua
local CustomTheme = {
    TextColor = Color3.fromRGB(240, 240, 240),

    Background = Color3.fromRGB(25, 25, 25),
    Topbar = Color3.fromRGB(34, 34, 34),
    Shadow = Color3.fromRGB(20, 20, 20),

    NotificationBackground = Color3.fromRGB(20, 20, 20),
    NotificationActionsBackground = Color3.fromRGB(230, 230, 230),

    TabBackground = Color3.fromRGB(80, 80, 80),
    TabStroke = Color3.fromRGB(85, 85, 85),
    TabBackgroundSelected = Color3.fromRGB(210, 210, 210),
    TabTextColor = Color3.fromRGB(240, 240, 240),
    SelectedTabTextColor = Color3.fromRGB(50, 50, 50),

    ElementBackground = Color3.fromRGB(35, 35, 35),
    ElementBackgroundHover = Color3.fromRGB(40, 40, 40),
    SecondaryElementBackground = Color3.fromRGB(25, 25, 25),
    ElementStroke = Color3.fromRGB(50, 50, 50),
    SecondaryElementStroke = Color3.fromRGB(40, 40, 40),
            
    SliderBackground = Color3.fromRGB(50, 138, 220),
    SliderProgress = Color3.fromRGB(50, 138, 220),
    SliderStroke = Color3.fromRGB(58, 163, 255),

    ToggleBackground = Color3.fromRGB(30, 30, 30),
    ToggleEnabled = Color3.fromRGB(0, 146, 214),
    ToggleDisabled = Color3.fromRGB(100, 100, 100),
    ToggleEnabledStroke = Color3.fromRGB(0, 170, 255),
    ToggleDisabledStroke = Color3.fromRGB(125, 125, 125),
    ToggleEnabledOuterStroke = Color3.fromRGB(100, 100, 100),
    ToggleDisabledOuterStroke = Color3.fromRGB(65, 65, 65),

    DropdownSelected = Color3.fromRGB(40, 40, 40),
    DropdownUnselected = Color3.fromRGB(30, 30, 30),

    InputBackground = Color3.fromRGB(30, 30, 30),
    InputStroke = Color3.fromRGB(65, 65, 65),
    PlaceholderColor = Color3.fromRGB(178, 178, 178)
}
```

## **APPLYING YOUR CUSTOM THEME**  

Once you’ve defined your **custom theme**, apply it like this:  

```lua
Window.ModifyTheme(CustomTheme)
```

Or, when creating the window:  

```lua
local Window = Fusion:CreateWindow({
   Name = "Fusion UI",
   Theme = CustomTheme
})
```

Now, Fusion will use your custom theme instead of a preset one. 🎨✨

## 🎮 Binding Keys in Fusion
Creating a Keybind


```local Keybind = Tab:CreateKeybind({
   Name = "Keybind Example",
   CurrentKeybind = "Q",
   HoldToInteract = false,
   Flag = "Keybind1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Keybind)
   -- The function that takes place when the keybind is pressed
   -- The variable (Keybind) is a boolean for whether the keybind is being held or not (HoldToInteract needs to be true)
   end,
})


# 📄 **Textual Elements in Fusion**

## **Creating a Label**

```lua
local Label = Tab:CreateLabel("Label Example", 4483362458, Color3.fromRGB(255, 255, 255), false) 
-- Title, Icon, Color, IgnoreTheme
Lucide Icon Support
You can now also use Lucide Icons with Fusion. To do so, replace the Image ID above 4483362458 with a string value of an icon name from Lucide Icons.

lua
Copy
Edit
local Label = Tab:CreateLabel("Label Example", "rewind")
This will set the icon to a rewind symbol from Lucide Icons.

For a full list of supported Lucide Icons, check Lucide Icons.

Credit to Lucide and Latte Softworks.

Updating a Label
lua
Copy
Edit
Label:Set("Label Example", 4483362458, Color3.fromRGB(255, 255, 255), false) 
-- Title, Icon, Color, IgnoreTheme
Creating a Paragraph
lua
Copy
Edit
local Paragraph = Tab:CreateParagraph({Title = "Paragraph Example", Content = "Paragraph Example"})
Updating a Paragraph
lua
Copy
Edit
Paragraph:Set({Title = "Paragraph Example", Content = "Paragraph Example"})
vbnet
Copy
Edit
