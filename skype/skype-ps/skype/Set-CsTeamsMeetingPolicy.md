---
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml 
online version: https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy
applicable: Skype for Business Online
title: Set-CsTeamsMeetingPolicy
schema: 2.0.0
manager: bulenteg
author: tomkau
ms.author: tomkau
ms.reviewer:
---

# Set-CsTeamsMeetingPolicy

## SYNOPSIS
The `CsTeamsMeetingPolicy` cmdlets enable administrators to control the type of meetings that users can create or the features that they can access while in a meeting. It also helps determine how meetings deal with anonymous or external users.

## SYNTAX

### Identity (Default)

```powershell
Set-CsTeamsMeetingPolicy [-Tenant <Guid>] [-Description <String>]
 [-AllowChannelMeetingScheduling <Boolean>] [-AllowCartCaptionsScheduling <String>] [-LiveInterpretationEnabledType <String>] [-AllowMeetNow <Boolean>] [-AllowPrivateMeetNow <Boolean>]
 [-MeetingChatEnabledType <String>] [-LiveCaptionsEnabledType <String>] [-AllowIPVideo <Boolean>] [-IPAudioMode <String>] [-IPVideoMode <String>]
 [-AllowAnonymousUsersToDialOut <Boolean>]
 [-AllowAnonymousUsersToJoinMeeting <Boolean>] [-AllowAnonymousUsersToStartMeeting <Boolean>]
 [-BlockedAnonymousJoinClientTypes <List>]
 [-AllowPrivateMeetingScheduling <Boolean>] [-AutoAdmittedUsers <String>] [-AllowCloudRecording <Boolean>]
 [-AllowOutlookAddIn <Boolean>] [-AllowPowerPointSharing <Boolean>]
 [-AllowParticipantGiveRequestControl <Boolean>] [-AllowExternalParticipantGiveRequestControl <Boolean>]
 [-AllowSharedNotes <Boolean>] [-AllowWhiteboard <Boolean>] [-AllowTranscription <Boolean>]
 [-MediaBitRateKb <UInt32>] [-RecordingStorageMode <String>] [-ScreenSharingMode <String>] [-AllowPSTNUsersToBypassLobby <Boolean>] [-AllowRecordingStorageOutsideRegion <Boolean>]
 [-PreferredMeetingProviderForIslandsMode <String>] [[-Identity] <XdsIdentity>]
 [-VideoFiltersMode <String>] [-AllowEngagementReport <String>] [-AllowNDIStreaming <Boolean>]
 [-DesignatedPresenterRoleMode <String>] [-AllowIPAudio <Boolean>] [-AllowOrganizersToOverrideLobbySettings <Boolean>]
 [-AllowUserToJoinExternalMeeting <String>] [-EnrollUserOverride <String>] [-StreamingAttendeeMode <String>] 
[-AllowBreakoutRooms <Boolean>] [-TeamsCameraFarEndPTZMode <String>] [-AllowMeetingReactions <Boolean>] 
[-AllowMeetingRegistration <Boolean>] [-AllowScreenContentDigitization <Boolean>] [-AllowTrackingInReport <Boolean>] [-RoomAttributeUserOverride <String>] 
[-SpeakerAttributionMode <String>] [-WhoCanRegister <String>] [-ChannelRecordingDownload <String>] [-NewMeetingRecordingExpirationDays <Int32>] 
[-MeetingInviteLanguages <String>] [-AllowNetworkConfigurationSettingsLookup <Boolean>] [-LiveStreamingMode <String>]
[-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `CsTeamsMeetingPolicy` cmdlets enable administrators to control the type of meetings that users can create or the features that they can access while in a meeting. It also helps determine how meetings deal with anonymous or external users.

The Set-CsTeamsMeetingPolicy cmdlet allows administrators to update existing meeting policies that can be assigned to particular users to control Teams features related to meetings.

## EXAMPLES

### EXAMPLE 1
```powershell
Set-CsTeamsMeetingPolicy -Identity SalesMeetingPolicy -AllowTranscription $True
```

The command shown in Example 1 uses the Set-CsTeamsMeetingPolicy cmdlet to update an existing meeting policy with the Identity SalesMeetingPolicy.
This policy will use all the existing values except one: AllowTranscription; in this example, meetings for users with this policy can include real time or post meeting captions and transcriptions.


### EXAMPLE 2

```powershell
Set-CsTeamsMeetingPolicy -Identity HrMeetingPolicy -AutoAdmittedUsers "Everyone" -AllowMeetNow $False
```

In Example 2, the Set-CsTeamsMeetingPolicy cmdlet is used to update a meeting policy with the Identity HrMeetingPolicy.
In this example two different property values are configured: AutoAdmittedUsers is set to Everyone and AllowMeetNow is set to False.
All other policy properties will use the existing values.

### EXAMPLE 3

```powershell
Set-CsTeamsMeetingPolicy -Identity NonEVNetworkRoamingPolicy -AllowNetworkConfigurationSettingsLookup $True
```

In Example 3, the Set-CsTeamsMeetingPolicy cmdlet is used to update an existing meeting policy with the Identity NonEVNetworkRoamingPolicy.
This policy will use all the existing values except one: AllowNetworkConfigurationSettingsLookup; in this example, we will fetch network roaming policy for the non-EV user with NonEVNetworkRoamingPolicy based on his current network location. 

## PARAMETERS

### -AllowAnonymousUsersToJoinMeeting

> [!NOTE]
> The experience for users is dependent on both the value of -DisableAnonymousJoin (the old tenant-wide setting) and -AllowAnonymousUsersToJoinMeeting (the new per-organizer policy). Please check <https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams> for details.

Determines whether anonymous users can join the meetings that impacted users organize. Set this to TRUE to allow anonymous users to join a meeting. Set this to FALSE to prohibit them from joining a meeting.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowAnonymousUsersToStartMeeting
Determines whether anonymous users can initiate a meeting. Set this to TRUE to allow anonymous users to initiate a meeting. Set this to FALSE to prohibit them from initiating a meeting.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlockedAnonymousJoinClientTypes
A user can join a Teams meeting anonymously using a [Teams client](https://support.microsoft.com/office/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508) or using a [custom application built using Azure Communication Services](/azure/communication-services/concepts/join-teams-meeting). When anonymous meeting join is enabled, both types of clients may be used by default. This optional parameter can be used to block one of the client types that can be used.

The allowed values are ACS (to block the use of Azure Communication Services clients) or Teams (to block the use of Teams clients). Both can also be specified, separated by a comma, but this is equivalent to disabling anonymous join completely.

```yaml
Type: List
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Empty List
Accept pipeline input: False
Accept wildcard characters: False
``` 

### -AllowChannelMeetingScheduling
Determines whether a user can schedule channel meetings. Set this to TRUE to allow a user to schedule channel meetings. Set this to FALSE to prohibit the user from scheduling channel meetings. 

> [!NOTE]
> This only restricts from scheduling and not from joining a meeting scheduled by another user.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowCloudRecording
Determines whether cloud recording is allowed in a user's meetings. Set this to TRUE to allow the user to be able to record meetings. Set this to FALSE to prohibit the user from recording meetings.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowRecordingStorageOutsideRegion
Allow storing recording outside of region. All meeting recordings will be permanently stored in another region, and can't be migrated. For more info, see https://aka.ms/in-region.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowExternalParticipantGiveRequestControl
Determines whether external participants can request or give control of screen sharing during meetings scheduled by this user. Set this to TRUE to allow the user to be able to give or request control. Set this to FALSE to prohibit an external user from giving or requesting control in a meeting.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowIPVideo
Determines whether video is enabled in  a user's meetings or calls. Set this to TRUE to allow the user to share their video. Set this to FALSE to prohibit the user from sharing their video.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAudioMode
Determines whether audio can be turned on in meetings and group calls. Set this to ENABLEDOUTGOINGINCOMING to allow outgoing and incoming audio in the meeting. Set this to DISABLED to prohibit outgoing and incoming audio in the meeting.

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

### -IPVideoMode
Determines whether video can be turned on in meetings and group calls. Set this to ENABLEDOUTGOINGINCOMING to allow outgoing and incoming video in the meeting. Set this to DISABLED to prohibit outgoing and incoming video in the meeting.

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

### -AllowCartCaptionsScheduling
Determines whether a user can add a URL for captions from a Communicatons Access Real-Time Translation (CART) captioner for providing real time captions in meetings.
Possible values are:
- **EnabledUserOverride**, CART captions is available by default but a user can disable.
- **DisabledUserOverride**, if you would like users to be able to use CART captions in meetings but by default it is disabled. 
- **Disabled**, if you'd like to not allow CART captions in meeting.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: DisabledUserOverride
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiveInterpretationEnabledType
Allows meeting organizers to configure a meeting for language interpretation, selecting attendees of the meeting to become interpreters that other attendees can select and listen to the real-time translation they provide.
Possible values are:
- **DisabledUserOverride**, if you would like users to be able to use interpretation in meetings but by default it is disabled. 
- **Disabled**, prevents the option to be enabled in Meeting Options.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: DisabledUserOverride
Accept pipeline input: False
Accept wildcard characters: False
```


### -AllowMeetNow
Determines whether a user can start ad-hoc meetings. Set this to TRUE to allow a user to start ad-hoc meetings. Set this to FALSE to prohibit the user from starting ad-hoc meetings. 

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowOutlookAddIn
Determines whether a user can schedule Teams Meetings in Outlook desktop client. Set this to TRUE to allow the user to be able to schedule Teams meetings in Outlook client. Set this to FALSE to prohibit a user from scheduling Teams meeting in Outlook client.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowParticipantGiveRequestControl
Determines whether participants can request or give control of screen sharing during meetings scheduled by this user. Set this to TRUE to allow the user to be able to give or request control. Set this to FALSE to prohibit the user from giving, requesting control in a meeting.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowPowerPointSharing
Determines whether Powerpoint sharing is allowed in a user's meetings. Set this to TRUE to allow. Set this to FALSE to prohibit.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowPrivateMeetingScheduling
Determines whether a user can schedule private meetings. Set this to TRUE to allow a user to schedule private meetings. Set this to FALSE to prohibit the user from scheduling private meetings. 

> [!NOTE]
> This only restricts from scheduling and not from joining a meeting scheduled by another user.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowSharedNotes
Determines whether users are allowed to take shared Meeting notes.  Set this to TRUE to allow. Set this to FALSE to prohibit.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowTranscription
Determines whether post-meeting captions and transcriptions are allowed in a user's meetings.  Set this to TRUE to allow. Set this to FALSE to prohibit.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowWhiteboard
Determines whether whiteboard is allowed in a user's meetings. Set this to TRUE to allow. Set this to FALSE to prohibit.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -AutoAdmittedUsers
Determines what types of participants will automatically be added to meetings organized by this user.
Possible values are:
- **EveryoneInCompany**, if you would like meetings to place every external user in the lobby but allow all users in the company to join the meeting immediately.
- **EveryoneInSameAndFederatedCompany**, if you would like meetings to allow federated users to join like your company's users, but place all other external users in a lobby. 
- **Everyone**, if you'd like to admit anonymous users by default. 
- **OrganizerOnly**, if you would like that only meeting organizers can bypass the lobby.
- **EveryoneInCompanyExcludingGuests**, if you would like meetings to place every external and guest users in the lobby but allow all other users in the company to join the meeting immediately.
- **InvitedUsers**, if you would like that only meeting organizers and invited users can bypass the lobby.

This setting also applies to participants joining via a PSTN device (i.e. a traditional phone).

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

### -Description
Enables administrators to provide explanatory text about the meeting policy.
For example, the Description might indicate the users the policy should be assigned to.

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

### -Force
Specifies whether to suppress warning and confirmation messages. It can be useful in scripting to suppress interactive prompts. If the switch isn't provided in the command, you're prompted for administrative input if required.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specify the name of the policy being created.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaBitRateKb
Determines the media bit rate for audio/video/app sharing transmissions in meetings.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScreenSharingMode
Determines the mode in which a user can share a screen in calls or meetings. Set this to SingleApplication to allow the user to share an  application at a given point in time. Set this to EntireScreen to allow the user to share anything on their screens. Set this to Disabled to prohibit the user from sharing their screens.

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

### -Tenant
Globally unique identifier (GUID) of the tenant account whose external user communication policy are being created. For example:

-Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"

You can return your tenant ID by running this command:

Get-CsTenant | Select-Object DisplayName, TenantID

If you are using a remote session of Windows PowerShell and are connected only to Skype for Business Online you do not have to include the Tenant parameter. Instead, the tenant ID will automatically be filled in for you based on your connection information. The Tenant parameter is primarily for use in a hybrid deployment.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### -AllowPSTNUsersToBypassLobby
Determines whether a PSTN user joining the meeting is allowed or not to bypass the lobby. If you set this parameter to **True**, PSTN users are allowed to bypass the lobby as long as an authenticated user is joined to the meeting.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MeetingChatEnabledType
Specifies if users will be able to chat in meetings. Possible values are: Disabled, Enabled, and EnabledExceptAnonymous.

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

### -AllowPrivateMeetNow
This setting controls whether a user can start an ad hoc private meeting.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowAnonymousUsersToDialOut

Determines whether anonymous users are allowed to dial out to a PSTN number. Set this to TRUE to allow anonymous users to dial out. Set this to FALSE to prohibit anonymous users from dialing out.

> [!NOTE]
> This parameter is temporarily disabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredMeetingProviderForIslandsMode
Determines the Outlook meeting add-in available to users on Islands mode. By default, this is set to TeamsAndSfb, and the users sees both the Skype for Business and Teams add-ins. Set this to Teams to remove the Skype for Business add-in and only show the Teams add-in.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: TeamsAndSfb
Accept pipeline input: False
Accept wildcard characters: False
```
### -RecordingStorageMode
This parameter can take two possible values:
- Stream
- OneDriveForBusiness

Note: The change of storing Teams meeting recordings from Classic Stream to OneDrive and SharePoint (ODSP) has been completed as of August 30th, 2021. All recordings are now stored in ODSP. This change overrides the RecordingStorageMode parameter, and modifying the setting in PowerShell no longer has any impact.

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

### -LiveCaptionsEnabledType
Determines whether real-time captions are available for the user in Teams meetings. Set this to DisabledUserOverride to allow user to turn on live captions. Set this to Disabled to prohibit.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: DisabledUserOverride
Accept pipeline input: False
Accept wildcard characters: False
```

### -VideoFiltersMode
Determines the background effects that a user can configure in the Teams client. Possible values are:

- NoFilters: No filters are available.
- BlurOnly: Background blur is the only option available (requires a processor with AVX2 support, see [Hardware requirements for Microsoft Teams](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app) for more information).
- BlurAndDefaultBackgrounds: Background blur and a list of pre-selected images are available.
- AllFilters: All filters are available, including custom images.

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

### -AllowEngagementReport
Determines whether meeting organizers are allowed to download the attendee engagement report. Possible values are:

- Enabled: allow the meeting organizer to download the report.
- Disabled: disable attendee report generation and prohibit meeting organizer from downloading it.

If set to enabled, only meeting organizers will get a link to download the report in Teams. Regular attendees will have no access to it.

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

### -AllowNDIStreaming
This parameter enables the use of NDI technology to capture and deliver broadcast-quality audio and video over your network.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DesignatedPresenterRoleMode
Determines if users can change the default value of the _Who can present?_ setting in Meeting options in the Teams client. This policy setting affects all meetings, including Meet Now meetings.

Possible values are:
- EveryoneUserOverride: All meeting participants can be presenters. This is the default value. This parameter corresponds to the _Everyone_ setting in Teams.
- EveryoneInCompanyUserOverride: Authenticated users in the organization, including guest users, can be presenters. This parameter corresponds to the _People in my organization_ setting in Teams.
- EveryoneInSameAndFederatedCompanyUserOverride: Authenticated users in the organization, including guest users and users from federated organizations, can be presenters. This parameter corresponds to the _People in my organization and trusted organizations_ setting in Teams.
- OrganizerOnlyUserOverride: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees. This parameter corresponds to the _Only me_ setting in Teams.

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

### -VideoFiltersMode
Determines what background effects a user can use in scheduled calls and meetings. 
Possible values: NoFilters, BlurOnly, BlurAndDefaultBackgrounds, AllFilters.

```yaml
Type: Enum
Position: Named
Default value: AllFilters
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowIPAudio
Determines whether audio is enabled in  a user's meetings or calls. Set this to TRUE to allow the user to share their audio. Set this to FALSE to prohibit the user from sharing their audio.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowOrganizersToOverrideLobbySettings
This parameter has been deprecated and currently has no effect.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowUserToJoinExternalMeeting
Currently, this parameter has no effect.

Possible values are:
- Enabled 
- FederatedOnly
- Disabled

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnrollUserOverride
Possible values are: 
- Disabled
- Enabled

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -StreamingAttendeeMode

Controls if Teams uses overflow capability once a meeting reaches its capacity (1,000 users with full functionality). 

Possible values are: 
- Disabled
- Enabled

Set this to Enabled to allow up to 20,000 extra view-only attendees to join.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Enabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowBreakoutRooms
Set to true to enable Breakout Rooms, set to false to disable the Breakout Rooms functionality.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamsCameraFarEndPTZMode
Possible values are: 
- Disabled
- AutoAcceptInTenant 
- AutoAcceptAll

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowMeetingReactions
Set to false to disable Meeting Reactions.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowMeetingRegistration
Controls if a user can create a webinar meeting. The default value is True.

Possible values:
- True
- False

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowScreenContentDigitization
This parameter is reserved for internal Microsoft use.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowTrackingInReport
This parameter is reserved for internal Microsoft use.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoomAttributeUserOverride
Possible values:

- Off
- Distinguish
- Attribute

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

### -SpeakerAttributionMode
Possible values:

- EnabledUserOverride
- Disabled

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

### -WhoCanRegister
Controls the attendees who can attend a webinar meeting. The default is Everyone, meaning that everyone can register. If you want to restrict registration  to internal accounts set the value  to 'EveryoneInCompany'. 

Possible values:

- Everyone
- EveryoneInCompany

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Everyone
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewMeetingRecordingExpirationDays
Specifies the number of days before meeting recordings will expire and move to the recycle bin. Value can be from 1 to 99,999 days. Value can also be -1 to set meeting recordings to never expire.

NOTE: You may opt to set Meeting Recordings to never expire by entering the value -1.

NOTE: This parameter is available to be set, but will not be effective until this feature gets general availability. Please refer to the [roadmap (Feature ID: 84580)](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=84580) for more information on its delivery date.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MeetingInviteLanguages
Controls how the join information in meeting invitations is displayed by enforcing a common language or enabling up to two languages to be displayed.
Note: All Teams supported languages can be specified using language codes. For more information about its delivery date, see the [roadmap (Feature ID: 81521)](https://www.microsoft.com/en-us/microsoft-365/roadmap?filters=&searchterms=81521).

The preliminary list of available languages is shown below:
ar-SA,az-Latn-AZ,bg-BG,ca-ES,cs-CZ,cy-GB,da-DK,de-DE,el-GR,en-GB,en-US,es-ES,es-MX,et-EE,eu-ES,fi-FI,fil-PH,fr-CA,fr-FR,gl-ES,he-IL,hi-IN,hr-HR,hu-HU,id-ID,is-IS,it-IT,ja-JP,ka-GE,kk-KZ,ko-KR,lt-LT,lv-LV,mk-MK,ms-MY,nb-NO,nl-NL,nn-NO,pl-PL,pt-BR,pt-PT,ro-RO,ru-RU,sk-SK,sl-SL,sq-AL,sr-Latn-RS,sv-SE,th-TH,tr-TR,uk-UA,vi-VN,zh-CN,zh-TW.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Microsoft Teams

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChannelRecordingDownload
Controls how channel meeting recordings are saved, permissioned, and who can download them. 

Possible values:

- Allow - Saves channel meeting recordings to a "Recordings" folder in the channel. The permissions on the recording files will be based on the Channel SharePoint permissions. This is the same as any other file uploaded for the channel.
- Block - Saves channel meeting recordings to a "Recordings\View only" folder in the channel. Channel owners will have full rights to the recordings in this folder, but channel members will have read access without the ability to download. 

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Allow
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowNetworkConfigurationSettingsLookup
Determines whether network configuration setting lookup can be made for users who are not Enterprise Voice enabled. It is used to enable Network Roaming policy.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiveStreamingMode
Determines whether you provide support for your users to stream their Teams meetings to large audiences through Real-Time Messaging Protocol (RTMP).

Possible values are: 
- Disabled
- Enabled

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

## INPUTS

### System.Management.Automation.PSObject


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
