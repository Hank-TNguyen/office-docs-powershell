---
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
online version: https://docs.microsoft.com/powershell/module/skype/sync-csonlineapplicationinstance
applicable: Microsoft Teams, Skype for Business Online
title: Sync-CsOnlineApplicationInstance
schema: 2.0.0
author: xixian73
ms.author: xixian
manager:naveenv
ms.reviewer:
---

# Sync-CsOnlineApplicationInstance

## SYNOPSIS
Use the Sync-CsOnlineApplicationInstance cmdlet to sync the application instance from Azure Active Directory into Agent Provisioning Service. This is needed because the mapping between application instance and application needs to be stored in Agent Provisioning Service. If an application ID was provided at the creation of the application instance, you need not run this cmdlet. 

## SYNTAX

```
Sync-CsOnlineApplicationInstance [-CallbackUri <String>] [-ObjectId <System.Guid>] [-ApplicationId <System.Guid>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Use the Sync-CsOnlineApplicationInstance cmdlet to sync application instances from Azure Active Directory into Agent Provisioning Service.

## EXAMPLES

### -------------------------- Example 1 --------------------------
```powershell
Sync-CsOnlineApplicationInstance -ObjectId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -ApplicationId yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy
```

This example sync application instance with object ID "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" and application ID "yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy" into Agent Provisioning Service.

### -------------------------- Example 2 --------------------------
```powershell
Sync-CsOnlineApplicationInstance -ObjectId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -ApplicationId 00000000-0000-0000-0000-000000000000
```
This command is helpful when there's already a mapping in Agent Provisioning Service and you want to set a different app ID value. In this case, when running the cmdlet in example 1, you will see `Sync-CsOnlineApplicationInstance : An item with the same key has already been added.`.

The command removes the mapping for application instance with object ID "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx". Run the example cmdlet again to create the mapping in Agent Provisioning Service.


## PARAMETERS

### -CallbackUri
This parameter is reserved for internal Microsoft use.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
The application instance ID.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationId
The application ID.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
This switch specifies whether to suppress warning and confirmation messages. It can be useful in scripting to suppress interactive prompts. If it isn't provided in the command, you're prompted for administrative input if required.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: `-Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information`, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).
