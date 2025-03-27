# Items
> [!NOTE]
> Item and Recipes are identified via integer values. This, unfortunately, means that conflicts between mods are possible if we (as a community) 
> do not communicate and document which mod(ders) use which ID regions.
>
> See current ID Allocations [here](https://stalburg.net/index.php?title=Obenseuer/Modding#ID_Allocations)
<br>

# Item.json
Lavender allows you to add new Items to Obenseuer without editing the native Items.json file! <br>
Since Lavenders Item.json format is exactly the same as Obenseuers one (it even uses Obenseuers Code to read it) you can simply learn from
Obenseuers Item.json file how to add Items!

## Example
```json
[
    {
	"ID": 101,
	"Title": "Item Name",
	"Categories": [
	    "CategoryName"
	],
	"Value": 1,
	"Description": "Modded Item using AssetBundles",
	"Stackable": 99,
	"Appearance": {
		"Material": "",
		"SpritePath": "AssetBundleFileName#AB<AssetBundle-ImageName>",
		"ColorValue": "",
		"PrefabPath": "AssetBundleFileName#AB<AssetBundle-PrefabName>",
		"PrefabPathMany": ""
	},
	"Actions": [],
	"Attachments": {
		"Name": "",
		"Attachment1": "none",
		"Attachment2": "none"
	},
	"Meta": []
    },
    {
	"ID": 102,
	"Title": "Item Name 2",
	"Categories": [
            "CategoryName",
            "AnotherCategory"
	],
	"Value": 1,
	"Description": "Modded Item using Runtime Imports",
	"Stackable": 99,
	"Appearance": {
		"Material": "",
		"SpritePath": "item-img.png",
		"ColorValue": "",
		"PrefabPath": "item-object.obj",
		"PrefabPathMany": ""
	},
	"Actions": [],
	"Attachments": {
		"Name": "",
		"Attachment1": "none",
		"Attachment2": "none"
	},
	"Meta": []
    }
]
```

In order to add Items through your own Item.json you need to register it to Lavender.
```cs
string itemsPath = "Items.json";
Lavender.AddCustomItemsFromJson(itemsPath, LCMPluginInfo.PLUGIN_NAME);
```

<br>

## Keys
> [!NOTE]
> When explained as '???' then I'm either unsure what it is or how to explain it. Take a look at Obenseuer's Item.json for more infos on those Keys. 

<table>
<tr>
    <td>ID</td>
    <td>Unique ID for the Item, which is used in the Item Database to find an Item by its ID.</td>
</tr>
<tr>
    <td>Title</td>
    <td>The name of your Item.</td>
</tr>
<tr>
    <td>Categories</td>
    <td>An List of Item Categories. e.g. 'Food' or 'YourModName'</td>
</tr>
<tr>
    <td>Value</td>
    <td>The value of this item in OC.</td>
</tr>
<tr>
    <td>Description</td>
    <td>Description of your Object.</td>
</tr>
<tr>
    <td>Stackable</td>
    <td>The max stack size of this item. e.g. 64 :)</td>
</tr>
<tr>
    <td>Appearance</td>
    <td></td>
</tr>
<tr>
    <td>Material</td>
    <td>???</td>
</tr>
<tr>
    <td>SpritePath</td>
    <td>The path to place where the Item UI Image is stored. InGame Addressable, AssetBundle or local file path.</td>
</tr>
<tr>
    <td>ColorValue</td>
    <td>???</td>
</tr>
<tr>
    <td>PrefabPath</td>
    <td>The path to place where the Item Prefab (InGame Object when dropped) is stored. InGame Addressable, AssetBundle or local file path.</td>
</tr>
<tr>
    <td>PrefabPathMany</td>
    <td>Similar to PrefabPath, but this is the object shown, when you drop an stacked Item.</td>
</tr>
<tr>
    <td>Actions</td>
    <td>???</td>
</tr>
<tr>
    <td>Attachments</td>
    <td>???</td>
</tr>
<tr>
    <td>Meta</td>
    <td>???</td>
</tr>
</table>

<br>

## Appearance
> [!WARNING]
> Lavender supports loading images and obj's at runtime, but the obj importer is currently pretty buggy. For the best and more stable results use AssetBundle imports instead!


Lavender allows you to use three ways to define the Items appearance:

### 1. AssetBundles
AssetBundles are the recommended way to define the Item appearance.
In order to import an asset (Image/3D-Model/etc.) simply add the following value to an key:
```json
"key": "AssetBundlePath#AB<Bundle-Object>"
```
- Replace ``AssetBundlePath`` with the path to your AssetBundle file relative to your Mod.dll path.
- Replace ``Bundle-Object`` with the bundle path to your object.

So if your AssetBundle file has the name ``McMushroom`` and is in or will be placed in the same directory of your Mod.dll and in the root directory
of your AssetBundle there is the Image ``ShroomBurgerIMG`` the key-value-pair would look like this:
```json
"key": "McMushroom#AB<ShroomBurgerIMG>"
```

### 2. Runtime Imports
For runtime imports simply enter the relative file path to your Asset as an value.
For Example, if you have an PNG Image named ``McMushroom.png`` in the same directory as your Mod.dll enter:
```json
"key": "McMushroom.png"
```

### 3. Addressables
Last but not least you can still point to Obenseuer's Addressables just like the game does it in its Item.json.
