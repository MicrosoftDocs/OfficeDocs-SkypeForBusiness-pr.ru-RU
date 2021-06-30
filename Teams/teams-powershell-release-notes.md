---
title: Microsoft Teams Заметки о выпуске PowerShell
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
ms.openlocfilehash: 4ba94e0c0fe466ab742e5b9ccfb42daf63e552a9
ms.sourcegitcommit: 0c942d9e25f9a51bb9bd22b40c5926e1d6d3892d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53186918"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams Заметки о выпуске PowerShell

На этой странице приводится Teams изменений PowerShell для общих выпусков и общедоступной предварительной версии.

## <a name="release-notes"></a>Заметки о выпуске

> [!NOTE]
> **Предварительный** просмотр в столбце версии ниже представляет обновления Teams предварительной версии PowerShell.

| Дата | Версия | Обновления |
|------- | -------------------- | ------------------------------ |
| Май 2021 г. | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>Поддержка входа AccessToken с Подключение MicrosoftTeams. Добавлен параметр -AccessTokens, который принимает массив маркера. Для использования параметра AccessTokens требуются msGraph и Teams маркеры ресурсов.</li><li>Удалены параметры AadAccessToken и MsAccessToken.</li>|
| Май 2021 г. | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>Обновить из . NETCore 2.1 to 3.1</li><li>Добавленный cmdlet to get multi-geo region for users and groups</li><li>Исправления для встроенной проверки подлинности Windows для использования -AccountId с Connect-MicrosoftTeams</li><li>Командлеты TeamsCallHoldPolicy теперь доступны</li><li>Обновления входных параметров и форматов вывода для многих команд</li><li>Устранение большой проблемы с задержкой при перенаправке команд</li><li>Пользовательские пакеты для ga</li>|
| Апрель 2021 г. | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Исправления для интегрированной проверки Windows для использования -AccountId с Подключение-MicrosoftTeams.</li><li>Добавленный cmdlet to get details of total change notification events that can be sent to users (Добавленный cmdlet) для получения сведений о событиях уведомлений об общем изменении, которые можно отправить пользователям.</li><li>Добавленный cmdlet to get multi-geo region for users and groups (Добавить многосемейный регион для пользователей и групп).</li><li>Обработка значений, переданных в teamsEnvironment name, была с чувствительностью к делу. Эта исправлена.</li><li>Основной рефактор удаленного управления сеансами в модуле для упрощения тестов. Администраторы клиентов не должны изменять функциональные функции.</li>|
| Апрель 2021 г. | [Предварительный просмотр 2.1.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Исправлено форматирование выходных данных некоторых командлетов для перезапись (например, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy и других).</li><li>Обновленный список параметров для управления политиками.</li>|
| Март 2021 г. | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Использование MSAL для проверки подлинности & авторизации</li> <li>Connect-MicrosoftTeams является точкой входа для всех cmdlets.</li><li>Новый-csOnlineSession больше не доступен. Он был заменен на Подключение MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection больше не требуется. Эта функция была реализована в модуле Teams PowerShell.</li> <li>Refactored Policy Package cmdlets and adds group package assignment</li><li>Значительные улучшения производительности для Get-Team управления</li> <li>Улучшенные параметры ведения журнала и отладки для существующих cmdlets </li> <li>Добавлены команды управления шаблонами</li> <li>Амортизации New-CsOnlineSession</li>|
| Февраль 2021 г. | [Предварительный просмотр 1.1.11](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Добавлены команды управления шаблонами</li><li>Mezzo и улучшения обработки пакетов для Get-Team-управления</li> <li>Улучшенные параметры ведения журнала и отладки для существующих cmdlets </li> <li>Refactored Policy Package cmdlets</li>|
| Декабрь 2020 г. | [Предварительный просмотр 1.1.10](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Обновления командлета New-Team с увеличенной идной и длительностью спящий режим</li>|
| Декабрь 2020 г. | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Обновления для интеграции Skype для бизнеса Online</li><li>Исправление дубликата запроса с помощью Connect-Microsoft Teams</li>|
| Ноябрь 2020 г. | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Добавляет настраиваемые пакеты политики</li><li>Исправления для команд отправки в иерархии targeting</li>|
| Ноябрь 2020 г. | [Предварительный просмотр 1.1.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Использование MSAL для проверки подлинности & авторизации</li><li>Refactored Policy Package cmdlets and adds group package assignment</li><li>Refactored targeting hierarchy upload commands to use an asynchronous model</li> <li>Если пользователь не использует параметр -credential, при первоначальной проверке подлинности пользователю будет дважды предложено сделать это. Пользователи могут передавать учетные данные с помощью параметра -credential, чтобы избежать дублирования запроса. Это будет исправлено в следующем выпуске.</li> |
| Сентябрь 2020 г. | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype для бизнеса Интеграция с Online Connector</li> |
| Сентябрь 2020 г. | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype для бизнеса Интеграция с Online Connector</li> |
| Июль 2020 г. | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Добавлены [cmdlets назначения групповой политики](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Июнь 2020 г. | [Предварительный просмотр 1.1.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype для бизнеса Интеграция с Online Connector<li>Get-Team оптимизации<li>Повышенная надежность</li> |
| Июнь 2020 г. | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Добавлена предзагрузка "Cmdlet"<li>Оптимизация .Net Framework</li>   |
| Апрель 2020 г. | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode и подписи сборок<li>Добавлено Get-CsPolicyPackage<li>Добавлено Get-CsUserPolicyPackage<li>Добавлено Get-CsUserPolicyPackageRecommendation<li>Добавлено Grant-CsUserPolicyPackage<li>Добавлено New-CsBatchPolicyPackageAssignmentOperation<li>Добавлено Set-TeamArchivedState<li>Добавлено Set-TeamPicture<li>Удалено Get-TeamHelp</li>  |
| Март 2020 г. | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Добавлено New-CsBatchPolicyAssignmentOperation</li> |
| Февраль 2020 г. | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team оптимизации</li>  |

## <a name="related-topics"></a>Статьи по теме

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Установка Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams ссылки на cmdlet](/powershell/teams/?view=teams-ps)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro?view=skype-ps)
