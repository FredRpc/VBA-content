
# Graphic.CropBottom Property (Excel)

Returns or sets the number of points that are cropped off the bottom of the specified picture or OLE object. Read/write  **Single** .


## Syntax

 _expression_ . **CropBottom**

 _expression_ An expression that returns a **Graphic** object.


## Remarks

Cropping is calculated relative to the original size of the picture. For example, if you insert a picture that is originally 100 points high, rescale it so that it's 200 points high, and then set the  **CropBottom** property to 50, 100 points (not 50) will be cropped off the bottom of your picture.


## Example

This example crops 20 points off the bottom of shape three on  `myDocument`. For the example to work, shape three must be either a picture or an OLE object.


```vb
Set myDocument = Worksheets(1) 
myDocument.Shapes(3).PictureFormat.CropBottom = 20
```

Using this example, you can specify the percentage you want to crop off the bottom of the selected shape, regardless of whether the shape has been scaled. For the example to work, the selected shape must be either a picture or an OLE object.




```vb
percentToCrop = InputBox( _ 
 "What percentage do you want to crop off" &; _ 
 " the bottom of this picture?") 
Set shapeToCrop = ActiveWindow.Selection.ShapeRange(1) 
With shapeToCrop.Duplicate 
 .ScaleHeight 1, True 
 origHeight = .Height 
 .Delete 
End With 
cropPoints = origHeight * percentToCrop / 100 
shapeToCrop.PictureFormat.CropBottom = cropPoints
```


## See also


#### Concepts


[Graphic Object](0ccdfb0d-effb-9fa4-8de9-b90688693375.md)
#### Other resources


[Graphic Object Members](c523b66f-3c54-4e97-0e05-80032819d234.md)
