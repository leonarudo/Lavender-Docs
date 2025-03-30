# StorageCreator Static Class
<br>

## Definition
Namespace: Lavender.StorageLib <br>
Source: [Type.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/StorageLib/StorageCreator.cs)

<br>

## Example

```cs
[FurniturePrefabHandler("Shipping Container")]
public static GameObject ShippingContainerHandler(GameObject gameObject)
{
    StorageCreator.AddSimpleStorage(gameObject, "Shipping Container", "Enter", "ShippingContainer");

    return gameObject;
}
```

<br>

## Methods

<table>
<tr>
    <td>AddSimpleStorage(GameObject, string, string, string)</td>
    <td>Setups a Storage component without any spawn information.</td>
</tr>
</table>

<br>