---
title: Переход на Teams из локального развертывания Skype для бизнеса (Microsoft Teams)
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Переход со Skype для бизнеса на Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940676"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Средства для перехода на Teams &mdash; для ИТ – администраторов

В этой статье описаны инструменты для перехода на Teams. В этой статье объясняется, как это третья часть, в которой описаны основные понятия и реализация обновления для ИТ – администраторов.  

- [Обзор](upgrade-to-teams-on-prem-overview.md)
- [Способы обновления](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Средства для управления обновлением**   (в этой статье)
- [Дополнительные рекомендации для организаций с локальными приложениями Skype для бизнеса](upgrade-to-teams-on-prem-considerations.md)
- [Реализация перехода](upgrade-to-teams-on-prem-implement.md)
- [Общие сведения о коммутируемых телефонных сетях (КТСОП)](upgrade-to-teams-on-prem-pstn-considerations.md)

Кроме того, в следующих статьях описаны важные концепции обновления и поведение сосуществования.

- [Сосуществование Teams и Skype для бизнеса](upgrade-to-teams-on-prem-coexistence.md)
- [Режимы сосуществования — справочные материалы](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Инструменты для управления обновлением

Какой бы метод обновления вы выбрали, вы управляете переходом к TeamsOnly с помощью [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), который управляет режимом сосуществования пользователя. Дополнительные сведения о каждом из режимов можно найти в разделе [режимы сосуществования](migration-interop-guidance-for-teams-with-skype.md).

Если вы выполняете переход на выбор возможностей в режимах Skype для бизнеса или просто переходите к режиму TeamsOnly из конфигурации острова по умолчанию, то TeamsUpgradePolicy является основным инструментом. Как и любые другие политики в Teams, вы можете назначить TeamsUpgradePolicy прямо пользователю. Вы также можете задать политику в качестве значения по умолчанию на уровне клиента. Любое назначение пользователю имеет приоритет над параметром клиента по умолчанию.  Политику можно управлять на консоли администрирования Teams и в PowerShell.

Вы можете назначить любой режим TeamsUpgradePolicy пользователям в Skype для бизнеса Online или в локальной среде, **за исключением того, что режим TeamsOnly можно назначить только пользователю, уже подключенному к Skype для бизнеса Online**. Это связано с тем, что взаимодействие с пользователями и федерациями Skype для бизнеса, а также с функциями телефонной системы Microsoft 365 возможно только в том случае, если пользователь находится в Skype для бизнеса Online.

Пользователи с учетными записями Skype для бизнеса, расположенные в локальной среде, [должны быть перемещены в Интернет](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (как в Skype для бизнеса Online, так и прямо в Teams) с помощью функции Move-CsUser в локальном наборе инструментов Skype для бизнеса. Эти пользователи могут быть перемещены в TeamsOnly в одном или двух шагах:

-   1 шаг: укажите параметр-MoveToTeams в разделе Move-CsUser. Для этого требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с обновления HF1 или более поздней версии.

-   2 шага: после запуска Move-CsUser, предоставьте пользователю режим TeamsOnly, используя TeamsUpgradePolicy.

В отличие от других политик, нельзя создавать новые экземпляры TeamsUpgradePolicy в Microsoft 365 или Office 365. Все существующие экземпляры встроены в службу.  (Обратите внимание, что Mode является свойством в TeamsUpgradePolicy, а не именем экземпляра политики.) В некоторых случаях имя экземпляра политики является таким же, как и в случае с режимом. В частности, чтобы назначить пользователю режим TeamsOnly, необходимо предоставить этому пользователю экземпляр "UpgradeToTeams" TeamsUpgradePolicy. Чтобы просмотреть список всех экземпляров, вы можете выполнить следующую команду:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Чтобы обновить пользователя Online до режима TeamsOnly, назначьте экземпляр "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Чтобы обновить локальный пользователь Skype для бизнеса до режима TeamsOnly, воспользуйтесь функцией Move-CsUser в локальном наборе инструментов.

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Чтобы изменить режим для всех пользователей в клиенте, за исключением тех, у которых есть явное разрешение пользователя (приоритет), выполните следующую команду:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Если у вас есть пользователи с локальными учетными записями Skype для бизнеса, вам не нужно назначать режим TeamsOnly на уровне клиента, если вы явно не назначаете какой-либо другой режим для всех пользователей в локальной учетной записи Skype для бизнеса.


## <a name="using-notifications-in-skype-for-business-clients"></a>Использование уведомлений в клиентах Skype для бизнеса

Администраторы могут предоставить уведомления конечных пользователей в клиенте Skype для бизнеса, чтобы уведомить пользователей о том, что они вскоре будут обновлены до Teams, как показано на следующей схеме. Например, за неделю до того, как администратор планирует обновить группу пользователей до TeamsOnly режима, администратор может попытаться включить эти уведомления для этой группы пользователей. Эти уведомления включены с помощью экземпляра TeamsUpgradePolicy с NotifySfbUsers = true.  Для всех режимов, кроме TeamsOnly, существует два экземпляра на каждый режим, соответствующие двум значениям NotifySfbUsers.  Для всех режимов, кроме TeamsOnly, существует два экземпляра на каждый режим, соответствующие двум значениям NotifySfbUsers. 

![Диаграмма, на которой показаны уведомления](media/teams-upgrade-sfb-with-notifications.png)

Если пользователи находятся в Skype для бизнеса Online, просто назначьте экземпляр политики, имеющий тот же режим, что и у пользователя, но с помощью NotifySfbUsers = true. 

Если пользователи находятся в локальной среде Skype для бизнеса Server, вам потребуется использовать локальный набор инструментов, и вам понадобится Skype для бизнеса Server 2019 или обновления HF1 для Skype для бизнеса Server 2015. Для пользователей, размещенных в локальной версии Skype для бизнеса, свойство Mode из экземпляра Online TeamsUpgradePolicy принимается, но свойство NotifySfbUsers — нет. Если вы хотите получать уведомления, необходимо создать локальный экземпляр TeamsUpgradePolicy для управления поведением клиента. 

В локальном окне PowerShell создайте новый экземпляр TeamsUpgradePolicy с NotifySfbUsers = true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Затем в том же локальном окне PowerShell Назначьте новую политику для нужных пользователей:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Миграция собрания

Когда пользователь переносится в режим TeamsOnly, существующие собрания Skype для бизнеса по умолчанию будут преобразованы в Teams. Вы можете дополнительно отключить поведение по умолчанию при назначении пользователю режима TeamsOnly. При перемещении пользователей из локальной сети собрания должны быть перенесены в облако для работы с учетной записью пользователя в Интернете, но если не указать параметр-MoveToTeams, собрания будут переноситься в качестве собраний Skype для бизнеса, а не преобразуются в Teams. 

При назначении режима TeamsOnly на уровне клиента миграция собрания не запускается ни для каких пользователей. Если вы хотите назначить режим TeamsOnly на уровне клиента и перенести собрания, вы можете использовать PowerShell для получения списка пользователей в клиенте (например, с помощью команды Get-CsOnlineUser с необходимыми фильтрами), а затем пройти каждый из этих пользователей для активации миграции собраний с помощью Start-CsExMeetingMigration. Подробности можно найти в разделе [Использование службы миграции собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).



## <a name="related-links"></a>Дополнительные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридной связи между Skype для бизнеса Server и Microsoft 365 или Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы миграции собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

