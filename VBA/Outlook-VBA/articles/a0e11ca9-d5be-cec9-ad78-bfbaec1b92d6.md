
# Inspector.SetCurrentFormPage Method (Outlook)

Displays the specified form page or form region in the inspector.


## Syntax

 _expression_ . **SetCurrentFormPage**( **_PageName_** )

 _expression_ A variable that represents an **Inspector** object.


### Parameters



|**Name**|**Required/Optional**|**Data Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _PageName_|Required| **String**|The display name of the form page, or the internal name of a form region.|

## Remarks

You can use  **SetCurrentFormPage** to display a form region by specifying the **[InternalName](2478d44e-887c-c245-6cfa-70a6a1e2c828.md)** property of the form region, if the form region is an a separate, replace, or replace-all form region.


## Example

This Visual Basic for Applications (VBA) example uses the  **SetCurrentFormPage** method to show the **All Fields** page of the currently open item. If an error occurs, Outlook will display a message box to the user.


```vb
Sub ShowAllFieldsPage() 
 
 On Error GoTo ErrorHandler 
 
 Dim myInspector As Inspector 
 
 Dim myItem As Object 
 
 
 
 Set myInspector = Application.ActiveInspector 
 
 myInspector.SetCurrentFormPage ("All Fields") 
 
 Set myItem = myInspector.CurrentItem 
 
 myItem.Display 
 
Exit Sub 
 
 
 
ErrorHandler: 
 
 MsgBox Err.Description, vbInformation 
 
End Sub
```


## See also


#### Concepts


[Inspector Object](d7384756-669c-0549-1032-c3b864187994.md)
#### Other resources


[Inspector Object Members](acd3e13f-4727-7966-d2a5-a95e4528425c.md)
