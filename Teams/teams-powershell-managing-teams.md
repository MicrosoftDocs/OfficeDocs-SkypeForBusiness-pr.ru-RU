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
ms.openlocfilehash: 66f873b163222d3d9745e68881da2b8071f60eec
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396530"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Управление Teams с помощью Microsoft Teams PowerShell

В этой статье показано, как использовать Microsoft Teams PowerShell для управления Teams и Skype для бизнеса.

Используйте это руководство в сочетании со справочником по [командлетам Microsoft Teams](/powershell/teams/?view=teams-ps) [и Skype для бизнеса командлетами](/powershell/skype/intro?view=skype-ps).

Сведения об управлении Teams в Центре администрирования Teams см. в статье ["Управление Teams с помощью Azure Cloud Shell](#manage-teams-with-azure-cloud-shell)".

## <a name="create-and-manage-teams-using-powershell"></a>Создание команд и управление ими с помощью PowerShell

Командлеты для создания команд и управления ими находятся в модуле [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Teams поддерживаются группами Office 365, поэтому при создании команды вы создаете группу. Существует набор командлетов для работы с основной командой и ее параметрами (``new-team``, , управление ``set-team``пользователями группы (``add-teamuser``, ``remove-teamuser``), а также командлеты для управления каналами команды (``new-teamchannel``, ``remove-teamchannel````get-team``). Все эти командлеты можно запускать от имени конечных пользователей, но они будут работать только с командами, которыми вы владеете или входите в нее. Если вы глобальный администратор Администратор или администратор Teams, вы сможете работать со всеми командами в вашей организации.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> Идентификатор **groupId**, используемый в командлетах модуля Microsoft Teams PowerShell, совпадает со свойством **Identity**``Get-UnifiedGroup``, возвращенным модулем Exchange PowerShell.

## <a name="manage-teams-with-azure-cloud-shell"></a>Управление Teams с помощью Azure Cloud Shell

Cloud Shell является интерактивной оболочкой с проверкой подлинности, доступной в браузере, которая позволяет управлять ресурсами. Дополнительные сведения о Cloud Shell см. в [Cloud Shell](/azure/cloud-shell/overview).

Чтобы получить доступ к azure Cloud Shell и использовать PowerShell для управления Teams, войдите в Центр администрирования Teams.

1. Щелкните значок Cloud Shell в правом верхнем углу.

    ![Снимок экрана: заголовок Центра администрирования Teams со Cloud Shell значком.](media/cloud-shell-icon-select.png)

1. При появлении запроса выберите **PowerShell**.

    ![Снимок экрана: запрос Cloud Shell Azure.](media/cloud-shell.png)

1. Выполните следующую команду, чтобы запустить сеанс Teams PowerShell:

    ```powershell
    Connect-MicrosoftTeams
    ```

После выполнения этих действий можно приступать к выполнению команд Teams PowerShell.

> [!IMPORTANT]
> Если вы хотите использовать командлеты Cs* , сначала необходимо подключиться к Teams с помощью команды ``Connect-MicrosoftTeams -UseDeviceAuthentication`` .

## <a name="manage-policies-via-powershell"></a>Управление политиками с помощью PowerShell

> [!NOTE]
> - Skype для бизнеса Соединитель Online консолидирован в Teams PowerShell. В настоящее время он доступен в общедоступной предварительной версии. Со временем Skype для бизнеса Online, применимые к Teams, будут изначально доступны в модуле Teams PowerShell. Инструкции по установке см. в статье ["Установка Teams PowerShell](teams-powershell-install.md) ".
> - Командлеты будут доступны в сеансе PowerShell после подключения к Skype для бизнеса Online. Дополнительные сведения см. в разделе ["Управление Skype для бизнеса Online с помощью Office 365 PowerShell"](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Найдите командлеты для управления политиками в Skype для бизнеса [командлета](/powershell/module/teams).

Политика — это группа параметров, которые можно детально применять к отдельным пользователям. Каждый тип политики имеет собственный набор командлетов для создания, просмотра, удаления и обновления самих политик, а затем назначения этих политик пользователям. Общая структура:

- **Команды GET** (например, ): возвращает документы политики, ``Get-CsTeamsMeetingPolicy``доступные для назначения в организации, включая политики, созданные корпорацией Майкрософт для использования, а также созданные вами настраиваемые политики.
  - Чтобы найти только пользовательские политики, созданные в организации, используйте ``-Filter "tag:*"``.

- **Команды NEW** (например, ``New-CsTeamsMeetingPolicy``): создает новые политики для назначения пользователям в организации. Не все политики поддерживают создание пользовательских политик. Часто это необходимо для того, чтобы политики, которые вы используете в организации, поддерживали сочетание параметров.

- **Команды SET** (например, ``Set-CsTeamsMeetingPolicy``): задает определенные значения для данной политики. Некоторые политики не имеют доступных команд SET или содержат параметры, которые не могут быть настроены в политике. В описаниях PowerShell указывается, какие параметры нельзя настроить.
  - Чтобы изменить политику, которая будет по умолчанию назначена пользователям в организации, которым не назначена пользовательская политика, выполните команду ``Set-Cs<PolicyName> -Identity Global``.

- **Команды REMOVE** (например, ``Remove-CsTeamsMeetingPolicy``): удаляет пользовательскую политику, созданную в клиенте. Если удалить пользовательскую политику, назначенную по крайней мере одному пользователю в организации, этот пользователь возвратится к глобальной политике.
  - Вы не можете удалить глобальную политику в организации, но если вы хотите сбросить глобальную политику в организации до параметров по умолчанию, предоставленных Корпорацией Майкрософт, выполните команду ``Remove-Cs<PolicyName> -Identity Global``.

- **Команда GRANT** (например, ``Grant-CsTeamsMeetingPolicy``): назначает политику конкретному пользователю.
  - Чтобы удалить назначение настраиваемой политики и вернуть пользователя к политике по умолчанию в организации, выполните команду ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> Не все политики позволяют создавать настраиваемые политики, а некоторые политики имеют параметры, которые нельзя настроить (``set-````new-``чтобы можно было просмотреть параметр, но не задать настраиваемое значение во время и). В документации по каждому командлету указывается, доступны ли параметры для использования клиентами.

Общие параметры:

- **Удостоверение**: для ``Get-``параметра  Identity , ``Set-````New-``и ``Remove-``, всегда будет ссылаться на определенный экземпляр политики. Для ``Grant``**параметра Identity** используется определенный объект пользователя, к которому применяется политика.

## <a name="manage-configurations-via-powershell"></a>Управление конфигурациями с помощью PowerShell

Найдите командлеты для управления конфигурацией в Skype для бизнеса [командлета](/powershell/module/skype).

Конфигурации — это контейнеры параметров, поддерживаемые в службе, которые нельзя указать на уровне пользователя. Параметры всегда применяются во всей организации. Глобальная конфигурация — это только эффективная конфигурация в вашей организации. Каждый тип конфигурации поставляется с двумя основными командлетами:

- ``Get-Cs<ConfigurationName>`` (например, ``Get-CsTeamsClientConfiguration``):

- Команды SET (например, ``Set-CsTeamsClientConfiguration``): задайте свойства в конфигурации этого типа. Укажите параметры, которые требуется изменить.
    > [!NOTE]
    > Вы можете ссылаться на конфигурацию, которую вы изменяете, одним из двух способов: путем указания -**Identity Global** или путем запуска ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.

## <a name="what-can-each-admin-role-do"></a>Что может делать каждая роль администратора?

[Прочтите сведения об использовании ролей администратора Microsoft Teams для управления Teams](using-admin-roles.md), чтобы понять, какие роли администраторов могут запускать каждый командлет PowerShell.

## <a name="related-topics"></a>См. также

[Установка Teams PowerShell](teams-powershell-install.md)

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Teams](/powershell/teams/?view=teams-ps)

[Skype для бизнеса командлета](/powershell/skype/intro?view=skype-ps)

[Управление Teams с ролями администратора](using-admin-roles.md)
