---
title: "IProfAdminDeleteProfile"
description: "Describes the syntax, parameters, return value, and remarks for IProfAdmin DeleteProfile, which deletes a profile."
manager: lindalu
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.service: office-online-server
ms.localizationpriority: medium
api_name:
- IProfAdmin.DeleteProfile
api_type:
- COM
ms.assetid: 730af2da-4c4a-42a7-9d52-56d914107d64
---

# IProfAdmin::DeleteProfile

  
  
**Applies to**: Outlook 2013 | Outlook 2016 
  
Deletes a profile.
  
```cpp
HRESULT DeleteProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## Parameters

 _lpszProfileName_
  
> [in] A pointer to the name of the profile to be deleted.
    
 _ulFlags_
  
> [in] A bitmask of flags that controls how a profile is deleted.  The following flag can be set:

MAPI_APP_PROFILE

> Allows deleting an "app" profile.  This flag must be set if the profile to be deleted is an "app" profile.
> 
> This flag may not be recognized or supported in all MAPI implementations.

## Return value

S_OK 
  
> The profile was successfully deleted.

MAPI_E_NO_ACCESS

> The profile is an "app" profile, and the MAPI_APP_PROFILE flag was not set.

MAPI_E_NOT_FOUND 
  
> The specified profile does not exist.
    
## Remarks

The **IProfAdmin::DeleteProfile** method deletes a profile. If the profile to delete is in use when **DeleteProfile** is called, **DeleteProfile** returns S_OK but does not delete the profile immediately. Instead, **DeleteProfile** marks the profile for deletion and deletes it after it is no longer being used, when all of its active sessions have ended. 
  
The entry point function for each message service in the profile is called with the MSG_SERVICE_DELETE value set in the _ulContext_ parameter. First, the function deletes the service, and then it deletes the service's profile section. The message service entry point function is not called again after the service has been deleted. 
  
No password is required to delete a profile.



## MFCMAPI reference

For MFCMAPI sample code, see the following table.
  
|**File**|**Function**|**Comment**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |HrRemoveProfile  <br/> |MFCMAPI uses the **IProfAdmin::DeleteProfile** method to delete the selected profile. |
   
## See also



[IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)


[MFCMAPI as a Code Sample](mfcmapi-as-a-code-sample.md)

