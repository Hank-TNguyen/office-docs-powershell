---
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
online version: https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems
applicable: Exchange Online, Security & Compliance, Exchange Online Protection
title: Get-TenantAllowBlockListItems
schema: 2.0.0
author: chrisda
ms.author: chrisda
ms.reviewer:
---

# Get-TenantAllowBlockListItems

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Get-TenantAllowBlockListItems cmdlet to view entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://docs.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### Expiration (Default)
```
Get-TenantAllowBlockListItems -ListType <ListType> [-ExpirationDate <DateTime>]
 [-Allow]
 [-Block]
 [-Entry <String>]
 [-ListSubType <ListSubType[]>]
 [-OutputJson]
 [<CommonParameters>]
```

### NoExpiration
```
Get-TenantAllowBlockListItems -ListType <ListType> [-NoExpiration]
 [-Allow]
 [-Block]
 [-Entry <String>]
 [-ListSubType <ListSubType[]>]
 [-OutputJson]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

This example returns all blocked URLs.

### Example 2
```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

This example returns information for the specified file hash value.

### Example 3
```powershell
Get-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery
```

This example returns information for all allowed third-party phishing simulation URLs. For more information, see [Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-advanced-delivery).

## PARAMETERS

### -ListType
The ListType parameter specifies the list to view. Valid values are:

- FileHash
- Sender
- Url

```yaml
Type: ListType
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Entry
The Entry parameter filters the results based on the ListType parameter value. Valid values are:

- FileHash: The exact SHA256 file hash value.
- Sender: The exact domain or email address value.
- Url: The exact URL value.

This value is shown in the Value property of the entry in the output of the Get-TenantAllowBlockListItems cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoExpiration
The NoExpiration switch filters the results by entries that are set to never expire. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: NoExpiration
Aliases:
Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Allow
This parameter is available only in Exchange Online PowerShell.

The Allow switch filters the results for allow entries. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Block
The Block switch filters the results for block entries. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpirationDate
The ExpirationDate parameter filters the results by expiration date in Coordinated Universal Time (UTC).

To specify a date/time value for this parameter, use either of the following options:

- Specify the date/time value in UTC: For example, `"2021-05-06 14:30:00z"`.
- Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2020 9:30 AM").ToUniversalTime()`. For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-Date).

```yaml
Type: DateTime
Parameter Sets: Expiration
Aliases:
Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListSubType
This parameter is available only in Exchange Online PowerShell.

The ListSubType parameter filters the results by subtype. Valid values are:

- AdvancedDelivery
- Tenant: This is the default value.

```yaml
Type: ListSubType[]
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputJson
The OutputJson switch specifies whether to return all entries in a single JSON value. You don't need to specify a value with this switch.

You use this switch to prevent the command from halting on the first entry that contains a syntax error.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
