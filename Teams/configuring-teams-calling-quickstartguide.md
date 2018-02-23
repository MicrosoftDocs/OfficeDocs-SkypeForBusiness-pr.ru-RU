---
title: "Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
description: "Краткое руководство по настройке планов звонков в Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f9b266a3ce8d5a151ca608453d7f49821069208
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
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

> [!IMPORTANT]
> Перед настройкой планов звонков в Teams ознакомьтесь с приведенными далее ограничениями.
> * **Teams не поддерживает гибридную голосовую связь.** Гибридная голосовая связь в Teams сейчас не поддерживается. Клиентам, использующим гибридную голосовую связь, не рекомендуется изменять какие-либо политики для получения звонков в Teams, так как это приведет к нарушению работы службы.
> * **Teams не поддерживает федеративные звонки.** Федеративные звонки (звонки между клиентами или компаниями) сейчас не поддерживаются в Teams. Пока их поддержка не будет реализована, такие звонки всегда будут перенаправляться в Skype для бизнеса вне зависимости от того, как настроены вызовы.

## <a name="teams-interop-policy-configuration"></a>Настройка политики взаимодействия Teams
Чтобы активировать возможность приема звонков в Teams, необходимо перенастроить политику взаимодействия Teams на перенаправление звонков в это приложение. Используйте для этого удаленный сеанс Windows PowerShell с командлетами для Skype для бизнеса [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype). Дополнительные сведения о политике взаимодействия Teams см. в разделе [Взаимодействие Microsoft Teams и Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).

> [!TIP]
> Чтобы найти нужные командлеты PowerShell, введите "CsTeamsInteropPolicy" в поле **Фильтр** в [документации по командлетам PowerShell в Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-interop-policy"></a>Политика взаимодействия Teams по умолчанию
Конфигурация политики по умолчанию в Teams предназначена для обеспечения непрерывности бизнес-процессов в ходе развертывания Teams. По умолчанию звонки по VoIP, ТСОП и федеративные звонки вашим пользователям будут по-прежнему поступать в Skype для бизнеса до тех пор, пока вы не обновите политику и не активируете входящие звонки в Teams. Это гарантирует отсутствие непредвиденных нарушений в работе служб голосовой связи при пилотном запуске и развертывании Teams.

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

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a>Настройка Teams для использования политики по умолчанию
Глобальная политика взаимодействия Teams по умолчанию применяется ко всем пользователям в клиенте и настраивается с параметрами по умолчанию, описанными выше. Если по какой-либо причине вы предоставили пользователям разные политики и хотели бы вернуться к настройкам по умолчанию, вам нужно применить глобальную политику взаимодействия Teams через удаленный сеанс Windows PowerShell для Skype для бизнеса.

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> Хотя вы можете изменить значения глобальной политики взаимодействия Teams по умолчанию, настоятельно не рекомендуем это делать. 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Настройка Teams для приема входящих звонков по ТСОП
Для приема входящих звонков по ТСОП в Teams потребуется настроить Teams как приложение для звонков по умолчанию, применив политику взаимодействия Teams с параметром `CallingDefaultClient`, имеющим значение "Teams".

> [!IMPORTANT]
> Эту конфигурацию рекомендуется применить к стартовому набору пользователей, чтобы они могли опробовать новые потрясающие возможности звонков в Teams, прежде чем вносить изменения на более широком уровне или на уровне всей организации.

Для направления входящих звонков по ТСОП в Teams рекомендуем рассмотреть возможность использования следующей готовой политики взаимодействия Teams.

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Приведенная выше политика действует следующим образом.
* **Для существующих клиентов Skype для бизнеса** эта политика будет перенаправлять входящие звонки в Teams. В их число входят звонки по VoIP (из Teams и Skype для бизнеса) и звонки по ТСОП. Федеративные звонки будут по-прежнему поступать в Skype для бизнеса. 
* **Для клиентов без Skype для бизнеса** звонки по ТСОП будут поступать в Teams. Федеративные звонки в Teams сейчас **не поддерживаются**.

> [!WARNING]
> В настоящее время задание параметру `CallingDefaultClient` значения "Teams" будет также влиять на звонки на IP-телефоны Skype для бизнеса. Входящие вызовы не будут поступать на эти телефоны. Их будут принимать только клиенты Teams. Сведения о поддержке существующих сертифицированных SIP-телефонов см. в документе с [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) (Переход со Skype для бизнеса на Microsoft Teams: стратегия внедрения возможностей).

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a>Настройка Teams для приема звонков по ТСОП
Примените политику взаимодействия Teams как описано выше через удаленный сеанс Windows PowerShell для Skype для бизнеса, чтобы перенаправлять звонки в Teams.

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a>Настройка Teams для разрешения пользователям изменять предпочитаемый способ звонков
Чтобы пользователи могли самостоятельно выбирать предпочитаемый способ приема вызовов, т. е. решать, принимать ли звонки в Teams или Skype для бизнеса, создайте настраиваемую политику взаимодействия Teams, которая активирует параметр `AllowEndUserClientOverride`.

Далее приведен пример политики взаимодействия Teams, которая предоставляет пользователю возможность выбора подходящего способа работы со звонками.

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

После применения настраиваемой политики к пользователям в клиенте Teams им станет доступна возможность самостоятельно изменять предпочитаемое приложение для звонков.

![Предпочитаемое приложение для звонков](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> Эту конфигурацию рекомендуется применить к стартовому набору пользователей, прежде чем вносить изменения на более широком уровне или на уровне всей организации.

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a>Создание и применение настраиваемой политики взаимодействия Teams
Чтобы создать, как описано выше, настраиваемую политику взаимодействия Teams в ходе удаленного сеанса Windows PowerShell для Skype для бизнеса, сделайте следующее.

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a>См. также
[Set up Calling Plans (Настройка планов звонков)](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Взаимодействие Microsoft Teams и Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[Практическое руководство по телефонной системе с планами звонков в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Справочник по командлетам PowerShell для Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype)

[Справочник по командлетам PowerShell для Teams](https://docs.microsoft.com/powershell/module/teams)
