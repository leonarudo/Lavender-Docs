# FastObjImporter Class
<br>

## Definition
Namespace: Lavender.RuntimeImporter <br>
Source: [FastObjImporter.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/RuntimeImporter/FastObjImporter.cs)

Import ``.obj`` files at runtime.
<br>

## Example
```cs
Mesh mesh = FastObjImporter.Instance.ImportFile("McMushroom.obj");
```
<br>

## Static Properties

<table>
<tr>
    <td>Instance</td>
    <td>The current FastObjImporter instance.</td>
</tr>
</table>

<br>

## Methods

<table>
<tr>
    <td>ImportFile(string)</td>
    <td>Imports the given OBJ and returns an UnityEngine.Mesh Object.</td>
</tr>
</table>

<br>