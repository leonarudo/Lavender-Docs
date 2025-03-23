# HandlerAttributes (FurnitureLib)

Namespace: Lavender.FurnitureLib <br>
Source: [HandlerAttributes.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/FurnitureLib/HandlerAttributes.cs)

<br>

# FurnitureHandlerAttribute

The Furniture Handler Attribute allows you to add custom scripts to your furniture prefab!

The Handler will always be called every time your furniture gets loaded in ``SavableScriptableObject.LoadFromPath()``.
Scripts added to your prefabs directly in the furniture creation or AssetBundle are likely causing errors, so always add your scripts using this handler!

<br>

## Example

```cs
using Lavender.FurnitureLib;

// This Handler function gets called every time your furniture gets loaded!
[FurnitureHandler("YourFurnitureTitle")]
public static Furniture YourFurnitureHandler(Furniture furniture)
{
    // ... -> do something with the fresh loaded furniture like furniture.prefab.AddComponent<T>()

    return furniture;
}
```

In order to make the ``FurnitureHandler`` work, you need to register it:
```cs
using Lavender;

// Put this in your mod Awake() function
Lavender.AddFurnitureHandlers(typeof(the_class_containing_the_FurnitureHandler));
Lavender.AddFurnitureShopRestockHandlers(typeof(the_class_containing_the_FurnitureShopRestockHandler));
```

<br>

## Constructors

<table>
<tr>
    <td>FurnitureHandler(string)</td>
    <td>Initializes a new instance of the FurnitureHandlerAttribute class</td>
</tr>
</table>

<br>

## Properties

<table>
<tr>
    <td>FurnitureTitle</td>
    <td>The furniture title defines the lavender furniture the handler is applied to!</td>
</tr>
</table>

<br>

---

# FurnitureShopRestockHandlerAttribute
The Furniture Shop Restock Handler Attribute allows you to add your furniture every time a restock event occurs!

<br>

## Example

```cs
using Lavender.FurnitureLib;

[FurnitureShopRestockHandlerAttribute("AnyID")]
public static List<BuildingSystem.FurnitureInfo> FurShopRestockHandler(FurnitureShopName name)
{
    List<BuildingSystem.FurnitureInfo> restock = new List<BuildingSystem.FurnitureInfo>();

    string path = "FurnitureConfig.json";
    
    // Idea: Randomize the restock amount to make it more realistic
    int amount = 20;
   
    BuildingSystem.FurnitureInfo? info = FurnitureCreator.CreateShopFurniture(path, amount);
    if(info != null) restock.Add(info);

    return restock;
}
```

In order to make the ``FurnitureShopRestockHandler`` work, you need to register it:
```cs
using Lavender;

// Put this in your mod Awake() function
Lavender.AddFurnitureShopRestockHandlers(typeof(the_class_containing_the_FurnitureShopRestockHandler));
```

<br>

## Constructors

<table>
<tr>
    <td>FurnitureShopRestockHandler(string)</td>
    <td>Initializes a new instance of the FurnitureShopRestockHandlerAttribute class.</td>
</tr>
</table>

<br>

## Properties

<table>
<tr>
    <td>HandlerUID</td>
    <td>A Unique ID needed incase you want to remove an handler after registering it.</td>
</tr>
</table>

<br>

## FurnitureShopName Enum
The FurnitureShopName Enum which is one of the parameters of the FurnitureShopRestockHandler function allows you to identify which furniture shop the restock event came from.

<br>

### Values

> [!WARNING]
> Values from the Furniture Shops which came with the Mines Update are currently (v2.1) missing and displayed as NONE!

<table>
<tr>
    <td>None</td>
    <td>If none of the other values fit, the enum will be set to ``FurnitureShopName.None``</td>
</tr>
<tr>
    <td>OneStopShop</td>
    <td>One Stop Shop</td>
</tr>
<tr>
    <td>MoebelmannFurnitures</td>
    <td>Möbelmann Furnitures</td>
</tr>
<tr>
    <td>SamuelJonasson</td>
    <td>Jonasson's Shop</td>
</tr>
</table>

<br>
