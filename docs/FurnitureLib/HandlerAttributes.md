# HandlerAttributes (FurnitureLib)

Namespace: Lavender.FurnitureLib <br>
Source: [HandlerAttributes.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/FurnitureLib/HandlerAttributes.cs)

<br>

# FurniturePrefabHandlerAttribute

The Furniture Prefab Handler Attribute allows you to add custom scripts to your furniture prefab!

The Handler will always be called every time your furniture gets newly loaded for the FurnitureDatabase. (at the beginning of every scene containing your furniture)<br>
Scripts added to your prefabs directly in the AssetBundle are likely causing errors, so always add your scripts using this handler!

<br>

## Example

```cs
using Lavender.FurnitureLib;

// This Handler function gets called every time your furniture gets loaded!
[FurniturePrefabHandler("YourFurnitureTitle")]
public static GameObject YourFurniturePrefabHandler(GameObject gameobject)
{
    // ... -> do something with the furniture prefab, like prefab.AddComponent<T>()

    return gameobject;
}
```

In order to make the ``FurniturePrefabHandler`` work, you need to register it:
```cs
using Lavender;

// Put this in your mod Awake() function
Lavender.AddFurniturePrefabHandlers(typeof(the_class_containing_the_FurnitureHandler));
```

<br>

## Constructors

<table>
<tr>
    <td>FurniturePrefabHandler(string)</td>
    <td>Initializes a new instance of the FurniturePrefabHandlerAttribute class</td>
</tr>
</table>

<br>

## Properties

<table>
<tr>
    <td>FurnitureTitle</td>
    <td>The furniture title defines the furniture the handler is applied to! (Lavender only!)</td>
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
<tr>
    <td>OSMiningServices</td>
    <td>OS Mining Services</td>
</tr>
</table>

<br>
