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
ms.openlocfilehash: 56a848f5ea1639e7cd4a8533f15b6005ff1ff10d
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852170"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Заметки о выпуске Microsoft Teams PowerShell

На этой странице вы найдете самую последнюю версию журнала изменений для Teams PowerShell для общедоступной доступности и общедоступной предварительной версии.

## <a name="release-notes"></a>Заметки о выпуске

> [!NOTE]
> **-Preview** в столбце Version (версия) ниже представлены обновления для общедоступной предварительной версии оболочки PowerShell для Teams.

| Дата | Версия | Обновлении |
|------- | -------------------- | ------------------------------ |
| Ноябрь 2020 г. | [1.1.7 — предварительный просмотр](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Использует MSAL для проверки подлинности & авторизации</li><li>Командлеты пакетов политики с рефакторингом и добавление группового пакета</li><li>Реструктурированная Целевая иерархия. выгрузка команд отправки для использования асинхронной модели</li> |
| Сентябрь 2020 г. | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Интеграция соединителя Skype для бизнеса Online</li> |
| Сентябрь 2020 г. | [1.1.5 — предварительный просмотр](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Интеграция соединителя Skype для бизнеса Online</li> |
| 2020 июля | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Добавлены [командлеты назначения групповой политики](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| Июнь 2020 | [1.1.3 — предварительный просмотр](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Интеграция соединителя Skype для бизнеса Online<li>Оптимизация Get-Team<li>Повышенная надежность</li> |
| Июнь 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Добавлена Предварительная загрузка командлета<li>Оптимизации платформы .NET Framework</li>   |
| Апрель 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Подписывание Authenticode и сборка<li>Добавлены Get-CsPolicyPackage<li>Добавлены Get-CsUserPolicyPackage<li>Добавлены Get-CsUserPolicyPackageRecommendation<li>Добавлены Grant-CsUserPolicyPackage<li>Добавлены New-CsBatchPolicyPackageAssignmentOperation<li>Добавлены Set-TeamArchivedState<li>Добавлены Set-TeamPicture<li>Удален Get-TeamHelp</li>  |
| Март 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Добавлены New-CsBatchPolicyAssignmentOperation</li> |
| Фев 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Оптимизация Get-Team</li>  |

### <a name="cmdlet-availability"></a>Доступность командлетов

> [!NOTE]
> Список в приведенной ниже таблице содержит только командлеты, которые встроены в модуль PowerShell Teams. Командлеты Teams в[модуле соединителя S kype для бизнеса Online](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) не отображаются. Тем не менее, так как эти командлеты переносятся в Teams PowerShell, они будут добавлены в эту таблицу.

| Командлет | Доступно в общедоступной предварительной версии | Доступно в GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Да | **Нет** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Да | Да |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Да | **Нет**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Да | Да |
| [Разъединить — MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Да | Да |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Да | Да |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | Да | **Нет** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | Да | Да |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Да | Да |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Да | Да |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Да | Да |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Да | Да |
| [Получение и команда](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Да | Да |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | Да | Да|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Да | **Нет** |
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | Да | Да |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | Да | Да |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Да | **Нет** |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Да | Да |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Да | Да |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Да | Да |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Да | Да |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | Да | Да |
| [Новая группа](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Да | Да |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | Да | Да |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Да | Да |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Да | Да |
| [Удаление группы](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Да | Да |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Да | Да |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Да | **Нет** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Да | Да |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Да | **Нет** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | Да | **Нет**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Да | Да |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Да | **Нет** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Да | Да |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Да | Да |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Да | Да |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Да | Да |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Да | Да |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Да | **Нет** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Да | **Нет** |

## <a name="related-topics"></a>Статьи по теме

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Установка оболочки PowerShell для Teams](teams-powershell-install.md)

[Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md)

[Справочник по командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
