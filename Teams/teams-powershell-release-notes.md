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
ms.openlocfilehash: da52be2d586bec681a753f22a3db0b2aaf839496
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886728"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Заметки о выпуске Microsoft Teams PowerShell

На этой странице содержится последний журнал изменений Teams PowerShell для общих выпусков и общедоступной предварительной версии.

## <a name="release-notes"></a>Заметки о выпуске

> [!NOTE]
> **Предварительный просмотр** в столбце версии ниже представляет обновления общедоступных предварительных версий Teams PowerShell.

| Дата | Версия | Обновления |
|------- | -------------------- | ------------------------------ |
| Апрель 2021 г. | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Исправления для интегрированной проверки подлинности Windows для использования -AccountId с Connect-MicrosoftTeams.</li><li>Добавленный cmdlet to get details of total change notification events that can be sent to users (Добавленный cmdlet) для получения сведений о событиях уведомлений об общем изменении, которые можно отправить пользователям.</li><li>Добавленный cmdlet to get multi-geo region for users and groups (Добавить многосемейный регион для пользователей и групп).</li><li>Обработка значений, переданных в teamsEnvironment name, была с чувствительностью к делу. Эта исправлена.</li><li>Основной рефактор удаленного управления сеансами в модуле для упрощения тестов. Администраторы клиентов не должны изменять функциональные функции.</li>|
| Апрель 2021 г. | [Предварительный просмотр 2.1.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Фиксированное форматирование существующих командлетов (например, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy и другие).</li><li>Обновленный список параметров для управления политиками.</li>|
| Март 2021 г. | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Использование MSAL для проверки подлинности & авторизации</li> <li>Connect-MicrosoftTeams является точкой входа для всех cmdlets.</li><li>Новый-csOnlineSession больше не доступен. Она заменена на Connect-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection больше не требуется. Эта функция была реализована в модуле Teams PowerShell.</li> <li>Refactored Policy Package cmdlets and adds group package assignment</li><li>Значительные улучшения производительности для Get-Team управления</li> <li>Улучшенные параметры ведения журнала и отладки для существующих cmdlets </li> <li>Добавлены команды управления шаблонами</li> <li>Депрекация New-CsOnlineSession</li>|
| Февраль 2021 г. | [Предварительный просмотр 1.1.11](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Добавлены команды управления шаблонами</li><li>Mezzo и улучшения обработки пакетов для Get-Team-управления</li> <li>Улучшенные параметры ведения журнала и отладки для существующих cmdlets </li> <li>Refactored Policy Package cmdlets</li>|
| Декабрь 2020 г. | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Обновления командлета New-Team с увеличенной идной и длительностью спящий режим</li>|
| Декабрь 2020 г. | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Обновления интеграции Skype для бизнеса Online</li><li>Исправление запроса на дублирование в Connect-Microsoft Teams</li>|
| Ноябрь 2020 г. | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Добавляет настраиваемые пакеты политики</li><li>Исправления для команд отправки в иерархию targeting</li>|
| Ноябрь 2020 г. | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Использование MSAL для проверки подлинности & авторизации</li><li>Refactored Policy Package cmdlets and adds group package assignment</li><li>Refactored targeting hierarchy upload commands to use an asynchronous model</li> <li>Если пользователь не использует параметр -credential, при первоначальной проверке подлинности пользователю будет дважды предложено сделать это. Пользователи могут передавать учетные данные с помощью параметра -credential, чтобы избежать дублирования запроса. Это будет исправлено в следующем выпуске.</li> |
| Сентябрь 2020 г. | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Интеграция Соединитела Skype для бизнеса Online</li> |
| Сентябрь 2020 г. | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Интеграция Соединитела Skype для бизнеса Online</li> |
| Июль 2020 г. | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Добавлены [cmdlets назначения групповой политики](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Июнь 2020 г. | [Предварительный просмотр 1.1.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Интеграция Соединитела Skype для бизнеса Online<li>Get-Team оптимизации<li>Повышенная надежность</li> |
| Июнь 2020 г. | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Добавлена предзагрузка "Cmdlet"<li>Оптимизация .Net Framework</li>   |
| Апрель 2020 г. | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode и подписи сборок<li>Добавлено Get-CsPolicyPackage<li>Добавлено Get-CsUserPolicyPackage<li>Добавлено Get-CsUserPolicyPackageRecommendation<li>Добавлено Grant-CsUserPolicyPackage<li>Добавлено New-CsBatchPolicyPackageAssignmentOperation<li>Добавлено Set-TeamArchivedState<li>Добавлено Set-TeamPicture<li>Удалено Get-TeamHelp</li>  |
| Март 2020 г. | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Добавлено New-CsBatchPolicyAssignmentOperation</li> |
| Февраль 2020 г. | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team оптимизации</li>  |

## <a name="related-topics"></a>Статьи по теме

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Установка Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Справочник по командлетам Microsoft Teams](/powershell/teams/?view=teams-ps)

[Справочник по cmdletлету Skype для бизнеса](/powershell/skype/intro?view=skype-ps)
