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
>  ``imageName``, ``prefabName`` and ``previewPrefabName`` only accept LavenderAssets!

### FurnitureConfig.json
```json
{
    "id": 0,
    "title": "Name",
    "details":"Description",

    "priceOC": 0,
    "priceRM": 0,

    "trash": false,

    "imageName":"#lv_modname-001",
    "prefabName":"#lv_modname-101",
    "previewPrefabName":"#lv_modname-101",
	
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
    <td>trash</td>
    <td>?</td>
</tr>
<tr>
    <td>imageName</td>
    <td>LavenderAsset-ID 'ModName-id' e.g. Lavender-100</td>
</tr>
<tr>
    <td>prefabName</td>
    <td>LavenderAsset-ID 'ModName-id' e.g. Lavender-100</td>
</tr>
<tr>
    <td>previewPrefabName</td>
    <td>LavenderAsset-ID 'ModName-id' e.g. Lavender-100</td>
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
- None

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
- Store
- Communal
- Public

<br>

## FurniturePlaceType
- all
- floor
- wall
- ceiling
- floorAndWall