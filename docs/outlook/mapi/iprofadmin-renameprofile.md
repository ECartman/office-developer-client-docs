---
title: "IProfAdminRenameProfile"
 
 
manager: lindalu
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.service: office-online-server
ms.localizationpriority: medium
api_name:
- IProfAdmin.RenameProfile
api_type:
- COM
ms.assetid: 2a575cac-dbfd-4f42-9c10-4b7e355a065e
---

# IProfAdmin::RenameProfile

  
  
**Applies to**: Outlook 2013 | Outlook 2016 
  
Assigns a new name to a profile.
  
```cpp
HRESULT RenameProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## Parameters

 _lpszOldProfileName_
  
> [in] A pointer to the current name of the profile to rename.
    
 _lpszOldPassword_
  
> [in] Always NULL.
    
 _lpszNewProfileName_
  
> [in] A pointer to the new name of the profile to rename.
    
 _ulUIParam_
  
> [in] A handle to the parent window of any dialog boxes or windows that this method displays. 
    
 _ulFlags_
  
> [in] A bitmask of flags that controls how the profile is renamed.  The following flag can be set:

MAPI_APP_PROFILE

> Allows renaming an "app" profile. This flag must be set if the profile is an "app" profile.

## Return value

S_OK 
  
> The profile was successfully renamed.

MAPI_E_LOGON_FAILED 

> The profile password is incorrect.

MAPI_E_NO_ACCESS

> The profile is an "app" profile, and the MAPI_APP_PROFILE flag was not set.

MAPI_E_USER_CANCEL 
  
> The user canceled the operation, typically by clicking the **Cancel** button in a dialog box. 
    
## Remarks

The **IProfAdmin::RenameProfile** method assigns a new name to a profile, if it has one. If the profile to rename is in use by a client when **RenameProfile** is called, **RenameProfile** marks the profile and returns S_OK instead of attempting the rename operation while the profile is in use. When the profile is no longer being used, **RenameProfile** assigns it the new name. 
  
The old and new names of the profile can be up to 64 characters in length and can include the following characters:
  
- All alphanumeric characters, including accent characters and the underscore character.
    
- Embedded spaces, but not leading or trailing spaces.
    
The  _lpszPassword_ should always be NULL or a pointer to a zero-length string. 

## Notes to callers

> [!CAUTION]
> The MAPI_APP_PROFILE flag is only supported in versions 2405 and newer.  Using this flag in earlier versions may fail.

## See also



[IProfAdmin : IUnknown](iprofadminiunknown.md)

