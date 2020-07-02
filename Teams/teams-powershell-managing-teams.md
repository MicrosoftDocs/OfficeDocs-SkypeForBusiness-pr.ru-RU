---
title: Управление группами с помощью Microsoft Teams PowerShell
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
description: Сведения о том, как управлять Microsoft Teams с помощью PowerShell Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944148"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Управление группами с помощью Microsoft Teams PowerShell

В этой статье объясняется, как использовать Microsoft Teams PowerShell для управления группами и Skype для бизнеса. 

Используйте это руководство в сочетании с ссылкой на [командлет Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) и [ссылкой на командлеты Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="create-and-manage-teams-using-powershell"></a>Создание команд и управление ими с помощью PowerShell

Командлеты для создания и управления группами находятся в [модуле Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Команды создаются для групп Office 365, поэтому при создании группы создайте группу. Существует набор командлетов, предназначенных для работы с основной командой и ее параметрами ( ``new-team`` , ``get-team`` , ``set-team`` ), Управление пользователями группы ( ``add-teamuser`` , ``remove-teamuser`` ), а также командлетами для управления каналами группы ( ``new-teamchannel`` , ``remove-teamchannel`` ). Все эти командлеты можно запускать как конечные пользователи, но они будут работать только в тех группах, которыми вы владеете или являетесь участниками. Если вы являетесь администратором глобального администратора или службы Teams Service, вы сможете работать со всеми группами в Организации.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> Идентификатор **groupId** , используемый в командлетах модуля Microsoft Teams PowerShell, совпадает со свойством **Identity** , возвращенным ``Get-UnifiedGroup`` в модуле Exchange PowerShell.

## <a name="manage-policies-via-powershell"></a>Управление политиками через PowerShell

> [!NOTE]
> - Соединитель Skype для бизнеса Online консолидируется в командную оболочку PowerShell. В настоящее время она доступна в общедоступном предварительном просмотре. На данный момент командлеты Skype для бизнеса Online, применимые к Teams, будут доступны в модуле PowerShell Teams. Инструкции по установке можно найти в статье [Установка оболочки PowerShell для Teams](teams-powershell-install.md) .
>
> - После подключения к Skype для бизнеса Online командлеты будут доступны в сеансе PowerShell. Дополнительные сведения можно найти в разделе [Управление Skype для бизнеса Online в Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Найдите командлеты для управления политиками в [модуле командлетов Skype для бизнеса](https://www.microsoft.com/download/details.aspx?id=39366).

Политика — это группа параметров, которые могут быть применены к отдельным пользователям. У каждого типа политики есть собственный набор командлетов для создания, просмотра, удаления и обновления политик, а затем назначения этих политик пользователям. Общая структура:

- **Получить** команды (например, ``Get-CsTeamsMeetingPolicy`` ): возвращает документы политики, которые можно назначить в вашей организации, включая политики, созданные корпорацией Майкрософт, и созданные вами пользовательские политики.
   - Чтобы найти только пользовательские политики, созданные в вашей организации, используйте ``-Filter "tag:*"`` .

- **Новые** команды (например, ``New-CsTeamsMeetingPolicy`` ): создает новые политики для Организации, назначаемые пользователям в Организации. Не все политики поддерживают создание настраиваемых политик. Чаще всего это необходимо для того, чтобы политики, используемые в вашей организации, поддерживали сочетание параметров.

- **Set** Commands (например, ``Set-CsTeamsMeetingPolicy`` ): задает определенные значения для указанной политики. Некоторые политики не имеют доступных команд SET или содержат параметры, которые не могут быть настроены в политике. В описаниях PowerShell вы можете указать, какие параметры нельзя настроить. 
   - Чтобы изменить политику, которая будет использоваться по умолчанию для пользователей в вашей организации, у которых нет назначенной особой политики, запустите ``Set-Cs<PolicyName> -Identity Global`` .

- **Удалить** команды (например, ``Remove-CsTeamsMeetingPolicy`` ): удаляет специальную политику, созданную в клиенте. При удалении настраиваемой политики, назначенной по крайней мере одному пользователю в Организации, этот пользователь будет возвращаться к глобальной политике.
   - Вы не можете удалить глобальную политику в вашей организации, но если вы хотите сбросить глобальную политику в вашей организации до указанных для Microsoft параметров по умолчанию, выполните ``Remove-Cs<PolicyName> -Identity Global`` .

- Команда **Grant** (например, ``Grant-CsTeamsMeetingPolicy`` ): назначение политики определенному пользователю.
   - Чтобы удалить настраиваемое назначение политики и вернуть пользователя к политике по умолчанию в вашей организации, выполните ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Не все политики допускают создание настраиваемых политик, а некоторые политики имеют параметры, которые нельзя настраивать (поэтому вы можете просматривать параметры, но не может задавать пользовательские значения во время ``set-`` и ``new-`` ). В документации для каждого командлета осуществляется обращение к параметрам, которые можно использовать для пользователей.

Общие параметры:

- **Identity**: for ``Get-`` , ``Set-`` , ``New-`` и ``Remove-`` , параметр **Identity** всегда будет ссылаться на определенный экземпляр политики. Для ``Grant`` параметра **Identity** — конкретный объект пользователя, которому применяется политика.

## <a name="manage-configurations-via-powershell"></a>Управление конфигурациями с помощью PowerShell

Найдите командлеты для управления конфигурацией в [модуле командлетов Skype для бизнеса](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Конфигурации — это сегменты параметров, поддерживаемых в службе, которые не могут быть указаны на уровне пользователя. Параметры всегда применяются во всей Организации. Ваша Глобальная конфигурация является единственной действующей конфигурацией в вашей организации. Каждый тип конфигурации поставляется с двумя основными командлетами:

- ``Get-Cs<ConfigurationName>``(например, ``Get-CsTeamsClientConfiguration`` ):

- SET Commands (например, ``Set-CsTeamsClientConfiguration`` ): Настройка свойств в конфигурации этого типа. Укажите параметры, которые вы хотите изменить.
   > Вы можете создать ссылку на изменяемую конфигурацию одним из двух способов: указав**глобальный идентификатор**или запустив приложение ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Что может делать каждая роль администратора?

Прочитать [Используйте роли администратора Microsoft Teams для управления группами](using-admin-roles.md) , чтобы понять, какие роли администратора могут выполнять каждый командлет PowerShell.

## <a name="related-topics"></a>Статьи по теме

[Установка оболочки PowerShell для Teams](teams-powershell-install.md)

[Заметки о выпуске оболочки PowerShell для Teams](teams-powershell-release-notes.md)

[Справочник по командлетам Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Управление Teams с ролями администратора](using-admin-roles.md)