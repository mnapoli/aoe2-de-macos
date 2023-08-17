# Running Age of Empires 2 DE on macOS Without Crossover

Someone on reddit wrote a guide on how to play aoe 2 de on mac os without needing crossover. https://www.reddit.com/r/aoe2/comments/150t2v1/aoe_2_de_fix_on_mac_using_wineskin_winery/

Copy pasted here just in case

Here's a quick guide on how to get it running (should work on Intel and Apple silicon Macs):

- Start by installing Homebrew (https://brew.sh/) by opening terminal and typing the following:

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

Install Wineskin Winery (https://github.com/Gcenx/WineskinServer) by typing the following in terminal:

`brew install --cask --no-quarantine gcenx/wine/wineskin`

- Open the Wineskin Winery app that should appear with the rest of your apps in your Applications folder.

- Make sure you have the latest wrapper (currently 2.9.1.9 or higher) and install the latest engine (currently WS11WineCX64Bit22.1.1-8 or higher).
 
- Click on the “Create New Blank Wrapper” button at the bottom. I named my wrapper “Steam” since it’ll be used for all my steam games. Wineskin Winery will create a new wrapper that will appear in “/Macintosh HD/Users/[YOUR USER NAME]/Applications/Wineskin/” folder (not the same Applications folder that has all your applications).
 
- If Wineskin Winery freezes and becomes unresponsive, just give it some time. If it doesn’t fix itself in 5 minutes, then just kill it by holding the cmd+option+esc keys to get the force quit menu and kill the unresponsive process. Usually, the wrapper will be created successfully, so go ahead and use it directly.
     
- Open Finder and navigate to “/Macintosh HD/Users/[YOUR USER NAME]/Applications/Wineskin/”.
     
- Right-click on the new Steam wrapper and click on “Show Package Contents”.
     
- Click on the Wineskin app in there. This will be how you control the wrapper's settings.
    
- You can click on “Install Software” if you have a .exe file, but in the case of Steam, it’s better to install it through Winetricks as explained in the next steps.
     
- Click on “Winetricks”.
-It might take some time to load, so be patient :)
     
- Search for Steam and install it with vcrun2019 or vcrun2022. It may take some time, so be patient.
-Wait until it’s done installing and it should work afterwards! Just close the winetricks page and launch the wrapper directly like you’d do with any other app.



# Running Age of Empires 2 DE on macOS with Crossover

There are too many outdated instructions online. This place is meant to contain the most up-to-date instructions for running Age of Empires 2 DE on macOS (with multiplayer support).

> **Warning**
> 
> There seems to be an issue with the latest Steam update, follow this thread: https://www.codeweavers.com/support/forums/general/?t=27;msg=279837
>
> **Update:** there are also issues with the latest update of AoE 🤡, follow this thread: https://www.codeweavers.com/compatibility/crossover/forum/age-of-empires-ii-definitive-edition?;msg=278919
>
> If you know how to run AoE without Crossover on Mac, please send a pull request with updated instructions! It might be time to move to Proton or whatever alternative there is.

You need MacOS Big Sur 11.1 or greater.

- Install [Crossover](https://www.codeweavers.com/crossover) (requires a paid license but there's a free trial)
- Create a new Windows 10 bottle in Crossover
- Install Steam
- Open steam and install AOE2:DE
- In the bottle, install "DXVK (Builtin)"
- In the bottle, install "DirectX for modern games"
- In the bottle settings, enable DXVK
- In the bottle settings, optionally enable "High resolution" to enable Retina display resolution
- Download the patched [`ucrtbase.dll` here](https://community.pcgamingwiki.com/files/file/2081-ucrtbasedll-extracted-from-microsoft-visual-c-2015-redistributable-update-3-rc/)
- In the Crossover bottle, click "Open C: drive" and navigate to `C:/Windows/System32`
- Put the `ucrtbase.dll` file you downloaded in that folder (overwrite the existing file)
- Open the Wine configuration panel: in "Libraries" add `concrt140.dll` and `ucrtbase`. They should show up as `native, builtin` in the list.
- In Steam, optionally set AOE2:DE launch parameters to `SKIPINTRO`

Feel free to send pull requests to update this guide.



