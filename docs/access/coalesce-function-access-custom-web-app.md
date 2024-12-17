---
title: "Coalesce function (Access custom web app)" 
manager: lindalu
ms.date: 09/05/2017
ms.audience: Developer 
ms.localizationpriority: medium
ms.assetid: 92a7cc0a-1f9f-4969-8439-56a8d18e1347
description: "Returns the first expression that is not NULL from a list of arguments."
---

# Coalesce function (Access custom web app)

Returns the first expression that is not NULL from a list of arguments.
  
> [!NOTE]
> The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error:
> *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*
> For cloud storage for Office Online, Office for iOS, and Office for Android, look into our [Office Cloud Storage Partner Program](/microsoft-365/cloud-storage-partner-program/online/overview).
  
## Syntax

**Coalesce** (*Value*, [*Value*], …,[*Value*])
  
The **Coalesce** function contains the following arguments
  
|**Argument name**|**Description**|
|:-----|:-----|
| *Value*  <br/> |An expression. |

## Remarks

If all arguments are NULL, **Coalesce** returns NULL.
  
## Example

The following expression is used as the validation rule for a table. The expression ensures that entries are made in the First Name, Last Name, Email, Mobile Phone, Work Phone, Home Phone, and Company fields before a record is committed. If any of the listed fields are left blank, the **Coalesce** function returns Null, which violates the validation rule.
  
```vb
Coalesce([First Name],[Last Name],[Email],[Mobile Phone],[Work Phone],[Home Phone],[Company]) Is Not Null
```
