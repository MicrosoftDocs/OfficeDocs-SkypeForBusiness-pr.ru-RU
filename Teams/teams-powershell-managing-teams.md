---
title: Управление Teams с помощью Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как управлять Microsoft Teams с помощью Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4200c23f6320e67781353e62363d588c230fceb7
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756164"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Управление Teams с помощью Microsoft Teams PowerShell

В этой статье показано, как использовать Microsoft Teams PowerShell для управления Teams и Skype для бизнеса. 

Используйте это руководство в сочетании со справочником по [командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) и Skype для [бизнеса.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Создание команд и управление ими с помощью PowerShell

Командлеты для создания команд и управления группами находятся в модуле [Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Команды создаются при помощи групп Office 365, поэтому при создании команды создается группа. Для работы с основной командой и ее настройками (, , , ), для управления пользователями команды (, ), а также командлеты для управления каналами команды ``new-team`` ``get-team`` ( ,  ``set-team`` ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` ). Все эти командлеты можно запускать как конечные пользователи, но они будут работать только с командами, владельцем или участником которые вы владеете. Если вы глобальный администратор или администратор служб Teams, вы сможете работать со всеми командами в организации.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Код **GroupId,** используемый в модулях Microsoft Teams PowerShell, такой же, как и свойство **Identity,** возвращаемого в модуле ``Get-UnifiedGroup`` Exchange PowerShell.

## <a name="manage-policies-via-powershell"></a>Управление политиками с помощью PowerShell

> [!NOTE]
> - Соединитель Skype для бизнеса Online объединяется в Teams PowerShell. В настоящее время она доступна в режиме предварительной версии. Со временем командлеты Skype для бизнеса Online, которые относятся к Teams, будут полностью доступны в модуле Teams PowerShell. Действия по установке можно найти [в статье об установке Teams PowerShell.](teams-powershell-install.md)
>
> - После подключения к Skype для бизнеса Online эти cmdlets будут доступны в сеансе PowerShell. Дополнительные сведения см. в управлении [Skype для бизнеса Online с помощью Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Найдите командлеты для управления политиками в модуле [командлетов Skype](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)для бизнеса.

Политика — это группа параметров, которые можно детально применять к отдельным пользователям. Каждый тип политики имеет собственный набор наборов для создания, просмотра, удаления и обновления сами политики, а затем назначение этих политик пользователям. Общая структура:

- **Команды GET** (например, ): возвращают документы политики, доступные для назначения в организации, включая политики, созданные корпорацией Майкрософт для использования, а также созданные вами настраиваемые ``Get-CsTeamsMeetingPolicy`` политики.
   - Чтобы найти только настраиваемые политики, созданные в организации, используйте ``-Filter "tag:*"`` .

- **Новые** команды (например, ): создание новых политик для организации, назначаемой пользователям ``New-CsTeamsMeetingPolicy`` в организации. Не все политики поддерживают создание настраиваемой политики. Часто это необходимо для того, чтобы политики, которые вы используете в организации, поддерживали сочетание параметров.

- **Команды** SET (например, ): задает конкретные ``Set-CsTeamsMeetingPolicy`` значения для данной политики. Некоторые политики не имеют команд SET или содержат параметры, которые нельзя настроить в политике. В описании PowerShell описано, какие параметры нельзя настроить. 
   - Чтобы изменить политику, которая по умолчанию будет назначена пользователям в организации, которым не назначена настраиваемая политика, запустите ``Set-Cs<PolicyName> -Identity Global`` ее.

- **Команды** REMOVE (например, ): удаляют настраиваемую политику, созданную ``Remove-CsTeamsMeetingPolicy`` в клиенте. При удалении настраиваемой политики, назначенной хотя бы одному пользователю в организации, этот пользователь вернется к глобальной политике.
   - Удалить глобальную политику в организации нельзя, но если вы хотите восстановить для нее параметры по умолчанию, предоставленные Майкрософт, запустите ``Remove-Cs<PolicyName> -Identity Global`` ее.

- **Команда** GRANT (например, ``Grant-CsTeamsMeetingPolicy`` ): назначает политику конкретному пользователю.
   - Чтобы удалить назначение настраиваемой политики и вернуть пользователя к политике по умолчанию в организации, запустите ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` ее.

> [!TIP]
> Не все политики позволяют создавать настраиваемые политики, и некоторые политики имеют параметры, которые нельзя настроить (чтобы можно было просматривать параметры, но не устанавливать их во время ``set-`` ``new-`` и). В документации каждого из этих параметров содержится информация о том, доступны ли параметры для использования клиентами.

Общие параметры:

- **Identity:** для ``Get-`` ``Set-`` ``New-`` параметра Identity , и, параметр ``Remove-`` **Identity** всегда будет ссылаться на определенный экземпляр политики. Для ``Grant`` **параметра Identity** указывается объект пользователя, к которому применяется политика.

## <a name="manage-configurations-via-powershell"></a>Управление конфигурациями с помощью PowerShell

Найдите в модуле командлетов Skype для бизнеса командлеты для управления [конфигурацией.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

Конфигурации — это сегменты параметров, которые сохраняются в службе, которые нельзя укадрять на уровне пользователя. Параметры всегда применяются во всей организации. Ваша глобальная конфигурация является единственной эффективной конфигурацией в организации. Каждый тип конфигурации имеет два основных cmdlets:

- ``Get-Cs<ConfigurationName>`` (например, ``Get-CsTeamsClientConfiguration`` ):

- Команды SET (например, ``Set-CsTeamsClientConfiguration`` ): заведите свойства в конфигурации этого типа. Укажите параметры, которые вы хотите изменить.
   > Вы можете ссылаться на конфигурацию, которую вы хотите изменить, одним из двух способов: указать :**Identity Global** или путем ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` запуска.

## <a name="what-can-each-admin-role-do"></a>Что может делать каждая роль администратора?

Прочитайте [статью "Использование](using-admin-roles.md) ролей администратора Microsoft Teams для управления Teams", чтобы понять, какие роли администраторов могут выполнить каждый командлет PowerShell.

## <a name="related-topics"></a>Статьи по теме

[Установка Teams PowerShell](teams-powershell-install.md)

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по cmdlet в Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Управление Teams с ролями администратора](using-admin-roles.md)
