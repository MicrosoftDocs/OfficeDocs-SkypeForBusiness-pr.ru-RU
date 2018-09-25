---
title: Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Краткое руководство по настройке планов звонков в Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a1fb82f57035f238ce222bf7f21b72983d21075
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015935"
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
Чтобы включить вкладку **Звонки** в Teams и позволить пользователям совершать и принимать звонки по ТСОП, необходимо подготовить пользователей для использования службы телефонной системы и планов звонков. Соответствующие инструкции см. в разделе [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans) (Настройка планов звонков).

## <a name="teams-interop-policy-configuration"></a>Настройка политики взаимодействия Teams
Чтобы разрешить Teams принимать звонки, нужно изменить политику обновления Teams и политику взаимодействия Teams с помощью [Microsoft Teams и Центра администрирования Skype для бизнеса](https://aka.ms/teamsadmincenter) или удаленного сеанса Windows PowerShell с командлетами [`*-CsTeamsUpgradePolicy` и `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) Skype для бизнеса для перенаправления звонков в Teams.

Дополнительные сведения о политиках обновления и взаимодействия Teams см. в статье [Руководство по миграции и взаимодействию для организаций с использованием Teams вместе со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Чтобы найти нужные командлеты PowerShell, введите "CsTeamsUpgradePolicy" или "CsTeamsInteropPolicy" в поле **Фильтр** в [документации по командлетам PowerShell в Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Политики обновления и взаимодействия Teams по умолчанию
Конфигурация политики по умолчанию в Teams предназначена для обеспечения непрерывности бизнес-процессов в ходе развертывания Teams. По умолчанию звонки по VoIP, ТСОП и федеративные звонки вашим пользователям будут по-прежнему поступать в Skype для бизнеса до тех пор, пока вы не обновите политику и не активируете входящие звонки в Teams. Это гарантирует отсутствие непредвиденных нарушений в работе служб голосовой связи при пилотном запуске и развертывании Teams.

Политика обновления Teams по умолчанию находится в устаревшем режиме, который учитывает политику взаимодействия Teams для определения места для перенаправления чатов и звонков — Teams или Skype для бизнеса.

> [!NOTE]
> Режим работы политик обновления и взаимодействия Teams скоро изменится, как описано в статье [Руководство по миграции и взаимодействию для организаций с использованием Teams вместе со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

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
Для приема входящих звонков по ТСОП в Teams потребуется настроить Teams как приложение для звонков по умолчанию, применив политику обновления Teams с соответствующей политикой взаимодействия Teams, которая задает для параметра `CallingDefaultClient` значение Teams.

> [!IMPORTANT]
> Эту конфигурацию рекомендуется применить к стартовому набору пользователей, чтобы они могли опробовать новые потрясающие возможности звонков в Teams, прежде чем вносить изменения на более широком уровне или на уровне всей организации.

Если вы хотите продолжить использование устаревшей политики обновления Teams, используйте следующую предварительно настроенную политику взаимодействия Teams для маршрутизации входящих звонков по ТСОП в Teams:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Если вы хотите использовать измененную политику обновления Teams, вам нужно назначить своим пользователям режим TeamsOnly.

Приведенная выше политика действует следующим образом:
* **Для существующих клиентов Skype для бизнеса** эта политика будет перенаправлять входящие звонки в Teams. В их число входят звонки по VoIP (из Teams и Skype для бизнеса) и звонки по ТСОП. 
* **Для клиентов без Skype для бизнеса** звонки по ТСОП будут поступать в Teams.

> [!WARNING]
> В настоящее время задание параметру `CallingDefaultClient` значения "Teams" будет также влиять на звонки на IP-телефоны Skype для бизнеса. Входящие вызовы не будут поступать на эти телефоны. Их будут принимать только клиенты Teams. Сведения о поддержке существующих сертифицированных SIP-телефонов см. в документе с [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) (Переход со Skype для бизнеса на Microsoft Teams: стратегия внедрения возможностей).

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Настройка пользователей для получения звонков по ТСОП в Teams
Примените политику взаимодействия Teams, как описано выше, через удаленный сеанс Windows PowerShell для Skype для бизнеса, чтобы перенаправлять звонки в Teams:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Если вы решили использовать режим TeamsOnly, то можете изменить режим сосуществования пользователя на TeamsOnly через Microsoft Teams и Центр администрирования Skype для бизнеса либо через удаленный сеанс Windows PowerShell Skype для бизнеса, чтобы перенаправлять звонки в Teams:

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>См. также
[Set up Calling Plans (Настройка планов звонков)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Руководство по миграции и взаимодействия для организаций, использующих Teams вместе со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Практическое руководство по телефонной системе с планами звонков в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Справочник по командлетам PowerShell для Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype)

[Справочник по командлетам PowerShell для Teams](https://docs.microsoft.com/powershell/module/teams)
