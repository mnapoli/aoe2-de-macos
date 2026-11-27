# Running Age of Empires 2 DE on macOS

There are too many outdated instructions online. This place is meant to contain the most up-to-date instructions for running Age of Empires 2 DE on macOS (with multiplayer support).

## With Crossover

You need MacOS Big Sur 11.1 or greater.

- Install [Crossover](https://www.codeweavers.com/crossover) (requires a paid license but there's a free trial)
- Create a new Windows 10 bottle in Crossover
- Install Steam
- Open steam and install AOE2:DE
- In the bottle, install "DXVK (Builtin)"
- In the bottle, install "DirectX for modern games"
- In the bottle settings, enable DXVK
- In the bottle settings, optionally enable "High resolution" to enable Retina display resolution
- In Steam, optionally set AOE2:DE launch parameters to `SKIPINTRO`

Older versions of this guide replaced `ucrtbase.dll` and set `concrt140` and `ucrtbase` to `native, builtin`. This is no longer needed with Crossover 26.x, and in a bottle without a native Visual C++ runtime it stops replays from loading ([measurements](https://github.com/kyrios/TrebuchetApp/blob/main/fixes/crossover-ucrt-note/README.md#m1-pro--crossover-263-in-game-measurement)).

Feel free to send pull requests to update this guide.

### Fixing lag with Trebuchet

If the game lags in Crossover (especially with units selected or health bars shown), [Trebuchet](https://trebuchetapp.com) ([source](https://github.com/kyrios/TrebuchetApp)) is a free, open-source launcher that runs AOE2:DE through Crossover with performance fixes on Apple Silicon. It uses the Crossover/Steam setup above and doesn't modify your bottle. It also supports [CaptureAge](https://captureage.com). Requires macOS 26 or 27.

In our tests on an M1 Pro (macOS 26, same replay, compared to plain Crossover with DXVK): 8× the FPS paused with units selected, 7.3× while playing, +52% paused with nothing selected, and far fewer freezes of 150 ms or more.

## Without Crossover

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
