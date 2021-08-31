---
title: Инструменты для обновления до Teams из Skype для бизнеса локального развертывания
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Инструменты для обновления с Skype для бизнеса до Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d98257e9a29564d22b57c5cc537d703bbb1fe842
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729308"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Средства для обновления до Teams &mdash; для ИТ-администраторов

В этой статье описаны средства для перехода с Teams Skype для бизнеса. 

Перед началом обновления корпорация Майкрософт рекомендует следующие статьи, в которые описываются основные понятия обновления и принципы совместной работы.

- [Совместное Teams Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Режимы сосуществования — справка](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Инструменты для управления обновлением

Какой бы способ обновления вы ни выбрали, для пользователей, у которых уже есть Skype для бизнеса Online, вы управляете переходом на TeamsOnly с помощью [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)который управляет режимом совместной работы пользователя. Для пользователей с локальной учетной записью в Skype для бизнеса Server вы также можете переместить их в `Move-CsUser` [облако.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Дополнительные сведения о каждом из режимов см. в теме [Режимы сосуществования.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> Если вы используете Skype для бизнеса Online Connector для управления службами, необходимо перейти в модуль Teams PowerShell и обновить существующие сценарии PowerShell. Дополнительные сведения см. в Skype для бизнеса Online Connector в [модуле Teams PowerShell.](teams-powershell-move-from-sfbo.md)

Независимо от того, выполняете ли вы переход на выборку с помощью Skype для бизнеса или просто переходите в режим TeamsOnly с конфигурации "Острова", Основным средством является TeamsUpgradePolicy. Как и любую другую политику в Teams, Вы можете назначать TeamsUpgradePolicy напрямую пользователю. Вы также можете использовать политику по умолчанию для всего клиента. Любое назначение пользователю имеет приоритет над параметром клиента по умолчанию.  Вы можете управлять политикой в консоли Teams администратора и в PowerShell.

Пользователям, которые работают в локальной Skype для бизнеса TeamsUpgradePolicy, можно назначить любой режим TeamsUpgradePolicy, кроме режима TeamsOnly. И наоборот, пользователям, которые работают в облаке, может быть назначен только режим TeamsOnly. **Режим TeamsOnly** можно на назначень только пользователю, который уже находится в облаке, так как функциональность Skype для бизнеса Microsoft 365 телефонная система и федерации возможна только в том случае, если он находится в Skype для бизнеса Online.  Кроме того, вы не можете назначить **режим TeamsOnly** стандартным для всего клиента, если у вас есть локальное развертывание Skype для бизнеса (которое обнаруживается наличием записи DNS lyncdiscover, которая указывает на другое расположение, кроме Office 365. Подробные сведения см. в том, как отключить [гибридную конфигурацию для завершения](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)миграции только на Teams.

Пользователей с Skype для бизнеса локальной учетной записью необходимо перетасковку в режим Teams только с помощью Move-CsUser в локальной Skype для бизнеса. [](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

В отличие от других политик, создать новые экземпляры TeamsUpgradePolicy в Microsoft 365 или Office 365. Все существующие экземпляры встроены в службу.  (Обратите внимание, что режим — это свойство в TeamsUpgradePolicy, а не имя экземпляра политики.) В некоторых случаях (но не все) имя экземпляра политики такое же, как в режиме. В частности, чтобы назначить пользователю режим TeamsOnly, необходимо предоставить ему экземпляр TeamsUpgradePolicy UpgradeToTeams. Чтобы увидеть список всех экземпляров, можно выполнить следующую команду:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Чтобы перейти в режим TeamsOnly, назначьте экземпляр UpgradeToTeams: 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Чтобы обновить локального пользователя Skype для бизнеса до режима TeamsOnly, используйте Move-CsUser в локальном средстве:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

Чтобы изменить режим для всех пользователей в клиенте, за исключением тех, у которых есть явное разрешение на предоставление пользователю (который имеет приоритет), запустите следующую команду:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Если у вас есть пользователи с Skype для бизнеса локальной учетной записью, назначить режим TeamsOnly на уровне клиента невозможно. С помощью Move-CsUser эти пользователи должны перемещаться в Teams только в режиме перемещения.


## <a name="using-notifications-in-skype-for-business-clients"></a>Использование уведомлений в Skype для бизнеса клиентах

Администраторы могут предоставлять уведомления конечным пользователям в клиенте Skype для бизнеса о том, что их скоро обновят до Teams, как показано на приведенной ниже схеме. Например, за неделю до того, как администратор планирует перейти в режим TeamsOnly, администратор может включить эти уведомления для этой группы пользователей. Эти уведомления включены с помощью экземпляра TeamsUpgradePolicy с NotificationSfbUsers=true.  Для всех режимов, кроме TeamsOnly, в одном режиме фактически есть два экземпляра, соответствующие двум значениям NotifySfbUsers.  Для всех режимов, кроме TeamsOnly, в одном режиме фактически есть два экземпляра, соответствующие двум значениям NotifySfbUsers. 

![Схема с уведомлениями.](media/teams-upgrade-sfb-with-notifications.png)

Если ваши пользователи находятся в Skype для бизнеса Online, просто назначьте экземпляр политики, который имеет тот же режим, что и пользователь, но с notifySfbUsers=true. 

Если ваши пользователи находятся в локальной Skype для бизнеса Server, вам потребуется использовать локальное решение, а вам потребуется Skype для бизнеса Server 2019 или CU8 для Skype для бизнеса Server 2015. Для пользователей, Skype для бизнеса Server локальной сети, свойство mode веб-экземпляра TeamsUpgradePolicy будет соблюдаться, но свойство NotifySfbUsers не будет. При желании необходимо создать локальное экземпляр TeamsUpgradePolicy, чтобы контролировать поведение клиента. 

В локальном окне PowerShell создайте новый экземпляр TeamsUpgradePolicy с функцией NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Затем в том же локальном окне PowerShell назначьте новую политику нужным пользователям:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Перенос собраний

При миграции пользователя в режим TeamsOnly существующие собрания, Skype для бизнеса, которые он организовывал, по умолчанию преобразуются в Teams. При назначении пользователю режима TeamsOnly можно отключить поведение по умолчанию. При перемещении пользователей из локальной системы собрания необходимо перенести в облако для работы с учетной записью пользователя в сети, но если не указать -MoveToTeams, собрания будут перенесены как собрания Skype для бизнеса, а не преобразованы в Teams. 

При назначении режима TeamsOnly на уровне клиента перенос собраний не запускается для пользователей. Если вы хотите назначить режим TeamsOnly на уровне клиента и перенести собрания, вы можете использовать PowerShell для получения списка пользователей в клиенте (например, с помощью Get-CsOnlineUser с нужными фильтрами), а затем цикличной миграции для каждого из них, чтобы запустить перенос собраний с помощью start-CsExMeetingMigration. Подробные сведения [см. в том, как использовать службу переноса собраний (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Связанные ссылки

[Режимы сосуществования — справка](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы переноса собраний (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
