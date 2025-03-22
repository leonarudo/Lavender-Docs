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
    <td>createdFurniture</td>
    <td>A list of all modded Furnitures using Lavender.</td>
</tr>
<tr>
    <td>customItemDatabase</td>
    <td>A list of all modded items using Lavender.</td>
</tr>
<tr>
    <td>customRecipeDatabase</td>
    <td>A list of all modded Recipes using Lavender.</td>
</tr>
</table>

<br>

## Methods
<table>
<tr>
    <td>GetFurnitureByTitel(string)</td>
    <td></td>
</tr>
<tr>
    <td>AddFurnitureHandlers(Type)</td>
    <td>Gets all FurnitureHandler methods defined in the given Type: type and registers them for the Handler callback</td>
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
</table>