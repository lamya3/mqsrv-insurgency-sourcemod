# mqsrv-insurgency-sourcemod

<br>
<div align=center>
README also available in Chinese simplified: <a href="https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/README_zh_CN.md">中文自述文件</a>
</div>
<br>

A source code repository of sourcemod plugins, which can be used for game insurgency.

So why did I create this repository:  I closed my server few months ago, but the code of some plugins on my server are opensource. Base on their licences, I have to release them; for another, many senior sourcemod coder from sourcemod community, steam discussions, discord and github help me a lot with programming. Although I'm not good at coding at all, but I still hope this repository can help more sourcemod novices or server owners like me.

Most of my code and GPLv2 sourcecode from other authors I was modified will be released in this repository, only GPLv2. If it helps you, please give a star for me or support original author.

(There may be ambiguity or difficult to understand what's mean in README, excuse my poor English ...)

Attention: most of plugins in this repository can only work in insurgency2 cooperative mode normally.

---

### Contents

- [Level chooser](#level-chooser)
- [Playlist coop enforcer](#playlist-coop-enforcer161162)

---

### Level chooser

##### Description

A very simple debug plugin. You can use it to change your current game level by a command. If you compile this plugin's sourcecode directly, you can only use it on game mode outpost or survival,  and change level between 0 to 100. (IDK why outpost have level 100 even more......)

##### Plugin's smx

[level chooser.smx](https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/insurgency/addons/sourcemod/plugins/level%20chooser.smx)

##### Sourcecode

[level chooser.sp](https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/insurgency/addons/sourcemod/scripting/level%20chooser.sp)

##### Cvars, commands and usage

```c
//commands
sm_lv <int>    //Just use it in client console and input a level number to replace <int> (integer between 0 to 100)
```

##### Source and license

[Polaris](https://github.com/lamya3) ([GPLv2](https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/LICENSE))

### Playlist coop enforcer(1.6.1,1.6.2)

##### Description

Yeah, you read that right... there are 2 code versions about this plugins, they are very simple and they have some little buggy. This plugins can enforce your playlist as coop.playlist, even use illegal map like dust2 in playlist coop! version 1.6.1 use `HookConVarChange()` instead of a 0.1sec repeat timer in version 1.6.2, I think that 1.6.1 use less performance but 1.6.2 is more reliability. I have no choice, so I release both of them and let you make a decision.

If you use 1.6.1, you have to start your server with bulit-in maps like `+map sinjar_coop checkpoint`, then change to custom map manually ( just use map command in console). maybe no need to do that if you use 1.6.2

Finally, both 2 versions incompatible with bulit-in map in mapcyclelist.txt like `sinjar_coop, tell etc.`, you can not vote any custom maps again when you rtv and changed to a bulit-in map.

##### Plugin's smx

[Playlist coop enforcer 1.6.1.smx](https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/insurgency/addons/sourcemod/plugins/Playlist%20coop%20enforcer%201.6.1.smx)

[Playlist coop enforcer 1.6.2.smx](https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/insurgency/addons/sourcemod/plugins/Playlist%20coop%20enforcer%201.6.2.smx)

##### Sourcecode

[Playlist coop enforcer 1.6.1.sp](https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/insurgency/addons/sourcemod/scripting/Playlist%20coop%20enforcer%201.6.1.sp)

[Playlist coop enforcer 1.6.2.sp](https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/insurgency/addons/sourcemod/scripting/Playlist%20coop%20enforcer%201.6.2.sp)

##### Cvars, commands and usage

```c
//No commands for them, just put it in plugins folder.

//1.6.1
//To use this plugin: you have to set your map as game's built-in map in start commands, like +map tell_coop checkpoint
//in addition, inside the game, you need to change maps between built-in map and custom maps aleast once
//or else, your server will only run in playlist custom, even use command map <map name>! you have to do like mentioned above.

//1.6.2
//it should be work well directly?

//Known bugs: 
//1.Throw can't find prop errors when changing map, but no hardly affects for game and plugins functions; 
//2.Server will not hibernate, cuz for maintenance functions;
//3.You can't vote a custom map when you change your map from a custom map to built-in map last time, so you have to use custom map only in mapcyclelist.txt (but built-in map when server start).
```

##### Source and license

[Polaris](https://github.com/lamya3) ([GPLv2](https://github.com/lamya3/mqsrv-insurgency-sourcemod-release/blob/main/LICENSE))
