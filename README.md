<br />
<div align="center">
  <a href="[https://github.com/othneildrew/Best-README-Template](https://discord.gg/PRdHZznczp)">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Best-README-Template</h3>

  <p align="center">
    An awesome README template to jumpstart your projects!
    <br />
    <br />
  </p>
</div>








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
![image](https://user-images.githubusercontent.com/65407488/126976325-17cc3241-bb9e-451f-a6ed-610a8ef52fa5.png)

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


[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
