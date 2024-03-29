<br />
<div align="center">
  <a href="[https://github.com/othneildrew/Best-README-Template](https://discord.gg/PRdHZznczp)">
    <img src="https://github.com/Jay0Hx/esx_multicharacter/assets/119745695/85ffcb91-f2c0-4117-bb50-3d686f7519ef" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">'esx_multicharacter' (tweaked)</h3>

  <p align="center">
    Basically the same but with a logo and animation!
    <br />
    <br />
  </p>
</div>

### Jay0Hx Additions:
- Config.ServerLogo = "LINK_HERE" | Post an image link here (500x500).
- Config.EnableAnimation = "true" | If you don't want the animation, set this to false.
- Config.AnimationDict = "anim@mp_player_intcelebrationmale@wave" | Set this to your desired animation.
- Config.AnimationSecondary = "wave" | Set this to the secondary animation listed.
- Use this for animations: https://alexguirre.github.io/animations-list/
- Side note: I've tried to update this read-me as much as possible to reflect the latest version.

I haven't done much to this resource at all. I do not take credit for creating this resource and I would like to use this space to link the original repo along with the source that I used to modify. I have modified this resource because i always though the addition of a logo would be perfect for esx_multicharacter and I could never find a simple plug and play alternative, so here it is, please raise any issues you have and i'll get them fixed ASAP as i use this for my own server. If you are the creator of this resource and wish for me to remove this please contact me directly and I will be happy to do so. I don't plan to do much with this in the future in terms of updating it to make it better but I will fix any issues that are found with it.

- Original Repo: https://github.com/thelindat/esx_multicharacter
- New Source: [[esx_addons]/esx_multicharacter](https://github.com/rwain69/ESX-Legacy-Server-Pack/tree/main/%5Besx_addons%5D/esx_multicharacter)
- My Discord For Support: https://discord.gg/aGMfNhAxTj

NOTE: If you are already using the most up to date version of esx_multicharacter, i.e, if it looks like the pictures I have posted below, this resource is a straight swap and you can ignore everything below, just delete your version and replace it with this.

------------------------------------------------------------------------------------------------

### Requirements (ensure you are using the latest)
- [ESX Legacy](https://github.com/esx-framework/esx-legacy)
- [MySQL Async 3.3.2](https://github.com/brouznouf/fivem-mysql-async/releases/tag/3.3.2)
- [ESX Identity](https://github.com/esx-framework/esx_identity)
- [ESX Skin](https://github.com/esx-framework/esx_skin) - Not required if using illenium-appearance
- [Spawnmanager](https://github.com/citizenfx/cfx-server-data/tree/master/resources/%5Bmanagers%5D/spawnmanager) - Not required if using illenium-appearance


### Installation
- Modify your ESX config with `Config.Multichar = true`
- Set your database name for `Config.Database` in server/main.lua
- All owner and identifier columns should be set to `VARCHAR(60)` to ensure correct data entry
	- The resource will attempt to set columns automatically

### Conflicts
* The following resources should not be used with ESX Legacy and can result in errors
	- essentialmode
	- basic-gamemode
	- fivem-map-skater
	- fivem-map-hipster
	- default_spawnpoint

### Common issues
#### Black screen / loading scripts
	- Download and run all requirements
	- Use a fresh spawnmanager as many people alter the code
	- Ensure none of the conflicting resources are enabled
#### mysql-async duplicate entry
	- You have not increased the VARCHAR size of the table holding identifiers - usually `owner` or `identifier`

#### The menu interface is esx_menu_default - you can use any version if you want a different appearance
![image](https://github.com/Jay0Hx/esx_multicharacter/assets/119745695/ea789729-9167-43c0-b1d6-e5bb1cfbbc0c)

### Relogging
- Do not enable this setting if you do not intend to properly set up relog support
- Requires the latest update for ESX Status (prevents multiple status ticks from running)
- Add the following events to resources that require support for relogging, or
- Add them to [@esx/imports.lua](https://github.com/esx-framework/es_extended/blob/legacy/imports.lua) (and use the imports in your resources)
```lua
RegisterNetEvent('esx:playerLoaded')
AddEventHandler('esx:playerLoaded', function(xPlayer)
	ESX.PlayerData = xPlayer
 	ESX.PlayerLoaded = true
end)

RegisterNetEvent('esx:onPlayerLogout')
AddEventHandler('esx:onPlayerLogout', function()
	ESX.PlayerLoaded = false
	ESX.PlayerData = {}
end)
```
- Any threads using ESX.PlayerData in a loop should check if ESX.PlayerLoaded is true
	- This ensures the resource does not error after relogging, or while on character selection
	- Setup correctly you can break your loops and trigger them again after loading
	- Refer to my [boilerplate](https://github.com/thelindat/esx_legacy_boilerplate) for more information and usage examples

### Notes
- This resource is not compatible with ExtendedMode or previous versions of ESX
- Legacy, skin, and identity must be updated to at least the minimum commits specified above
- Characters are stored in the users table as `char#:license` - if you need to use a different identifier then you need to modify ESX itself
- Character deletion does not require manual entries for the tables to remove
- As characters are stored with unique identifiers, there is no excessive queries being executed
	
### Kashacters
- This project is forked from the [kashacters multicharacter resource](https://github.com/FiveEYZ/esx_kashacter)
- Most of the code has been entirely rewritten
- KASH has given permission for this resource to use his code and the addition of a license
- The license obviously does not apply to previous versions and KASH has stated his resource is free to be used however



## Notice
Copyright© 2021 Linden and KASH

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see https://www.gnu.org/licenses.


### Thanks to KASH, XxFri3ndlyxX, and all those who have contributed
