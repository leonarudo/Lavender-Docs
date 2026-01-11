# Lavender Class
<br>

## Definition
Namespace: Lavender <br>
Source: [Lavender.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/Lavender.cs)

Lavenders "Main" Class, you will use it pretty often.

<br>

## Properties

<table>
<tr>
    <td>isInitialized</td>
    <td></td>
</tr>
<tr>
    <td>harmony</td>
    <td></td>
</tr>
<tr>
    <td>lastLoadedScene</td>
    <td>The build index of the last scene during the "SceneManager.sceneLoaded" callback</td>
</tr>
<tr>
    <td>LoadingDone</td>
    <td>You want to execute your mod logic only when LoadingDone = true to make sure that all game logic is already initialized!</td>
</tr>
</table>

<br>

## Static Properties
<table>
<tr>
    <td>instance</td>
    <td>Provides the current Lavender instance</td>
</tr>
<tr>
    <td>FurnitureDatabase</td>
    <td>A list of all modded furniture's using Lavender.</td>
</tr>
<tr>
    <td>customItemDatabase</td>
    <td>A list of all modded items using Lavender.</td>
</tr>
<tr>
    <td>customRecipeDatabase</td>
    <td>A list of all modded Recipes using Lavender.</td>
</tr>
<tr>
    <td>customStorageCategoryDatabase</td>
    <td>A list of all modded StorageCategories using Lavender.</td>
</tr>
<tr>
    <td>customStorageSpawnCategoryDatabase</td>
    <td>A list of all modded StorageSpawnCategories using Lavender.</td>
</tr>
</table>

<br>

## Static Methods
<table>
<tr>
    <td>AddLavenderAssets(string, string)</td>
    <td></td>
</tr>
<tr>
    <td>GetLavenderAsset(string)</td>
    <td>Tries to find the LavenderAsset by its ID 'modname-id' or '#lv_modname-id'</td>
</tr>
<tr>
    <td>GetLavenderAssetsFromMod(string)</td>
    <td>Returns all LavenderAssets added using the given mod name.</td>
</tr>
<tr>
    <td>FetchFurnitureByTitle(string)</td>
    <td></td>
</tr>
<tr>
    <td>FetchFurnitureByID(string)</td>
    <td></td>
</tr>
<tr>
    <td>AddFurniturePrefabHandlers(Type)</td>
    <td>Gets all FurniturePrefabHandler methods defined in the given Type: type and registers them for the Handler callback</td>
</tr>
<tr>
    <td>AddFurnitureShopRestockHandlers(Type)</td>
    <td>Gets all FurnitureShopRestockHandler methods defined in the given Type: type and registers them for the Handler callback</td>
</tr>
<tr>
    <td>AddCustomItem(Item, string)</td>
    <td></td>
</tr>
<tr>
    <td>AddCustomItemsFromJson(string, string)</td>
    <td></td>
</tr>
<tr>
    <td>AddCustomRecipe(Recipe, string)</td>
    <td></td>
</tr>
<tr>
    <td>AddCustomRecipesFromJson(string, string)</td>
    <td></td>
</tr>
<tr>
    <td>AddModifierToCraftingBase(string, int, bool = false)</td>
    <td>Adds a Modifier using its ID to a crafting station</td>
</tr>
<tr>
    <td>AddModifierInfo(ModifierInfo)</td>
    <td></td>
</tr>
<tr>
    <td>AddOnStorageEnterCallback(string, OnStorageEnter)</td>
    <td></td>
</tr>
<tr>
    <td>AddOnStorageExitCallback(string, OnStorageExit)</td>
    <td></td>
</tr>
<tr>
    <td>AddCustomStorageCategory(StorageCategory)</td>
    <td></td>
</tr>
<tr>
    <td>AddCustomStorageCategoryFromJson(string, string)</td>
    <td></td>
</tr>
<tr>
    <td>AddCustomStorageSpawnCategory(StorageSpawnCategory)</td>
    <td></td>
</tr>
<tr>
    <td>AddCustomStorageSpawnCategoryFromJson(string, string)</td>
    <td></td>
</tr>
</table>