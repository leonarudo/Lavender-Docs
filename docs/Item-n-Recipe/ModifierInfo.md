# ModifierInfo Class
<br>

## Definition
Namespace: Lavender.RecipeLib <br>
Source: [ModifierInfo.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/RecipeLib/ModifierInfo.cs)

<br>

## Example

```cs
// Loads an Icon.png by using Lavenders RuntimeImporter
Sprite Icon = Lavender.RuntimeImporter.ImageLoader.LoadSprite("ModifierIcon.png");

// Creates a new Modifier with the unique ID 101
ModifierInfo info = new RecipeLib.ModifierInfo(101, "Modifier Example", "An Example Modifier", Icon);
Lavender.AddModifierInfo(info);

// Applies the new Modifier to the 'Brick Furnace' crafting station
Lavender.AddModifierToCraftingBase("Brick Furnace", 101);
```

<br>

## Constructors

<table>
<tr>
    <td>ModifierInfo(int, string, string, Sprite)</td>
    <td>Creates a new crafting modifier</td>
</tr>
</table>

<br>

## Properties

<table>
<tr>
    <td>ID</td>
    <td>Unique Modifier ID</td>
</tr>
<tr>
    <td>TooltipTitle</td>
    <td>Modifier Title</td>
</tr>
<tr>
    <td>TooltipDetails</td>
    <td>Modifier Description</td>
</tr>
<tr>
    <td>Image</td>
    <td>Modifier Icon</td>
</tr>
</table>

<br>
