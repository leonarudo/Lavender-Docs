# LavenderAsset Class
<br>

## Definition
Namespace: Lavender.RuntimeImporter <br>
Source: [LavenderAsset.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/RuntimeImporter/LavenderAsset.cs)

> [!NOTE]
> LavenderAssets are also referenced as ``LVA``

<br>

## Example
``LavenderAsset.json``
```json
[
    {
        "ID": 1,
        "AssetType": "AssetBundle",
        "Data": {
            "path": "AssetBundleFile",
            "name": "AssetName"
        }
    },
    {
        "ID": 2,
        "AssetType": "Image",
        "Data": {
            "path": "Image.png",
            "name": ""
        }
    },
    {
        "ID": 3,
        "AssetType": "OBJ",
        "Data": {
            "path": "3DModel.obj",
            "name": "Example 3DModel",
            "objTexturePaths": [
                "3DModel_Texture.png"
            ]
        }
    }
]
```

In order to use these LVAs in your ``FurnitureConfig.json`` or ``Item/Recipe.json`` you need to register them to Lavender:
```cs
string path = "YourLavenderAsset.json";
Lavender.AddLavenderAssets("YourModName", path);

// Now you can reference these LVAs as e.g. #lv_YourModName-1
```

When using ``GetAssetData<T>()`` for AssetBundle LVAs, T must be the Type of the Asset you want to load:
```cs
LavenderAsset asset = Lavender.GetLavenderAsset("#lv_YourModName-1"); // 'YourModName-1' would also work here!

// GetAssetData<T>() returns a value of type 'object?'.
// So if you want to use the return value as GameObject
// you need to specify its type using '(GameObject)'.
GameObject loadedPrefab = (GameObject)asset.GetAssetData<GameObject>();
```

<br>

## Properties

<table>
<tr>
    <td>ID</td>
    <td>Unique ID</td>
</tr>
<tr>
    <td>AssetType</td>
    <td>Enum</td>
</tr>
<tr>
    <td>Data</td>
    <td></td>
</tr>
</table>

<br>

## Methods

<table>
<tr>
    <td>GetAssetData()</td>
    <td>Loads the Asset specified in the Data Class</td>
</tr>
</table>

<br>

---

# AssetType Enum
<br>

### 1. AssetBundle
<table>
<tr>
    <td>path</td>
    <td>The file path to the AssetBundle file relative to this json file.</td>
</tr>
<tr>
    <td>name</td>
    <td>The name of your asset in the AssetBundle.</td>
</tr>
</table>

<br>

### 2. Image
<table>
<tr>
    <td>path</td>
    <td>The file path to the PNG or JPG file relative to this json file.</td>
</tr>
</table>

<br>

### 3. OBJ
<table>
<tr>
    <td>path</td>
    <td>The file path to the OBJ file relative to this json file.</td>
</tr>
<tr>
    <td>name</td>
    <td>The created mesh will be named 'name' + '_Mesh'.</td>
</tr>
<tr>
    <td>objTexturePaths</td>
    <td>The file path(s) to the OBJs Texture PNG or JPG file(s) relative to this json file. Each Texture will be interpreted by GetAssetData() as an extra Material.</td>
</tr>
</table>