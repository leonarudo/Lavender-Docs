# Recipes
> [!NOTE]
> Item and Recipes are identified via integer values. This, unfortunately, means that conflicts between mods are possible if we (as a community) 
> do not communicate and document which mod(ders) use which ID regions.
>
> See current ID Allocations [here](https://stalburg.net/index.php?title=Obenseuer/Modding#ID_Allocations)
<br>

# Recipes.json

<br>

# Example

*recipes.json from ``norbby42 (Quackers)`` [Smuggler's Pack Mod](https://github.com/norbby42/SmugglersPack/)*
```json
[
  {
    "ID": 400001,
    "Name": "Smuggler's Pack Insert",
    "Type": "Sewing",
    "useOnlyStolenItems": false,
    "allowedNonStolenItemsIds": [],
    "keepItemOwnerOnFail": false,
    "disableJunkSpawn": false,
    "Appearance": {
      "SpritePath": "",
      "CraftShowModel": true,
      "itemToShow": {
        "ID": 400001,
        "name": "Smuggler's Pack Insert'",
        "itemnamespace": null
      }
    },
    "RecipeRequired": false,
    "RequiredConditions": [],
    "ExcludingConditions": [],
    "RecipeTags": [
      "Open Sewer Magazine"
    ],
    "variantItemCategory": "None",
    "variantItemAmount": 0,
    "input": [
      {
        "Key": {
          "ID": 14930,
          "Title": "Empty Backpack",
          "itemnamespace": null
        },
        "Value": 1.0
      },
      {
        "Key": {
          "name": "Cloth Roll",
          "itemnamespace": null,
          "ID": 12700
        },
        "Value": 1.0
      },
      {
        "Key": {
          "name": "Thread",
          "itemnamespace": null,
          "ID": 15750
        },
        "Value": 4.0
      },
      {
        "Key": {
          "name": "Scrap Metal",
          "itemnamespace": null,
          "ID": 35180
        },
        "Value": 2.0
      }
    ],
    "output": [
      {
        "Key": {
          "name": "Smuggler's Pack Insert",
          "itemnamespace": null,
          "ID": 400001
        },
        "Value": 1.0
      },
      {
        "Key": {
          "name": "Cloth Scraps",
          "itemnamespace": null,
          "ID": 12680
        },
        "Value": 1.0
      }
    ],
    "outputFail": [
      {
        "Key": {
          "name": "Cloth Scraps",
          "itemnamespace": null,
          "ID": 12680
        },
        "Value": 2.0
      },
      {
        "Key": {
          "name": "Scrap Metal",
          "itemnamespace": null,
          "ID": 35180
        },
        "Value": 1.0
      }
    ],
    "metaSettings": {
      "setIntegrity": 1.0,
      "setIntegrityFail": 0.5,
      "useAmmoAsInput": true,
      "setAmmoOfMax": 1.0,
      "setAmmoOfMaxFail": 0.0,
      "useLiquidContainers": false,
      "returnLiquidContainers": true,
      "putLiquidsIntoContainer": {
        "name": "",
        "itemnamespace": null,
        "ID": 0
      },
      "qualityFactor": 1.0,
      "qualityFactorFail": 0.5,
      "useFixedQuality": false,
      "fixedQuality": 1.0,
      "mailName": "",
      "mailReceiver": {
        "name": "",
        "ID": -1
      }
    },
    "FailChance": 0.85,
    "RelevantSkill": "Sewing",
    "SkillFactor": 1.0,
    "ProcessTime": 500,
    "Meta": null
  }
]
```

In order to add Recipes through your own Recipes.json you need to register it to Lavender.
```cs
string recipesPath = "Recipes.json";
Lavender.AddCustomRecipesFromJson(recipesPath, LCMPluginInfo.PLUGIN_NAME);
```

<br>

## Keys
I won't explain any keys here for now, because I didn't work that much with Recipes yet.<br>
Please refer to Obenseurs Recipes.json.

<table>
<tr>
    <td>Appearance</td>
    <td></td>
</tr>
<tr>
    <td>SpritePath</td>
    <td>The path to place where the Item UI Image is stored. InGame Addressable, AssetBundle or local file path.</td>
</tr>
</table>

For the ``SpritePath`` Asset Import Options, see [Appearance](Items.md#appearance).