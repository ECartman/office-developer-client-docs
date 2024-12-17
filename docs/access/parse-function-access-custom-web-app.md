---
title: "Parse Function (Access custom web app)"
 
 
manager: lindalu
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
  
ms.localizationpriority: medium
ms.assetid: 09dee0ae-89b2-449c-a3c8-d6b270710b64
description: "Parses a text value and returns its value in a given type using the culture of the application."
---

# Parse Function (Access custom web app)

Parses a text value and returns its value in a given type using the culture of the application.
  
> [!NOTE]
> The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error:
> *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*
> For cloud storage for Office Online, Office for iOS, and Office for Android, look into our [Office Cloud Storage Partner Program](/microsoft-365/cloud-storage-partner-program/).
  
## Syntax

**Parse** (*TextExpression*, *DataType*)
  
The **Parse** function contains the following arguments.
  
|**Argument name**|**Description**|
|:-----|:-----|
| *TextExpression*  <br/> |A text expression representing the formatted value to parse into the specified data type. |
| *DataType*  <br/> |Literal value representing the data type requested for the result. |
   
## Remarks

Use **Parse** only for converting from string to date/time and number types. For general type conversions, use the **Convert** function. Keep in mind that there is a certain performance overhead in parsing the string value.
  