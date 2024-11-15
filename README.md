# BadAppleTerrariaMap
In this repository you can find the source files for every tile used in building this slideshow. 
```
The first six bytes are the width and height values ​​from the bytes array, interpreted as 16-bit unsigned integers (ushort).
WidthStart: composed of the first and second bytes (bytes[0] and bytes[1]).
Width: composed of the third and fourth bytes (bytes[2] and bytes[3]).
Height: composed of the fifth and sixth bytes (bytes[4] and bytes[5]).
Each value is formed by concatenating two bytes, where the first byte is the low-order part and the second is the high-order part.
```
In this way, each tile from the file is read byte by byte. i >= 6
```csharp
Convert.ToBoolean(bytes[i]), // isWall
    Convert.ToBoolean(bytes[i + 1]), // isTorch
    (ushort)((bytes[i + 2] & 0xff) + ((bytes[i + 3] & 0xff) << 8)), // ID
    bytes[i + 4] // Color
```

