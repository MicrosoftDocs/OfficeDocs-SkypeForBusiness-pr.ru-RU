---
title: Использование PowerShell для управления подключением к сменам для управления ресурсами "Синий Yonder"
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как использовать PowerShell для управления подключением "Смены" к управлению трудовыми ресурсами "Синий Yonder".
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593692"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Использование PowerShell для управления подключением к сменам для управления ресурсами "Синий Yonder"

## <a name="overview"></a>Обзор

[Соединителя Microsoft Teams Shifts для blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) позволяет интегрировать приложение "Смены" в Microsoft Teams с управлением ресурсами "Синий Иондер" (blue Yonder WFM). После того как вы настроите подключение, сотрудники, работающие с телефоном, смогут без проблем просматривать свои расписания и управлять ими в службе WFM "Синий Yonder" в представлении "Смены".

Для этого можно использовать мастер соединитегорий [Shifts](shifts-connector-wizard.md) в Центр администрирования Microsoft 365 [или PowerShell](shifts-connector-blue-yonder-powershell-setup.md). После того как подключение настроено, вы управляете им с помощью соединителя [Shifts PowerShell.](#shifts-connector-cmdlets)

В этой статье описано, как с помощью PowerShell сделать следующее:

- [Проверка состояния настройки подключения](#check-connection-setup-status)
- [Просмотр отчета об ошибке подключения](#view-an-error-report-for-a-connection)
- [Устранение ошибок подключения](#resolve-connection-errors)
- [Изменение параметров подключения](#change-connection-settings)
- [Отсвечение команды от одного подключения и ее подключение к другому](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Отключение синхронизации для подключения](#disable-sync-for-a-connection)

> [!NOTE]
> В этой статье предполагается, что вы уже настроили подключение к WFM "Синий Yonder" с помощью мастера или PowerShell.

## <a name="before-you-begin"></a>Подготовка к работе

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Настройка среды

> [!NOTE]
> Перед запуском команд или сценариев, указанных в этой статье, выполните указанные здесь действия.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>Проверка состояния настройки подключения
<a name="setup_status"> </a>

Чтобы проверить состояние установленного подключения с помощью ИД операции, полученного по электронной почте:

1. [Настройка среды](#set-up-your-environment) (если вы еще не сделали этого).
1. Выполнить следующую команду: Эта команда позволяет получить общее состояние сопоставлений группы для подключения.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Дополнительные информации см [. в теме Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps).

## <a name="view-an-error-report-for-a-connection"></a>Просмотр отчета об ошибке подключения
<a name="error_report"> </a>

Вы можете запустить отчет с подробными сведениями об ошибках подключения. В отчете перечислены сопоставления группы и пользователей, которые успешно или не удалось. Здесь также приводится информация обо всех проблемах, связанных с учетными записями, связанными с подключением.

1. [Настройка среды](#set-up-your-environment) (если вы еще не сделали этого).
1. Получите список отчетов об ошибках для подключения.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Чтобы просмотреть определенный отчет об ошибке, запустите следующую команду:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Дополнительные информации см [. в get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps).

## <a name="resolve-connection-errors"></a>Устранение ошибок подключения

### <a name="user-mapping-errors"></a>Ошибки сопоставления пользователей

Ошибки сопоставления пользователей могут возникать, если один или несколько пользователей на сайте WFM "Синий Yonder" не являются членами сопоставленной группы в Teams. Чтобы устранить эту проблему, убедитесь, что пользователи в группе соотовешены с пользователями на сайте WFM "Синий Уодер".

Чтобы просмотреть сведения о неоконченных пользователях [,](#set-up-your-environment) настроите среду (если еще не сделали этого) и запустите следующий сценарий:

```powershell
#View sync errors script 
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x 
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>Ошибки авторизации учетной записи

Ошибки авторизации учетной записи могут возникать, если учетная запись службы WFM Microsoft 365 blue Yonder или учетные данные системной учетной записи неправильны или не имеют необходимых разрешений.

Чтобы изменить учетную запись службы WFM blue Yonder или учетные данные системной учетной записи Microsoft 365 для подключения, вы можете выполнить для подключения cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) или использовать сценарий [](#change-connection-settings) PowerShell в разделе Изменение параметров подключения этой статьи.

## <a name="change-connection-settings"></a>Изменение параметров подключения
<a name="change_settings"> </a>

Используйте этот сценарий для изменения параметров подключения. Параметры, которые можно изменить, включите учетную запись службы WFM Blue Yonder и пароль, Microsoft 365 системную учетную запись, сопоставления команд и параметры синхронизации.

Параметры синхронизации включают частоту синхронизации (в минутах) и данные расписания, синхронизируются между WFM и Shifts "Синий Yonder". Данные расписания определены в следующих параметрах, которые можно просмотреть с помощью [get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps).

- Параметр **enabledConnectorScenarios** определяет данные, синхронизированные с blue Yonder WFM с Shifts. Возможные варианты: `Shift`, `SwapRequest``UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff`. `TimeOffRequest`
- Параметр **enabledWfiScenarios** определяет данные, синхронизированные со сменами с blue Yonder WFM. Возможные варианты: `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`. `UserShiftPreferences`

    > [!NOTE]
    > Если вы решили не синхронизировать открытые смены, открытые запросы на смену, запросы на обмен или запросы на отступы между сменами и WFM "Синий Желтодер", вам нужно сделать еще один шаг, чтобы скрыть возможности в shifts. После запуска этого сценария убедитесь, что вы выполните действия, которые см. в разделе Отключение открытых смен, открытые запросы на смены [,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) запросы на обмен и запросы на отрезки далее в этой статье.

> [!IMPORTANT]
> Если вы не хотите изменять параметры, вам потребуется повторно ввести исходные параметры при запросе сценария.

[Настроите среду](#set-up-your-environment) (если вы еще этого не сделали), а затем запустите следующий сценарий:

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview) 
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping 
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping 
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Отключение открытых смен, открытых запросов на смены, запросов на обмен и отработан

> [!IMPORTANT]
> Выполните эти действия только в том случае, если вы отключили открытые смены, запросы на смену, запросы на обмен или отсоединения с помощью сценария в разделе Изменение параметров подключения ранее в этой статье или с помощью [](#change-connection-settings) [cmdlet Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps). Выполнение этого шага скрывает возможности в сменах. Без этого второго шага пользователи по-прежнему будут видеть функцию в shifts и получат сообщение об ошибке "Неподсвеченная операция" при попытке использовать ее.

Чтобы скрыть открытые смены, запросы на обмен и запросы на отключки в shifts [](/graph/api/resources/schedule?view=graph-rest-1.0) ```false```, используйте тип ресурса API Graph, чтобы настроить следующие параметры для каждой группы, назначенной сайту WFM "Синий Уодер":

- Открытие смен: ```openShiftsEnabled```
- Запросы на обмен:  ```swapShiftsRequestsEnabled```
- Запросы на отключки: ```timeOffRequestsEnabled```

Чтобы скрыть запросы на открытие смен в сменах, перейдите  Параметры в "Смены" и отключите параметр **"Открыть смены**".

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Отсвечение команды от одного подключения и ее подключение к другому

> [!NOTE]
> Учетная запись Microsoft 365 должна быть одной и той же для обоих подключений. Если это не так, вы получите сообщение об ошибке "Этот профиль назначенного субъекта не имеет прав владения командой".

Если вы хотите отсметь команду от одного подключения к другому:

1. [Настройка среды](#set-up-your-environment) (если вы еще не сделали этого).
1. Просмотр списка всех сопоставлений группы для подключения.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Удалите сопоставление группы из подключения.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Сое сообщение группы к другому подключению.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Дополнительные возможности см. в других проектах [: Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps) и [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps).

## <a name="disable-sync-for-a-connection"></a>Отключение синхронизации для подключения

Используйте этот сценарий, чтобы отключить синхронизацию для подключения. Помните, что этот сценарий не удаляет подключение. Синхронизация отключается, чтобы между сменами и WFM-данными не синхронизировалась ни одна из задачных подключений.

[Настроите среду](#set-up-your-environment) (если вы еще этого не сделали), а затем запустите следующий сценарий:

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Cmdlets connector shifts

Для справки по соединительным системам Shifts в справочнике по Teams [PowerShell](/powershell/teams/intro?view=teams-ps) наищите **ссылку на CsTeamsShiftsConnection**. Ниже lydlets (Ссылки на часто используемые cmdlets).

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>Статьи по теме

- [Соединитетели смен](shifts-connectors.md)
- [Использование мастера соединителя "Смены" для подключения shifts к управлению ресурсами "Синий Yonder"](shifts-connector-wizard.md)
- [Использование PowerShell для подключения shifts к управлению ресурсами "синий Yonder"](shifts-connector-blue-yonder-powershell-setup.md)
- [Управление приложением "Смены"](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Обзор PowerShell в Teams](../../teams-powershell-overview.md)