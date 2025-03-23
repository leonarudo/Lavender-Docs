# FurnitureConfig Class
<br>

## Definition
Namespace: Lavender.FurnitureLib <br>
Source: [FurnitureConfig.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/FurnitureLib/FurnitureConfig.cs)

<br>

## Example

> [!WARNING]
> Lavender supports loading images and obj's at runtime, but the obj importer is currently pretty buggy. For the best and more stable results use AssetBundle imports instead!

> [!NOTE]
>  If you are using an FurnitureAssetData.json instead of an AssetBundle, set the values for ``imageName``, ``prefabName`` and ``previewPrefabName`` to ``""``!

### FurnitureConfig.json
```json
{
    "id": 0,
	"title": "Name",
	"details":"Description",

	"priceOC": 0,
	"priceRM": 0,

	"assetBundlePath": "assetBundle",
	"imageName":"asset_img",
	"prefabName":"asset_pre",
	"previewPrefabName":"asset_prepre",
	
	"category": "ALL",
	"restrictedAreas": [
	],
	
	"displayStyle": "Default",
    "placeType": "all",
	"displayRotationY": 0
}
```

<br>

## Properties

<table>
<tr>
    <td>id</td>
    <td>Furniture ID</td>
</tr>
<tr>
    <td>title</td>
    <td>The name of the furniture</td>
</tr>
<tr>
    <td>details</td>
    <td>A short description of the furniture</td>
</tr>
<tr>
    <td>priceOC</td>
    <td>OC price</td>
</tr>
<tr>
    <td>priceRM</td>
    <td>RM price</td>
</tr>
<tr>
    <td>assetBundlePath</td>
    <td>The location of the AssetBundle, which contains the image,prefab and preview prefab, relative to the .json path
    <br>Or the location of the FurnitureAssetData .json</td>
</tr>
<tr>
    <td>imageName</td>
    <td>The name of the sprite in the AssetBundle defined at assetBundlePath</td>
</tr>
<tr>
    <td>prefabName</td>
    <td>The name of the GameObject/Prefab in the AssetBundle defined at assetBundlePath</td>
</tr>
<tr>
    <td>previewPrefabName</td>
    <td>The name of the GameObject/Prefab in the AssetBundle defined at assetBundlePath</td>
</tr>
<tr>
    <td>category</td>
    <td>The category of the Furniture</td>
</tr>
<tr>
    <td>restrictedAreas</td>
    <td>Restricted areas to build the furniture -> Allowed to put everywhere if empty</td>
</tr>
<tr>
    <td>displayStyle</td>
    <td>Should it be positioned like a normal furniture or like a painting or ceiling object?</td>
</tr>
<tr>
    <td>placeType</td>
    <td>Restricted places to build (wall, floor, etc)</td>
</tr>
<tr>
    <td>displayRotationY</td>
    <td>Display rotation on the Y-Aches</td>
</tr>
</table>

<br>

---

# Furniture Config Enums
<br>

## FurnitureCategory
- All
- Chairs
- Tables
- Electronics
- Paintings
- Lights
- Rugs
- Items
- Machines
- Storage
- Clutter
- Beds
- Sofas
- Decoration
- Plants
- Shelves
- Manufacturing
- Growing
- Letters
- Bathroom
- Signs
- Magazines
- Posters
- Curtains
- Flags
- LicensePlates
- Kitchen
- Tank

<br>

## FurnitureDisplayStyle
- Default
- Painting
- Ceiling

<br>

## FurnitureBuildingArea
- None
- Stairs
- PlayerApartment
- Workshop
- Outside
- Greenhouse

<br>

## FurniturePlaceType
- all
- floor
- wall
- ceiling
- floorAndWall