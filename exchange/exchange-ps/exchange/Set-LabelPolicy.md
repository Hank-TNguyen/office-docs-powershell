---
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
online version: https://docs.microsoft.com/powershell/module/exchange/set-labelpolicy
applicable: Security & Compliance
title: Set-LabelPolicy
schema: 2.0.0
author: chrisda
ms.author: chrisda
ms.reviewer:
---

# Set-LabelPolicy

## SYNOPSIS
This cmdlet is functional only in Security & Compliance PowerShell. For more information, see [Security & Compliance PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).

Use the Set-Label cmdlet to modify sensitivity label policies in your organization.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://docs.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### RetryDistribution
```
Set-LabelPolicy [-Identity] <PolicyIdParameter> -RetryDistribution
 [-AddLabels <MultiValuedProperty>]
 [-AdvancedSettings <PswsHashtable>]
 [-Confirm]
 [-MigrationId <String>]
 [-NextLabelPolicy <PolicyIdParameter>]
 [-PreviousLabelPolicy <PolicyIdParameter>]
 [-RemoveLabels <MultiValuedProperty>]
 [<CommonParameters>]
```

### Identity
```
Set-LabelPolicy [-Identity] <PolicyIdParameter>
 [-AddExchangeLocation <MultiValuedProperty>]
 [-AddExchangeLocationException <MultiValuedProperty>]
 [-AddLabels <MultiValuedProperty>]
 [-AddModernGroupLocation <MultiValuedProperty>]
 [-AddModernGroupLocationException <MultiValuedProperty>]
 [-AddOneDriveLocation <MultiValuedProperty>]
 [-AddOneDriveLocationException <MultiValuedProperty>]
 [-AddPublicFolderLocation <MultiValuedProperty>]
 [-AddSharePointLocation <MultiValuedProperty>]
 [-AddSharePointLocationException <MultiValuedProperty>]
 [-AddSkypeLocation <MultiValuedProperty>]
 [-AddSkypeLocationException <MultiValuedProperty>]
 [-AdvancedSettings <PswsHashtable>]
 [-Comment <String>]
 [-Confirm]
 [-MigrationId <String>]
 [-NextLabelPolicy <PolicyIdParameter>]
 [-RemoveExchangeLocation <MultiValuedProperty>]
 [-RemoveExchangeLocationException <MultiValuedProperty>]
 [-RemoveLabels <MultiValuedProperty>]
 [-RemoveModernGroupLocation <MultiValuedProperty>]
 [-RemoveModernGroupLocationException <MultiValuedProperty>]
 [-RemoveOneDriveLocation <MultiValuedProperty>]
 [-RemoveOneDriveLocationException <MultiValuedProperty>]
 [-RemovePublicFolderLocation <MultiValuedProperty>]
 [-RemoveSharePointLocation <MultiValuedProperty>]
 [-RemoveSharePointLocationException <MultiValuedProperty>]
 [-RemoveSkypeLocation <MultiValuedProperty>]
 [-RemoveSkypeLocationException <MultiValuedProperty>]
 [<CommonParameters>]
```

### AdaptiveScopeLocation
```
Set-LabelPolicy [-Identity] <PolicyIdParameter>
 [-AddLabels <MultiValuedProperty>]
 [-AdvancedSettings <PswsHashtable>]
 [-Comment <String>]
 [-Confirm]
 [-Force]
 [-MigrationId <String>]
 [-NextLabelPolicy <PolicyIdParameter>]
 [-PreviousLabelPolicy <PolicyIdParameter>]
 [-RemoveLabels <MultiValuedProperty>]
 [-Setting <PswsHashtable>]
 [-Settings <PswsHashtable>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
To use this cmdlet in Security & Compliance PowerShell, you need to be assigned permissions. For more information, see [Permissions in the Microsoft Purview compliance portal](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center-permissions).

**Note**: Don't use a piped Foreach-Object command when adding or removing scope locations: `"Value1","Value2",..."ValueN" | Foreach-Object {Set-LabelPolicy -Identity "Global Policy" -RemoveExchangeLocation $_ }`.

## EXAMPLES

### Example 1
```powershell
Set-LabelPolicy -Identity "Global Policy" -AdvancedSettings @{EnableCustomPermissions="False"}
```

This example configures the specified advanced setting for the sensitivity label policy name Global Policy.

## PARAMETERS

### -Identity
The Identity parameter specifies the policy that you want to view. You can use any value that uniquely identifies the policy. For example:

- Name
- Distinguished name (DN)
- GUID

```yaml
Type: PolicyIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -RetryDistribution
The RetryDistribution switch specifies whether to redistribute the policy to all Exchange Online locations. You don't need to specify a value with this switch.

Locations whose initial distributions succeeded aren't included in the retry. Policy distribution errors are reported when you use this switch.

**Note**: Because the process of retrying distribution is a significant operation, run it only if necessary and for one policy at a time. It is not intended to be run every time you update a policy. If you run a script to update multiple policies, wait until the policy distribution is successful before running the command again for the next policy.

```yaml
Type: SwitchParameter
Parameter Sets: RetryDistribution
Aliases:
Applicable: Security & Compliance

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddExchangeLocation
The AddExchangeLocation parameter specifies the mailboxes to add to the list of included mailboxes when you aren't using the value All for the ExchangeLocation parameter. A valid value is a mailbox.

To specify the mailbox, you can use any value that uniquely identifies it. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddExchangeLocationException
The AddExchangeLocationException parameter specifies the mailboxes to add to the list of excluded mailboxes when you use the value All for the ExchangeLocation parameter. A valid value is a mailbox.

To specify the mailbox, you can use any value that uniquely identifies it. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddLabels
The AddLabels parameter specifies the sensitivity labels that you want to add to the policy. You can use any value that uniquely identifies the label. For example:

- Name
- Distinguished name (DN)
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddModernGroupLocation
The AddModernGroupLocation parameter specifies the Microsoft 365 Groups to add to the list of included Microsoft 365 Groups. To identify the Microsoft 365 Group, you must use the primary SMTP address.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddModernGroupLocationException
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddOneDriveLocation
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddOneDriveLocationException
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPublicFolderLocation
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddSharePointLocation
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddSharePointLocationException
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddSkypeLocation
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddSkypeLocationException
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdvancedSettings
The AdvancedSettings parameter enables client-specific features and capabilities for the sensitivity label policy.

Specify this parameter with the identity (name or GUID) of the policy, with key/value pairs in a [hash table](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hash_tables). To remove an advanced setting, use the same AdvancedSettings parameter syntax, but specify a null string value.

Most of the settings that you configure with this parameter are supported only by the Azure Information Protection unified labeling client and not by Office apps that support built-in labeling. For instructions, see [Custom configurations for the Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations).

Supported settings for built-in labeling:

- **DisableMandatoryInOutlook**: Outlook apps that support this setting exempt Outlook messages from mandatory labeling. Example: ` Set-LabelPolicy -Identity Global -AdvancedSettings @{DisableMandatoryInOutlook="True"}`. For more information about this configuration choice, see [Outlook-specific options for default label and mandatory labeling](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-office-apps#outlook-specific-options-for-default-label-and-mandatory-labeling).

- **EnableAudit**: Prevent Office apps from sending sensitivity label data to Microsoft 365 auditing solutions. Supported apps: Word, Excel, and PowerPoint on Windows (version 2201+), macOS (version 16.57+), iOS (version 2.57+), and Android (version 16.0.14827+), and also Outlook on Windows (version 2201+). Example: `Set-LabelPolicy -Identity Global -AdvancedSettings @{EnableAudit="False"}`.

- **HideBarByDefault**: For Office apps that support the sensitivity bar, don't display the sensitivity label name on the window bar title so that there's more space to display long file names. Just the label icon and color (if configured) will be displayed. Users can't revert this setting in the app. Example: `Set-LabelPolicy -Identity Global -AdvancedSettings @{HideBarByDefault="True"}`

- **OutlookDefaultLabel**: Outlook apps that support this setting apply a default label, or no label. Example: `Set-LabelPolicy -Identity Global -AdvancedSettings @{OutlookDefaultLabel="None"}`. For more information about this configuration choice, see [Outlook-specific options for default label and mandatory labeling](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-office-apps#outlook-specific-options-for-default-label-and-mandatory-labeling).

Additionally, for Power BI:

- **powerbimandatory**: Mandatory labeling for Power BI. Example: `Set-LabelPolicy -Identity Global -AdvancedSettings @{powerbimandatory="true"}`. For more information about this configuration choice, see [Mandatory label policy for Power BI](https://docs.microsoft.com/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy).

- **powerbidefaultlabelid**: Default label for Power BI content. Example: `Set-LabelPolicy -Identity Global -AdvancedSettings @{powerbidefaultlabelid="General"}`. For more information about this configuration choice, see [Default label policy for Power BI](https://docs.microsoft.com/power-bi/admin/service-security-sensitivity-label-default-label-policy).

```yaml
Type: PswsHashtable
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Comment
The Comment parameter specifies an optional comment. If you specify a value that contains spaces, enclose the value in quotation marks ("), for example: "This is an admin note".

```yaml
Type: String
Parameter Sets: Identity, AdaptiveScopeLocation
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.
- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate.

```yaml
Type: SwitchParameter
Parameter Sets: AdaptiveScopeLocation
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationId
This parameter is reserved for internal Microsoft use.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextLabelPolicy
The NextLabelPolicy parameter updates the policy order so the policy that's specified by this parameter is after the current policy that you're modifying. You can use any value that uniquely identifies the policy. For example:

- Name
- Distinguished name (DN)
- GUID

```yaml
Type: PolicyIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreviousLabelPolicy
The PreviousLabelPolicy parameter updates the policy order so the policy that's specified by this parameter is before the current policy that you're modifying. You can use any value that uniquely identifies the policy. For example:

- Name
- Distinguished name (DN)
- GUID

```yaml
Type: PolicyIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveExchangeLocation
The RemoveExchangeLocation parameter specifies the mailboxes to remove from the list of included mailboxes when you aren't using the value All for the ExchangeLocation parameter. Valid values are:

- A mailbox
- A distribution group or mail-enabled security group (all mailboxes that are currently members of the group).

To specify a mailbox or distribution group, you can use any value that uniquely identifies it. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveExchangeLocationException
The RemoveExchangeLocationException parameter specifies the mailboxes to remove from the list of excluded mailboxes when you're using the value All for the ExchangeLocation parameter. Valid values are:

- A mailbox
- A distribution group or mail-enabled security group (all mailboxes that are currently members of the group).

To specify a mailbox or distribution group, you can use any value that uniquely identifies it. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveLabels
The RemoveLabels parameter specifies the sensitivity labels that you want to remove from the policy. You can use any value that uniquely identifies the label. For example:

- Name
- Distinguished name (DN)
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveModernGroupLocation
The RemoveModernGroupLocation parameter specifies the Microsoft 365 Groups to remove from the list of included groups. To identify the Microsoft 365 Group, you must use the primary SMTP address.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveModernGroupLocationException
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveOneDriveLocation
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveOneDriveLocationException
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePublicFolderLocation
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSharePointLocation
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSharePointLocationException
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSkypeLocation
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSkypeLocationException
This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Setting
This parameter is reserved for internal Microsoft use.

```yaml
Type: PswsHashtable
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Settings
This parameter is reserved for internal Microsoft use.

```yaml
Type: PswsHashtable
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
The WhatIf switch doesn't work in Security & Compliance PowerShell.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Security & Compliance

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
