---
title: Использование PowerShell для управления подключением Shifts к Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как использовать PowerShell для управления подключением Shifts к Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4edf815a3ce21a820fa292a06d41275c97d78a5
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647819"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Использование PowerShell для управления подключением Shifts к Blue Yonder Workforce Management

## <a name="overview"></a>Обзор

[Соединитель Смен Microsoft Teams для Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) позволяет интегрировать приложение Shifts в Microsoft Teams с Blue Yonder Workforce Management (Blue Yonder WFM). После настройки подключения ваши сотрудники переднего плана могут легко просматривать свои расписания и управлять ими в Blue Yonder WFM в shifts.

Для настройки подключения можно использовать мастер соединителя [shifts](shifts-connector-wizard.md) в Центр администрирования Microsoft 365 [или PowerShell](shifts-connector-blue-yonder-powershell-setup.md). После настройки подключения вы управляете этим подключением с помощью командлетов [PowerShell соединителя Shifts](#shifts-connector-cmdlets).

В этой статье описывается, как использовать PowerShell для выполнения следующих действий:

- [Проверка состояния установки подключения](#check-connection-setup-status)
- [Просмотр отчета об ошибке для подключения](#view-an-error-report-for-a-connection)
- [Устранение ошибок подключения](#resolve-connection-errors)
- [Изменение параметров подключения](#change-connection-settings)
- [Отмена сопоставления команды из одного подключения и сопоставление ее с другим подключением](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Отключение синхронизации для подключения](#disable-sync-for-a-connection)

> [!NOTE]
> В этой статье предполагается, что вы уже настроили подключение к Blue Yonder WFM с помощью мастера или PowerShell.

## <a name="before-you-begin"></a>Подготовка к работе

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Настройка среды

> [!NOTE]
> Перед выполнением команд или сценариев, описанных в этой статье, выполните следующие действия, чтобы настроить среду.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. Подключитесь к Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    При появлении запроса войдите в систему, используя учетные данные администратора. Теперь вы настроили выполнение скриптов, указанных в этой статье, и командлетов соединителя Shifts.

## <a name="check-connection-setup-status"></a>Проверка состояния установки подключения

<a name="setup_status"> </a>

Чтобы проверить состояние подключения, настроенного с помощью идентификатора операции, полученного по электронной почте:

1. [Настройка среды](#set-up-your-environment) (если вы еще этого не сделали).
1. Выполните следующую команду. Эта команда предоставляет общее состояние сопоставлений команд для подключения.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Дополнительные сведения см. в [статье Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation).

## <a name="view-an-error-report-for-a-connection"></a>Просмотр отчета об ошибке для подключения

<a name="error_report"> </a>

Можно запустить отчет, в котором отображаются сведения об ошибке подключения. В отчете перечислены сопоставления команд и пользователей, которые завершилось успешно и неудачно. Он также предоставляет сведения о любых проблемах, связанных с учетными записями, связанными с подключением.

1. [Настройка среды](#set-up-your-environment) (если вы еще этого не сделали).
1. Получение списка отчетов об ошибках для подключения.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Чтобы просмотреть конкретный отчет об ошибках, выполните следующую команду:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Дополнительные сведения см. в [статье Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport).

## <a name="resolve-connection-errors"></a>Устранение ошибок подключения

### <a name="user-mapping-errors"></a>Ошибки сопоставления пользователей

Ошибки сопоставления пользователей могут возникать, если один или несколько пользователей в экземпляре Blue Yonder WFM не является членом сопоставленной команды в Teams. Чтобы устранить эту проблему, убедитесь, что пользователи в сопоставленной команде соответствуют пользователям в экземпляре Blue Yonder WFM.

Чтобы просмотреть сведения о несопоставленных пользователях [, установите](#set-up-your-environment) среду (если вы еще не сделали этого), а затем выполните следующий сценарий.

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

Ошибки авторизации учетной записи могут возникать, если учетная запись WFM Blue Yonder или учетные данные системной учетной записи Microsoft 365 неверны или не имеют необходимых разрешений.

Чтобы изменить учетную запись службы Blue Yonder WFM или учетные данные системной учетной записи Microsoft 365 для подключения, можно запустить командлет [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) или использовать сценарий PowerShell в разделе "[](#change-connection-settings)Изменение параметров подключения" этой статьи.

## <a name="change-connection-settings"></a>Изменение параметров подключения
<a name="change_settings"> </a>

Используйте этот сценарий для изменения параметров подключения. К параметрам, которые можно изменить, относятся учетная запись и пароль службы Blue Yonder WFM, системная учетная запись Microsoft 365, сопоставления команд и параметры синхронизации.

Параметры синхронизации включают частоту синхронизации (в минутах) и данные расписания, синхронизированные между blue Yonder WFM shifts. Данные расписания определяются в следующих параметрах, которые можно просмотреть с помощью [командлета Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector).

- Параметр **enabledConnectorScenarios** определяет данные, синхронизированные с Blue Yonder WFM shifts. Параметры: `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOffRequest``TimeOff`.
- Параметр **enabledWfiScenarios** определяет данные, синхронизированные из shifts в blue Yonder WFM. Параметры: `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`. `UserShiftPreferences`

    > [!NOTE]
    > Если вы решили не синхронизировать открытые смены, открытые запросы на смену, запросы на переключение или запросы на отгулы между shifts и Blue Yonder WFM, необходимо сделать еще один шаг, чтобы скрыть возможность в shifts. После выполнения этого сценария убедитесь, что вы выполните действия, описанные в разделе "Отключение открытых смен", "Запросы на открытие смен" [,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) "Запросы на переключение" и "Запросы на отгулы" далее в этой статье.

> [!IMPORTANT]
> Для параметров, которые вы не хотите изменять, необходимо повторно ввести исходные параметры при появлении запроса скрипта.

[Настроите среду](#set-up-your-environment) (если вы еще этого не сделали), а затем выполните следующий сценарий.

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Отключение открытых смен, запросов на открытие смен, запросов на переключение и запросов на отгул

> [!IMPORTANT]
> Выполните следующие действия, только если вы решили отключить открытые смены, открытые запросы на смену, запросы на переключение или запросы на [](#change-connection-settings) отгулы с помощью скрипта в разделе "Изменение параметров подключения" ранее в этой статье или с помощью командлета [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance). Выполнение этого шага скрывает возможность в shifts. Без этого второго шага пользователи по-прежнему будут видеть возможность в shifts и будут получать сообщение об ошибке "неподдерживаемая операция", если они попытаются использовать ее.

Чтобы скрыть открытые смены, запросы на переключение и запросы на отгулы в shifts, используйте [](/graph/api/resources/schedule) тип ресурса расписания API Graph```false```, чтобы задать следующие параметры для каждой команды, сопоставленной с экземпляром Blue Yonder WFM:

- Открытые смены: ```openShiftsEnabled```
- Запросы на переключение:  ```swapShiftsRequestsEnabled```
- Запросы на отгулы: ```timeOffRequestsEnabled```

Чтобы скрыть запросы на открытые смены в сменах,  перейдите к разделу "Параметры в сменах" и отключите параметр **"Открыть смены**".

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Отмена сопоставления команды из одного подключения и сопоставление ее с другим подключением

> [!NOTE]
> Системная учетная запись Microsoft 365 должна быть одинаковой для обоих подключений. Если это не так, вы получите сообщение об ошибке "Этот профиль назначенного субъекта не имеет прав владения командой".

Если вы хотите отменить сопоставление команды из одного подключения и сопоставить ее с другим подключением:

1. [Настройка среды](#set-up-your-environment) (если вы еще этого не сделали).
1. Просмотрите список всех сопоставлений команд для подключения.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Удалите сопоставление команды из подключения.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Сопоставьте команду с другим подключением.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Дополнительные сведения см. в статьях [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) и [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap).

## <a name="disable-sync-for-a-connection"></a>Отключение синхронизации для подключения

Используйте этот сценарий, чтобы отключить синхронизацию для подключения. Помните, что этот сценарий не удаляет или не удаляет подключение. Он отключает синхронизацию, чтобы данные не синхронизируются между shifts и Blue Yonder WFM для указанного подключения.

[Настроите среду](#set-up-your-environment) (если вы еще этого не сделали), а затем выполните следующий сценарий.

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

## <a name="shifts-connector-cmdlets"></a>Командлеты соединителя Shifts

Чтобы получить справку по командлетам соединителя Shifts, найдите **CsTeamsShiftsConnection** в справочнике по [командлетам Teams PowerShell](/powershell/teams/intro). Ниже приведены ссылки на некоторые часто используемые командлеты.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>Статьи по теме

- [Соединители shifts](shifts-connectors.md)
- [Используйте мастер соединителя shifts для подключения shifts к blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Подключение shifts к blue Yonder с помощью PowerShell Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Управление приложением "Смены"](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Обзор PowerShell в Teams](../../teams-powershell-overview.md)
