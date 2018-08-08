---
title: Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 6/1/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
description: Краткое руководство по настройке планов звонков в Microsoft Teams.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ded826a87bbde3e95af3734eb310988db5d7aef
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "19694804"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
==============================================================

Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.

Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)

> [!NOTE]
> Чтобы спланировать и успешно провести развертывание, помимо этого краткого руководства рекомендуем также использовать [практическое руководство](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) и [FastTrack](https://aka.ms/cloudvoice).

За счет добавления планов звонков (компонента Office 365 на основе Skype для бизнеса) приложение Teams теперь позволяет делать и принимать звонки на стационарные и мобильные телефоны по телефонной сети общего пользования (ТСОП).

![Звонки в Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Что необходимо для активации вкладки **Звонки** в Teams
Чтобы включить вкладку **Звонки** в Teams и позволить пользователям совершать и принимать звонки по ТСОП, необходимо подготовить пользователей для использования службы телефонной системы и планов звонков. Соответствующие инструкции см. в разделе [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0) (Настройка планов звонков).

## <a name="teams-interop-policy-configuration"></a>Настройка политики взаимодействия Teams
Для включения групп начать принимать звонки, вам потребуется обновить команды обновления и политики группы взаимодействия, с помощью [групп Майкрософт & Скайп по центру администрирования бизнеса](https://aka.ms/teamsadmincenter) или с помощью удаленного сеанса Windows PowerShell с Скайп для бизнеса [ `*-CsTeamsUpgradePolicy`и `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) командлеты, можно настроить переадресацию звонков для группы.

Дополнительные сведения о политике обновления группы и политики взаимодействия команды можно [миграции и руководство по взаимодействию для организаций, с помощью команды Скайп для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Чтобы найти командлеты PowerShell, необходимую, введите «CsTeamsUpgradePolicy» или «CsTeamsInteropPolicy» в поле **Фильтр** в [Скайп документация командлета Business PowerShell](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Значение по умолчанию групп политики обновления и взаимодействия
Конфигурация политики по умолчанию в Teams предназначена для обеспечения непрерывности бизнес-процессов в ходе развертывания Teams. По умолчанию звонки по VoIP, ТСОП и федеративные звонки вашим пользователям будут по-прежнему поступать в Skype для бизнеса до тех пор, пока вы не обновите политику и не активируете входящие звонки в Teams. Это гарантирует отсутствие непредвиденных нарушений в работе служб голосовой связи при пилотном запуске и развертывании Teams.

Команды обновления политики по умолчанию будет храниться в унаследованный режим, который будет поддерживать групп взаимодействия политику, чтобы определить, где чаты и вызовы маршрутизирует--группы или Скайп для бизнеса.

> [!NOTE]
> Поведение группы обновление политики и скоро будет изменения политики взаимодействия команды, как описано в [руководстве по взаимодействию для организаций, с помощью команды Скайп для бизнеса и миграции](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

В политике взаимодействия Teams задана следующая конфигурация по умолчанию.

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

В конфигурации по умолчанию действует следующее поведение.
* **Для существующих клиентов Skype для бизнеса** эта политика будет направлять все звонки Skype для бизнеса в Skype для бизнеса, а звонки Teams — в Teams. Когда действует эта политика, звонки по ТСОП и федеративные звонки буду направляться в Skype для бизнеса.
* **Для клиентов без Skype для бизнеса** в Teams помимо звонков между пользователями Teams будут доступны только исходящие звонки по ТСОП. Чтобы принимать в Teams звонки по ТСОП, измените политику взаимодействия Teams, назначенную пользователям.

> [!NOTE]
> Пользователи, которым были назначены лицензии на службу телефонной системы с планами звонков, предназначенные для использования со Skype для бизнеса Online, и у которых настроена глобальная политика взаимодействия Teams по умолчанию, получат доступ к вкладке "Звонки" в Teams и смогут совершать исходящие звонки по ТСОП из Teams без необходимости каких-либо действий со стороны администраторов.

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Настройка Teams для приема входящих звонков по ТСОП
Получать входящие вызовы ТСОП в группах, необходимо настроить группы по умолчанию, вызов приложения с применением команды обновления политики с соответствующей группы взаимодействия политики, которая задает `CallingDefaultClient` параметр группам.

> [!IMPORTANT]
> Эту конфигурацию рекомендуется применить к стартовому набору пользователей, чтобы они могли опробовать новые потрясающие возможности звонков в Teams, прежде чем вносить изменения на более широком уровне или на уровне всей организации.

Для продолжения использования устаревших групп политики обновления, воспользоваться следующие предварительно настроенного политики взаимодействия групп для маршрутизации входящих звонков ТСОП к группам:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Если выбрано использование обновленного обновления политики групп, им необходимо назначить TeamsOnly режима для пользователей.

Приведенная выше политика действует следующим образом.
* **Для существующих клиентов Skype для бизнеса** эта политика будет перенаправлять входящие звонки в Teams. В их число входят звонки по VoIP (из Teams и Skype для бизнеса) и звонки по ТСОП. 
* **Для клиентов без Skype для бизнеса** звонки по ТСОП будут поступать в Teams.

> [!WARNING]
> В настоящее время задание параметру `CallingDefaultClient` значения "Teams" будет также влиять на звонки на IP-телефоны Skype для бизнеса. Входящие вызовы не будут поступать на эти телефоны. Их будут принимать только клиенты Teams. Сведения о поддержке существующих сертифицированных SIP-телефонов см. в документе с [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) (Переход со Skype для бизнеса на Microsoft Teams: стратегия внедрения возможностей).

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Как настроить пользователям пользоваться PSTN вызывает в группах
При использовании устаревшего обновления политики групп, применение политики взаимодействия команды, как описано выше, с помощью Скайп для бизнеса удаленного сеанса Windows PowerShell можно настроить переадресацию звонков для группы:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Если вы решите использовать режим TeamsOnly, может изменить режим сосуществования пользователя на TeamsOnly путем группами Майкрософт & Скайп по центру администрирования бизнеса, или с помощью Скайп для бизнеса удаленного сеанса Windows PowerShell можно настроить переадресацию звонков для группы.

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>См. также
[Set up Calling Plans (Настройка планов звонков)](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Руководство по миграции и взаимодействия для организаций, с помощью команды Скайп для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Практическое руководство по телефонной системе с планами звонков в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Справочник по командлетам PowerShell для Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype)

[Справочник по командлетам PowerShell для Teams](https://docs.microsoft.com/powershell/module/teams)
