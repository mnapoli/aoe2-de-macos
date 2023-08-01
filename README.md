# Running Age of Empires 2 DE on macOS

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

