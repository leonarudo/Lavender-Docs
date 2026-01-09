# FurnitureCreator "Static" Class
<br>

## Definition
Namespace: Lavender.FurnitureLib <br>
Source: [FurnitureCreator.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/FurnitureLib/FurnitureCreator.cs)

<br>

## Remarks
The FurnitureCreator allows you to create furniture's either from an FurnitureConfig json or directly by setting the right parameters in ``FurnitureCreator.NewFurniture(...)``
*(if you know what your doing xD)*

If you just want to create some furniture's stick to ``Create(...)`` and ``CreateShopFurniture(...)``.
<br>

## Methods

<table>
<tr>
    <td>NewFurniture(string, string, Sprite, string, Furniture.Category, int, int, GameObject, GameObject, Furniture.BuildingArea[], List<Furniture.ReseourceItem>, FurniturePlaceType, Furniture.DisplayStyle, int, bool)</td>
    <td>Creates an Furniture object and setups the prefab entity structure. *This function is for those who know what there doing!*</td>
</tr>
<tr>
    <td>FurnitureConfigToFurniture(FurnitureConfig)</td>
    <td>Uses a FurnitureConfig to create a Furniture</td>
</tr>
<tr>
    <td>Create(string, bool = false)</td>
    <td>Creates a Furniture from the given path to the FurnitureConfig json and adds it to the FurnitureDatabase</td>
</tr>
<tr>
    <td>CreateShopFurniture(string, int)</td>
    <td>Creates an BuildingSystem.FurnitureInfo for the FurnitureShopRestockHandler</td>
</tr>
<tr>
    <td>CreateShopFurniture(int, string)</td>
    <td>Creates an BuildingSystem.FurnitureInfo for the FurnitureShopRestockHandler</td>
</tr>
</table>

<br>