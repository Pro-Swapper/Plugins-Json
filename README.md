# Pro Swapper's Plugins Tutorial


### What are plugins?
Plugins are a way to implement items in Pro Swapper yourself. They can be created by the Pro Swapper Developer(s) (yes there's only 1 developer Kye#5000) or by the community

### What about the old plugins?
Yes, Pro Swapper did have plugins a while ago, those plugins will not be compatible with these new plugins as Fortnite's files have changed and they're just too outdated to use.

### What's Json?
Json (or JavaScript Object Notation) is a way to store data in text. Pro Swapper's Plugins will be using this Json format to store and read plugins. This means you need an understanding of Json to make Pro Swapper Plugins. Json is not hard to learn. If you want to learn Json there is this very informative video you can watch [here](https://youtu.be/iiADhChRriM)


## Making a plugin
To make a plugin you will need a text editor, you can use Notepad however it doesn't point out errors with the plugin you're making.
You can use one of the following text editors to make your plugin.

- [JSON Editor Online](https://jsoneditoronline.org/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Notepad++](https://notepad-plus-plus.org/downloads/)

I would recommend just using the JSON Editor Online as you don't have to download anything and it's straight from the browser.



Example Pro Swapper Plugin:
```json
{
	"SwapsFrom": "Assault Trooper",
	"SwapsTo": "Sparkle Specialist",
	"FromImage": "zmpyc8x.png",
	"ToImage": "WyDkv0V.png",
	"Note": "This is a note",
	"Asset": [
		{
			"Search": [
				"/Game/Characters/Player/Female/Medium/Bodies/F_Med_Soldier_01/Skins/TV_19/Materials/F_MED_Commando_Body_TV19.F_MED_Commando_Body_TV19"
			],
			"Replace": [
				"/Game/Characters/Player/Female/Medium/Bodies/F_Med_Soldier_01/Skins/BR_05/Materials/F_MED_Commando_Body_BR05.F_MED_Commando_Body_BR05"
			],
			"AssetPath": "/Game/Athena/Heroes/Meshes/Bodies/CP_015_Athena_Body"
		}
	]
}
```

Here I'll be explaining the JSON Keys from above.

- `SwapsFrom` is the Skin/Item the item will Swap From. This is the item the player needs in their account
- `SwapsTo` is the Skin/Item the item will Swap To. This is the item you want to have
- `FromImage` is the [imgur](https://imgur.com/upload) image url of the item it swaps from.The url is cut off so it's just the end. To get this follow [this Tutorial](https://youtu.be/WHN877B_cq0)

The imgur url can either be in one of the following formats:
- `https://i.imgur.com/Z6tPcSd.png`
- `Z6tPcSd.png`

The second one is recommend because it makes the json filesize smaller but choose whichever one you prefer


- `ToImage` is the imgur image url of the icon it swaps to.
- `Note` This is a Note about your item. You can make this something like "Made by Kye#5000" or "This is the default style". A note looks like this:

![image](https://user-images.githubusercontent.com/36981621/124550161-9b1e6d80-de73-11eb-9718-98afcd6e4954.png)

Here comes the tricky part, the actual swapping mechanic.

Inside the `Asset` key is an array of Assets.
An asset is a file inside Fortnite. For this example we're using, Assault Trooper To Sparkle Specialist only needs to change the body. Our `AssetPath` is set to `/Game/Athena/Heroes/Meshes/Bodies/CP_015_Athena_Body` because that's where the CharacterPart for Assault Trooper's is. For a full in depth Tutorial on FModel watch [@iFireMonkey](https://twitter.com/iFireMonkey)'s [FModel Tutorial](https://youtu.be/ZD2zqOyw7ZI).

- `Search` is the string you want to search
- `Replace` is the string you want to replace

The search and replace are a string array so you can put more than 1 string on it.
Here's an example:

```json
{
 "Search": [
  "Search1",
  "Search2"
 ],
 "Replace": [
  "Replace1",
  "Replace2"
 ]
}
```
`Search1` will always be replaced by `Replace1`, `Search2` will always be replaced by `Replace2`.


That's pretty much it. If there's anything made unclear in this tutorial [open an issue](https://github.com/Pro-Swapper/Plugins-Json/issues)
