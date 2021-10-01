---
title: Microsoft Teams Заметки о выпуске PowerShell
ms.reviewer: gothambi
author: BrandBer
ms.author: gothambi
manager: naanur
ms.date: 08/31/2021
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте о последних изменениях в Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3cd18d27434599a94daa55a6c42924ab26b266c
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045535"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams Заметки о выпуске PowerShell

На этой странице вы можете Teams журнал изменений PowerShell для общего доступа и общедоступной предварительной версии.

## <a name="release-notes"></a>Заметки о выпуске

> [!NOTE]
> **-preview** в столбце версии ниже представляет обновления для Teams предварительной версии PowerShell.

| Дата | Версия | Обновления |
|------- | -------------------- | ------------------------------ |
| Сентябрь 2021 г. | [2.6.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.0) |<li>Исправлена ошибка, из-за которой при подменике модуля MicrosoftTeams не удалось сделать вложенный модуль другого настраиваемого модуля PowerShell. Теперь командлеты MicrosoftTeams доступны, даже если это вложенный модуль другого модуля.</li><li>Выпуски \| [Получить полное \| \| очистить]-CsOnlineTelephoneNumberOrder.</li><li>Выпуск Get-CsOnlineTelephoneNumberCountry и Get-CsOnlineTelephoneNumberType.</li><li>Выпуск новых параметров для этих cmdlets: Get-CsOnlineApplicationInstance, New-CsExternalAccessPolicy, New-CsTeamsAppSetupPolicy, New-CsTeamsCallingPolicy, New-CsTeamsCallParkPolicy, New-CsTeamsMeetingPolicy, New-CsTeamsMessagingPolicy, Set-CsTeamsAppSetupPolicy, Set-CsTeamsCallParkPolicy, Set-CsTeamsGuestMessagingConfiguration, Set-CsTeamsMeetingPolicy, Set-CsTenantFederationConfiguration, Set-CsExternalAccessPolicy, Set-CsTeamsCallingPolicy.</li><li>Исправление сбоя, который произошел при повторном Connect-MicrosoftTeams при попытке входа.</li><li>Исправления Add-TeamChannelUser Remove-TeamChannelUser сбоя для частного канала.</li><li>Обновления, которые делают заметки о выпуске модуля доступными в коллекции PowerShell для каждой новой версии.</li>
| Сентябрь 2021 г. | [2.5.2](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.2) |<li>Примечание. Начиная с этой версии заметки о выпуске также будут публиковаться в коллекции PowerShell вместе с самим модулем, чтобы уменьшить задержку в доступности заметок о выпуске.</li><li>Releases [Get \| Set \| Grant New \| \| Remove]-CsTeamsEnhancedEncryptionPolicy cmdlets.</li><li>Удаляет [Получить \| новое \| \| удаление]-CsTenantBlockedNumberExceptionPattern.</li><li>Исправлена ошибка, из Microsoft Teams из-за которой не удалось Microsoft Teams модуля powerShell, если он был выполнен во вложенный модуль другого настраиваемого модуля PowerShell. Теперь Microsoft Teams командлеты доступны, даже если это вложенный модуль другого модуля.</li><li>Выпуски \| [Получить полное \| \| очистить]-CsOnlineTelephoneNumberOrder.</li><li>Выпуск Get-CsOnlineTelephoneNumberCountry и Get-CsOnlineTelephoneNumberType.</li><li>Исправление сбоя, который произошел при повторном Connect-MicrosoftTeams при попытке войти.</li><li>Исправления Add-TeamChannelUser Remove-TeamChannelUser сбоя для частного канала.</li>
| Август 2021 г. | [2.5.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.1) |<li>Для входа в токен Access для Connect-MicrosoftTeams теперь используется единый массив маркеров, а не отдельные параметры для каждого маркера ресурса. Дополнительные сведения можно найти [здесь.](/powershell/module/teams/connect-microsoftteams)</li><li>Исправлена интерактивная ошибка входа Connect-MicrosoftTeams в Cloudshell. Теперь по умолчанию используется учетное лицо пользователя, а не запрос на повторное аутентификацию.</li><li>Командлеты TeamsNussignedNumberTreatment теперь доступны.</li><li>Get-CsOnlineDialInConferencingBridge и Set-CsOnlineDialInConferencingBridge теперь перенесены из старой реализации в более новые API.</li><li>Выпущены современные Get-CsTenant и Get-CsOnlineUser (только с параметрами -identity). Они больше не излучают неподготовленные свойства и имеют некоторые изменения форматирования по сравнению с аналогами для перестановки.</li><li>Примечание. New-Team обновления, связанные с версией 2.5.0, были отменены, и была предоставлена предыдущая версия, чтобы избежать каких-либо разрывов изменений.</li>|
| Июль 2021 г. | [Предварительный просмотр 2.4.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>Предоставить изменения, внесенные в cmdlets, уже доступно.</li><li>Выпускаются новые видеокалеты, связанные с голосовой связи.</li><li>Удаление проверки подлинности thumbprint сертификата для -Cs* cmdlets.</li><li>Исправление для ведения журнала для файлов всех cmdlets.</li><li>Исправлены проблемы с командлетами *TeamChannelUser.</li>|
| Июнь 2021 г. | [2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>Предварительная версия только современных версий Get-CsTenant, Get-CsOnlineUser (только с параметром -identity), Get-CsOnlineDialInConferencingLanguagesSupported и Import-CsOnlineAudioFile.</li><li>Современные версии Get-CsOnlineDialInConferencingLanguagesSupported и Import-CsOnlineAudioFile должны работать аналогично их версиям для перенауполниния.</li><li>Современные версии Get-CsTenant и Get-CsOnlineUser (при запуске с параметром -identity) не излучают неподготовленные свойства.</li><li>В современных версиях Get-CsTenant и Get-CsOnlineUser (при запуске с параметром -identity) изменяется форматирование по сравнению с их счетчиками.</li><li>Releases [Get \| Set \| Grant New \| \| Remove]-CsTeamsAudioConferencingPolicy cmdlets.</li><li>Выпуск Get-CsOnlineAudioFile и Remove-CsOnlineAudioFile.</li><li>Set-TeamTargetingHierarchy, Remove-TeamTargetingHierarchy, Get-TeamTargetingHierarchyStatus теперь доступны для GCC пользователей.</li><li>Исправление конечной точки, которая называется командой Get-TeamTargetingHierarchyStatus.</li>|
| Май 2021 г. | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>Поддержка входа AccessToken с Подключение MicrosoftTeams. Добавлен параметр -AccessTokens, который принимает массив маркера. Для использования параметра AccessTokens требуются msGraph и Teams маркеры ресурсов.</li><li>Удалены параметры AadAccessToken и MsAccessToken.</li>|
| Май 2021 г. | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>Обновить из . NETCore 2.1 to 3.1</li><li>Добавленный cmdlet to get multi-geo region for users and groups</li><li>Исправления для встроенной проверки подлинности Windows для использования -AccountId с Connect-MicrosoftTeams</li><li>Командлеты TeamsCallHoldPolicy теперь доступны</li><li>Обновления входных параметров и форматов вывода для многих команд</li><li>Устранение большой проблемы с задержкой при перенаправке команд</li><li>Пользовательские пакеты для ga</li>|
| Апрель 2021 г. | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Исправления для интегрированной Windows проверки подлинности для использования -AccountId с Подключение-MicrosoftTeams.</li><li>Добавленный cmdlet to get details of total change notification events that can be sent to users (Добавленный cmdlet) для получения сведений о событиях уведомлений об общем изменении, которые можно отправить пользователям.</li><li>Добавленный cmdlet to get multi-geo region for users and groups (Добавить многосемейный регион для пользователей и групп).</li><li>Обработка значений, переданных в teamsEnvironment name, была с чувствительностью к делу. Эта исправлена.</li><li>Основной рефактор удаленного управления сеансами в модуле для упрощения тестов. Администраторы клиентов не должны изменять функциональные функции.</li>|
| Апрель 2021 г. | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Исправлено форматирование выходных данных некоторых командлетов для перезапись (например, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy и других).</li><li>Обновленный список параметров для управления политиками.</li>|
| Март 2021 г. | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Использование MSAL для проверки подлинности & авторизации</li> <li>Connect-MicrosoftTeams является точкой входа для всех cmdlets.</li><li>Новый-csOnlineSession больше не доступен. Он был заменен на Подключение MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection больше не требуется. Эта функция была реализована в модуле Teams PowerShell.</li> <li>Refactored Policy Package cmdlets and adds group package assignment</li><li>Значительные улучшения производительности для Get-Team управления</li> <li>Улучшенные параметры ведения журнала и отладки для существующих cmdlets </li> <li>Добавлены команды управления шаблонами</li> <li>Амортизации New-CsOnlineSession</li>|
| Февраль 2021 г. | [Предварительный просмотр 1.1.11](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Добавлены команды управления шаблонами</li><li>Mezzo и пакетные улучшения для Get-Team-управления</li> <li>Улучшенные параметры ведения журнала и отладки для существующих cmdlets </li> <li>Refactored Policy Package cmdlets</li>|
| Декабрь 2020 г. | [Предварительный просмотр 1.1.10](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Обновления командлета New-Team с увеличенной идной и длительностью спящий режим</li>|
| Декабрь 2020 г. | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Обновления для интеграции Skype для бизнеса Online</li><li>Исправление запроса на дублирование с помощью Connect-Microsoft Teams</li>|
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

## <a name="related-topics"></a>См. также

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Установка Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams ссылки на cmdlet](/powershell/teams/)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro)
