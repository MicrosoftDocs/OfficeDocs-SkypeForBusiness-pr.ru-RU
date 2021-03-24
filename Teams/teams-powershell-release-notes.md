---
title: Заметки о выпуске Microsoft Teams PowerShell
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте о последних изменениях в Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4b6aecf4aa9abd0815cd6efd5d6394501d6c14e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094109"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Заметки о выпуске Microsoft Teams PowerShell

На этой странице содержится последний журнал изменений Teams PowerShell для общих выпусков доступности и общедоступной предварительной версии.

## <a name="release-notes"></a>Заметки о выпуске

> [!NOTE]
> **-preview** в столбце версии ниже представляет обновления общедоступный предварительный просмотр Teams PowerShell.

| Дата | Версия | Обновления |
|------- | -------------------- | ------------------------------ |

| Март 2021 г| [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Использование MSAL для проверки подлинности & авторизации</li> <li>Connect-MicrosoftTeams является точкой входа для всех cmdlets.</li><li>Новый-csOnlineSession больше не является avaiable. Она была заменена на Connect-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection больше не требуется. Эта функция была реализована в модуле Teams PowerShell.</li> <li>Refactored Policy Package cmdlets and adds group package assignment</li><li>Значительные улучшения производительности для Get-Team управления</li> <li>Улучшенные параметры ведения журнала и отладки для существующих cmdlets </li> <li>Добавлены команды для управления шаблонами</li> <li>Деprecation of New-CsOnlineSession</li>| | Февраль 2021 г| [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Добавлены команды для управления шаблонами</li><li>Улучшения mezzo и пакетного пакета для Get-Team-управления</li> <li>Улучшенные параметры ведения журнала и отладки для существующих cmdlets </li> <li>Рефакторed Policy Package cmdlets</li>| | Декабрь 2020 г| [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Обновления для командлета new-team с увеличенным количеством и длительностью спящий режим</li>| | Декабрь 2020 г| [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Обновления интеграции Skype для бизнеса Online</li><li>Исправление запроса на дублирование в Connect-Microsoft Teams</li>| | Ноябрь 2020 г| [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Добавляет настраиваемые пакеты политики</li><li>Исправления для команд отправки в иерархию targeting</li>| | Ноябрь 2020 г| [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Использование MSAL для проверки подлинности & авторизации</li><li>Refactored Policy Package cmdlets and adds group package assignment</li><li>Рефакторed targeting hierarchy upload commands to use an asynchroned model</li> <li>Если пользователь не использует параметр -credential, при начальной проверке подлинности пользователю будет дважды предложено сделать это. Пользователи могут передавать учетные данные, используя параметр -credential, чтобы избежать дублирования запроса. Это будет исправлено в следующем выпуске.</li> | | Сентябрь 2020 г| [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Интеграция Соединитела Skype для бизнеса Online</li> | | Сентябрь 2020 г| [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Интеграция Соединитела Skype для бизнеса Online</li> | | Июль 2020 г| [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Добавлены [cmdlets назначения групповой политики](./assign-policies.md#assign-a-policy-to-a-group)</li> | | Июнь 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Интеграция Соединитела Skype для бизнеса Online<li>Get-Team оптимизации<li>Повышенная надежность</li> | | Июнь 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Добавлена предварительная загрузка для cmdlet<li>Оптимизация .Net Framework</li>   | | Апрель 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode и подписание сборки<li>Добавлено Get-CsPolicyPackage<li>Добавлено Get-CsUserPolicyPackage<li>Добавлено Get-CsUserPolicyPackageRecommendation<li>Добавлено Grant-CsUserPolicyPackage<li>Добавлено New-CsBatchPolicyPackageAssignmentOperation<li>Добавлено Set-TeamArchivedState<li>Добавлено Set-TeamPicture<li>Удалено Get-TeamHelp</li>  | | Март 2020 г| [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Добавлено New-CsBatchPolicyAssignmentOperation</li> | | Февраль 2020 г| [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team оптимизации</li>  |

### <a name="cmdlet-availability"></a>Доступность для cmdlet

> [!NOTE]
> В приведенной ниже таблице содержатся только командлеты, которые являются частью модуля Teams PowerShell. Командлеты Teams в модуле соединителя S[kype для бизнеса Online](/powershell/skype/intro?view=skype-ps) не отображаются. Но так как эти командлеты перенесены в Teams PowerShell, мы добавим их в эту таблицу.

| Командлет | Доступно в режиме public Preview | Доступно в ga |
| -| -- | --|
| [Add-TeamChannelUser](/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Да | **Нет** |
| [Add-TeamUser](/powershell/module/teams/add-teamuser?view=teams-ps) | Да | Да |
| [Add-TeamsAppInstallation](/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Да | **Нет**|
| [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Да | Да |
| [Disconnect-MicrosoftTeams](/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Да | Да |
| [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Да | Да |
| [Get-CsGroupPolicyAssignmentOperation](/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | Да | **Нет** |
| [Get-CsOnlinePowerShellEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | Да | Да |
| [Get-CsPolicyPackage](/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Да | Да |
| [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Да | Да |
| [Get-CsUserPolicyPackage](/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Да | Да |
| [Get-CsUserPolicyPackageRecommendation](/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Да | Да |
| [Get-Team](/powershell/module/teams/get-team?view=teams-ps) | Да | Да |
| [Get-TeamChannel](/powershell/module/teams/get-teamchannel?view=teams-ps) | Да | Да|
| [Get-TeamChannelUser](/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Да | **Нет** |
| [Get-TeamUser](/powershell/module/teams/get-teamuser?view=teams-ps) | Да | Да |
| [Get-TeamsApp](/powershell/module/teams/get-teamsapp?view=teams-ps) | Да | Да |
| [Get-TeamsAppInstallation](/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Да | **Нет** |
| [Grant-CsUserPolicyPackage](/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Да | Да |
| [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Да | Да |
| [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Да | Да |
| [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Да | Да |
| [New-CsOnlineSession](/powershell/module/skype/new-csonlinesession?view=skype-ps) | Да | Да |
| [New-Team](/powershell/module/teams/new-team?view=teams-ps) | Да | Да |
| [New-TeamChannel](/powershell/module/teams/new-teamchannel?view=teams-ps) | Да | Да |
| [New-TeamsApp](/powershell/module/teams/new-teamsapp?view=teams-ps) | Да | Да |
| [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Да | Да |
| [Remove-Team](/powershell/module/teams/remove-team?view=teams-ps) | Да | Да |
| [Remove-TeamChannel](/powershell/module/teams/remove-teamchannel?view=teams-ps) | Да | Да |
| [Remove-TeamChannelUser](/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Да | **Нет** |
| [Remove-TeamsApp](/powershell/module/teams/remove-teamsapp?view=teams-ps) | Да | Да |
| [Remove-TeamsAppInstallation](/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Да | **Нет** |
| [Remove-TeamTargetingHierarchy](./set-up-your-team-hierarchy.md#remove-your-hierarchy) | Да | **Нет**|
| [Remove-TeamUser](/powershell/module/teams/remove-teamuser?view=teams-ps) | Да | Да |
| [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Да | **Нет** |
| [Set-Team](/powershell/module/teams/set-team?view=teams-ps) | Да | Да |
| [Set-TeamArchivedState](/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Да | Да |
| [Set-TeamChannel](/powershell/module/teams/set-teamchannel?view=teams-ps) | Да | Да |
| [Set-TeamPicture](/powershell/module/teams/set-teampicture?view=teams-ps) | Да | Да |
| [Set-TeamsApp](/powershell/module/teams/set-teamapp?view=teams-ps) | Да | Да |
| [Set-TeamTargetingHierarchy](/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Да | **Нет** |
| [Update-TeamsAppInstallation](/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Да | **Нет** |
| [Enable-CsOnlineSessionForReconnection](/skypeforbusiness/set-up-your-computer-for-windows-powershell/diagnose-problems-with-the-skype-for-business-online-connector) | **Нет** | **Нет** |


## <a name="related-topics"></a>Статьи по теме

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Установка Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Справочник по командлетам Microsoft Teams](/powershell/teams/?view=teams-ps)

[Справочник по cmdlet в Skype для бизнеса](/powershell/skype/intro?view=skype-ps)