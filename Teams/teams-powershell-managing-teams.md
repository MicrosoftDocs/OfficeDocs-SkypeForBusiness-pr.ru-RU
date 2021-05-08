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
description: Узнайте, как управлять Microsoft Teams помощью Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71f68c813a1379c29cf64ad732eb5da1ffe4d188
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238975"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Управление Teams с помощью Microsoft Teams PowerShell

В этой статье показано, как Microsoft Teams PowerShell для управления Teams и Skype для бизнеса. 

Используйте это руководство вместе со ссылкой на [Microsoft Teams и](/powershell/teams/?view=teams-ps) Skype для бизнеса ссылкой на [Skype для бизнеса.](/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Создание команд и управление ими с помощью PowerShell

Командлеты для создания команд и управления их созданием находятся [в Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Teams группы Office 365, поэтому при создании команды создается группа. Существует набор командлетов для работы с основной командой и ее параметров (, , , ), управления пользователями команды ( , ), а также командлетов для управления каналами команды ``new-team`` ``get-team`` ( ,  ``set-team`` ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` ). Все эти командлеты можно запускать как конечные пользователи, но они будут работать только с командами, владельцем или участником в которые вы состоите. Если вы глобальный администратор или администратор Teams, вы сможете работать со всеми командами в организации.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Идентификатор **GroupId,** используемый в Microsoft Teams модуле PowerShell, такой же, как свойство **Identity,** возвращенное в модуле ``Get-UnifiedGroup`` Exchange PowerShell.

## <a name="manage-policies-via-powershell"></a>Управление политиками с помощью PowerShell

> [!NOTE]
> - Skype для бизнеса Online Connector объединяется с Teams PowerShell. В настоящее время она доступна в режиме предварительной версии. Со временем Skype для бизнеса online, которые применяются к Teams, будут доступны в модуле Teams PowerShell. Шаги установки можно найти в [статье установка Teams PowerShell.](teams-powershell-install.md)
>
> - Они будут доступны в сеансе PowerShell после подключения к Skype для бизнеса Online. Дополнительные сведения см. в [Skype для бизнеса Online с помощью Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Найдите командлеты для управления политиками в модуле Skype для бизнеса [командлетов](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

Политика — это группа параметров, которые можно детально применять к отдельным пользователям. У каждого типа политики есть собственный набор наборов для создания, просмотра, удаления и обновления политик, а затем их назначения пользователям. Общая структура:

- **Команды GET** (например, ): возвращает документы политики, которые можно назначить в организации, включая политики, созданные корпорацией Майкрософт, а также созданные вами настраиваемые ``Get-CsTeamsMeetingPolicy`` политики.
   - Чтобы найти только настраиваемые политики, созданные в организации, используйте ``-Filter "tag:*"`` .

- **Новые** команды (например, ): создание новых политик для организации, назначаемой пользователям ``New-CsTeamsMeetingPolicy`` в организации. Не все политики поддерживают создание настраиваемой политики. Часто это необходимо для того, чтобы политики, которые вы используете в организации, поддерживали сочетание параметров.

- **Команды** SET (например, ``Set-CsTeamsMeetingPolicy`` ): задает определенные значения для данной политики. Некоторые политики не содержат команд SET или содержат параметры, которые нельзя настроить в политике. Описание PowerShell говорит о том, какие параметры нельзя настроить. 
   - Чтобы изменить политику, которая по умолчанию будет назначена пользователям в организации, которым не назначена настраиваемая политика, запустите ``Set-Cs<PolicyName> -Identity Global`` .

- **Команды** REMOVE (например, ): удаляет настраиваемую политику, созданную ``Remove-CsTeamsMeetingPolicy`` в клиенте. При удалении настраиваемой политики, назначенной хотя бы одному пользователю в организации, он вернется к глобальной политике.
   - Глобальную политику в организации удалить нельзя, но если вы хотите восстановить для нее параметры по умолчанию, предоставленные Майкрософт, запустите ``Remove-Cs<PolicyName> -Identity Global`` .

- **Команда** GRANT (например, ``Grant-CsTeamsMeetingPolicy`` ): назначение политики конкретному пользователю.
   - Чтобы удалить назначение настраиваемой политики и вернуть пользователя к политике по умолчанию в организации, запустите ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Не все политики позволяют создавать настраиваемые политики, а некоторые политики имеют параметры, которые нельзя настроить (чтобы можно было просматривать параметры, но не устанавливать настраиваемые значения во время и ``set-`` ``new-`` ). В документации каждого из этих параметров посяговые данные о том, доступны ли параметры для использования клиентами.

Общие параметры:

- **Identity:** для ``Get-`` , , и , параметр ``Set-`` Identity ``New-`` всегда будет ``Remove-`` ссылаться на определенный экземпляр политики.  Для ``Grant`` **параметра Identity** указывается объект пользователя, к которому применяется политика.

## <a name="manage-configurations-via-powershell"></a>Управление конфигурациями с помощью PowerShell

Найдите командлеты для управления конфигурацией в Skype для бизнеса [командлета](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

Конфигурации — это сегменты параметров службы, которые нельзя укадрять на уровне пользователя. Параметры всегда применяется во всей организации. Ваша глобальная конфигурация является единственной эффективной конфигурацией в организации. Каждый тип конфигурации поставляется с двумя основными cmdlets:

- ``Get-Cs<ConfigurationName>`` (Например: ``Get-CsTeamsClientConfiguration`` :

- Команды SET (например, ``Set-CsTeamsClientConfiguration`` ): настройка свойств в конфигурации этого типа. Укажите параметры, которые вы хотите изменить.
   > Вы можете ссылаться на конфигурацию, которую вы хотите изменить, одним из двух способов: с помощью параметра -**Identity Global** или с помощью запуска ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Что может делать каждая роль администратора?

Ознакомьтесь [со Microsoft Teams роли](using-admin-roles.md) администраторов для управления Teams, чтобы понять, какие роли администраторов могут запускать каждый из этих систем.

## <a name="related-topics"></a>Статьи по теме

[Установка Teams PowerShell](teams-powershell-install.md)

[Teams Заметки о выпуске PowerShell](teams-powershell-release-notes.md)

[Teams ссылки на cmdlet](/powershell/teams/?view=teams-ps)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro?view=skype-ps)

[Управление Teams с ролями администратора](using-admin-roles.md)