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
ms.openlocfilehash: 86d5069794d160d4c4241a67f0c8d45fc9cac708
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046025"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Управление Teams с помощью Microsoft Teams PowerShell

В этой статье показано, как Microsoft Teams PowerShell для управления Teams и Skype для бизнеса.

Используйте это руководство в сочетании с Microsoft Teams [ссылкой](/powershell/teams/?view=teams-ps) на Skype для бизнеса и ссылкой на [Skype для бизнеса.](/powershell/skype/intro?view=skype-ps)

Чтобы управлять Teams в Центре Teams администрирования, см. Teams с помощью облачной оболочки [Azure.](#manage-teams-with-azure-cloud-shell)

## <a name="create-and-manage-teams-using-powershell"></a>Создание команд и управление ими с помощью PowerShell

Командлеты для создания команд и управления их созданием [находятся в Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Teams группы Office 365, поэтому при создании команды создается группа. Существует набор командлетов, которые можно настроить для работы с основной командой и ее настройками (, , , ), для управления пользователями группы ( , ), а также командлеты для управления каналами команды ``new-team`` ``get-team`` ( ,  ``set-team`` ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` ). Все эти командлеты можно запускать как конечные пользователи, но они будут работать только с командами, владельцем или участником в которые вы состоите. Если вы глобальный администратор Teams администратором, вы сможете работать со всеми командами в организации.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> Идентификатор **GroupId,** используемый в Microsoft Teams модуле PowerShell, такой же, как свойство **Identity,** возвращенное в модуле ``Get-UnifiedGroup`` Exchange PowerShell.

## <a name="manage-teams-with-azure-cloud-shell"></a>Управление Teams с помощью облачной оболочки Azure

Облачная оболочка — это интерактивная оболочка с возможностью проверки подлинности, доступная в браузере, которая позволяет управлять ресурсами. Дополнительные сведения о облачной оболочке см. в [этой службе.](/azure/cloud-shell/overview)

Чтобы получить доступ к облачной оболочке Azure и использовать PowerShell для управления Teams, во Teams центре администрирования.

1. В правом верхнем углу выберите значок облачной оболочки.

    ![Снимок экрана: Teams центра администрирования со значком облачной оболочки.](media/cloud-shell-icon-select.png)

1. При запросе выберите **PowerShell**.

    ![Снимок экрана: запрос на использование облачной оболочки Azure.](media/cloud-shell.png)

1. Чтобы начать сеанс Teams PowerShell, запустите следующую команду:

    ```powershell
    Connect-MicrosoftTeams
    ```

После завершения этих действий вы можете запускать команды Teams PowerShell.

> [!IMPORTANT]
> Если вы хотите использовать командлеты CS*, сначала необходимо подключиться к Teams с помощью ``Connect-MicrosoftTeams -UseDeviceAuthentication`` команды.

## <a name="manage-policies-via-powershell"></a>Управление политиками с помощью PowerShell

> [!NOTE]
> - Skype для бизнеса Online Connector объединяется с Teams PowerShell. В настоящее время она доступна в режиме предварительной версии. Со временем Skype для бизнеса Online, которые применяются к Teams, будут доступны в модуле Teams PowerShell. Шаги установки можно найти в статье [установка Teams PowerShell.](teams-powershell-install.md)
> - Они будут доступны в сеансе PowerShell после подключения к Skype для бизнеса Online. Дополнительные сведения см. в [Skype для бизнеса Online с помощью Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Найдите командлеты для управления политиками в модуле Skype для бизнеса [командлетов](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

Политика — это группа параметров, которые можно детально применять к отдельным пользователям. У каждого типа политики есть собственный набор наборов для создания, просмотра, удаления и обновления политик, а затем их назначения пользователям. Общая структура:

- **Команды GET** (например, ): возвращает документы политики, которые можно назначать в организации, включая политики, созданные корпорацией Майкрософт, а также созданные вами настраиваемые ``Get-CsTeamsMeetingPolicy`` политики.
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

- **Identity:** ``Get-`` для ``Set-`` , и , параметр Identity ``New-`` всегда будет ``Remove-`` ссылаться на определенный экземпляр политики.  Для ``Grant`` **параметра Identity** указывается объект пользователя, к которому применяется политика.

## <a name="manage-configurations-via-powershell"></a>Управление конфигурациями с помощью PowerShell

Найдите командлеты для управления конфигурацией в [Skype для бизнеса командлета](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

Конфигурации — это сегменты параметров службы, которые нельзя укадрять на уровне пользователя. Параметры всегда применяется во всей организации. Ваша глобальная конфигурация является единственной эффективной конфигурацией в организации. Каждый тип конфигурации поставляется с двумя основными cmdlets:

- ``Get-Cs<ConfigurationName>`` (Например: ``Get-CsTeamsClientConfiguration`` :

- Команды SET (например, ``Set-CsTeamsClientConfiguration`` ): настройка свойств в конфигурации этого типа. Укажите параметры, которые вы хотите изменить.
    > [!NOTE]
    > Вы можете ссылаться на конфигурацию, которую вы хотите изменить, одним из двух способов: с помощью параметра -**Identity Global** или с помощью запуска ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Что может делать каждая роль администратора?

Ознакомьтесь [со Microsoft Teams роли](using-admin-roles.md) администраторов для управления Teams, чтобы понять, какие роли администраторов могут запускать каждый из этих систем.

## <a name="related-topics"></a>См. также

[Установка Teams PowerShell](teams-powershell-install.md)

[Teams Заметки о выпуске PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Teams](/powershell/teams/?view=teams-ps)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro?view=skype-ps)

[Управление Teams с ролями администратора](using-admin-roles.md)
