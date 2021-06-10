---
title: Средства для обновления до Teams из Skype для бизнеса локального развертывания
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Инструменты для обновления с Skype для бизнеса до Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e37efe19e5256d4722cca54f128e8131e24a116
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282476"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Средства для обновления до Teams &mdash; для ИТ-администраторов

В этой статье описаны средства для перехода с Teams Skype для бизнеса. 

Перед началом обновления корпорация Майкрософт рекомендует следующие статьи, в которые описываются основные понятия обновления и принципы совместной работы.

- [Совместное Teams Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Режимы сосуществования — справка](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Инструменты для управления обновлением

Какой бы способ обновления вы ни выбрали, для пользователей, у которых уже есть Skype для бизнеса Online, вы управляете переходом на TeamsOnly с помощью [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)который управляет режимом совместной работы пользователя. Для пользователей с локальной учетной записью в Skype для бизнеса Server вы также можете переместить их `Move-CsUser` [в облако.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Дополнительные сведения о каждом из режимов см. в теме [Режимы сосуществования.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> Если вы используете Skype для бизнеса Online Connector для управления службами, необходимо перейти в модуль Teams PowerShell и обновить существующие сценарии PowerShell. Дополнительные сведения см. в Skype для бизнеса [Online Connector в модуле Teams PowerShell.](teams-powershell-move-from-sfbo.md)

Независимо от того, выполняете ли вы переход на выборку в режиме Skype для бизнеса или просто переходите в режим TeamsOnly с конфигурации "Острова", TeamsUpgradePolicy является основным средством для пользователей, у которых уже есть Skype для бизнеса Online. Как и любую другую политику в Teams, Вы можете назначать TeamsUpgradePolicy напрямую пользователю. Вы также можете использовать политику по умолчанию для всего клиента. Любое назначение пользователю имеет приоритет над параметром клиента по умолчанию.  Вы можете управлять политикой в консоли Teams администратора и в PowerShell.

Вы также можете назначить пользователям, которые работают в локальной Skype для бизнеса TeamsUpgradePolicy, за исключением режима TeamsOnly. **Режим TeamsOnly можно** на условиях Только для пользователя, который уже находится в Skype для бизнеса Online. Это потому, что Skype для бизнеса пользователями, федерациями и Microsoft 365 телефонная система функциональность возможна только в том случае, если пользователь находится в Skype для бизнеса Online. Кроме того, вы не можете назначить **режим TeamsOnly** стандартным для всего клиента, если у вас есть локальное развертывание Skype для бизнеса (которое обнаруживается наличием записи DNS lyncdiscover, которая указывает на другое расположение, кроме Office 365.

Пользователей с Skype для бизнеса локальной учетной записью необходимо перенаправить в интернет-сеть [(в](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) Skype для бизнеса Online или напрямую в Teams), используя Move-CsUser в локальной Skype для бизнеса. Этих пользователей можно 3 или 2 шага 3 или 2 в TeamsOnly.

-   1 шаг. Укажите переключатель -MoveToTeams в Move-CsUser. Для этого требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с cu8 или более поздней.

-   2 шага. После запуска Move-CsUser предоставить пользователю режим TeamsOnly с помощью TeamsUpgradePolicy.

В отличие от других политик, создать новые экземпляры TeamsUpgradePolicy в Microsoft 365 или Office 365. Все существующие экземпляры встроены в службу.  (Обратите внимание, что режим — это свойство в TeamsUpgradePolicy, а не имя экземпляра политики.) В некоторых случаях (но не все) имя экземпляра политики такое же, как в режиме. В частности, чтобы назначить пользователю режим TeamsOnly, необходимо предоставить ему экземпляр TeamsUpgradePolicy "UpgradeToTeams". Чтобы увидеть список всех экземпляров, можно выполнить следующую команду:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Чтобы перейти в режим TeamsOnly, назначьте экземпляр UpgradeToTeams: 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Чтобы обновить локального пользователя Skype для бизнеса до режима TeamsOnly, используйте Move-CsUser в локальном средстве:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Чтобы изменить режим для всех пользователей в клиенте, за исключением тех, у которых есть явное разрешение на предоставление пользователю (имеет приоритет), запустите следующую команду:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Если у вас есть пользователи с Skype для бизнеса локальной учетной записью, назначить режим TeamsOnly на уровне клиента невозможно. С помощью Move-CsUser эти пользователи должны перемещаться в облако по отдельности.


## <a name="using-notifications-in-skype-for-business-clients"></a>Использование уведомлений в Skype для бизнеса клиентах

Администраторы могут предоставлять уведомления конечным пользователям в клиенте Skype для бизнеса о том, что их скоро обновят до Teams, как показано на приведенной ниже схеме. Например, за неделю до того, как администратор планирует перейти в режим TeamsOnly, администратор может включить эти уведомления для этой группы пользователей. Эти уведомления включены с помощью экземпляра TeamsUpgradePolicy с NotificationSfbUsers=true.  Для всех режимов, кроме TeamsOnly, в одном режиме фактически есть два экземпляра, соответствующие двум значениям NotifySfbUsers.  Для всех режимов, кроме TeamsOnly, в одном режиме фактически есть два экземпляра, соответствующие двум значениям NotifySfbUsers. 

![Схема с уведомлениями](media/teams-upgrade-sfb-with-notifications.png)

Если ваши пользователи находятся в Skype для бизнеса Online, просто назначьте экземпляр политики, который имеет тот же режим, что и пользователь, но с помощью NotifySfbUsers=true. 

Если ваши пользователи находятся в локальной Skype для бизнеса Server, вам потребуется использовать локальное решение для Skype для бизнеса Server 2019 или CU8 для Skype для бизнеса Server 2015. Для пользователей, Skype для бизнеса Server локального экземпляра TeamsUpgradePolicy, будет соблюдаться свойство mode из интернет-экземпляра TeamsUpgradePolicy, но свойство NotifySfbUsers не будет. При желании необходимо создать локальное экземпляр TeamsUpgradePolicy, чтобы контролировать поведение клиента. 

В локальном окне PowerShell создайте новый экземпляр TeamsUpgradePolicy с функцией NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Затем в том же локальном окне PowerShell назначьте новую политику нужным пользователям:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Перенос собраний

При переносе пользователя в режим TeamsOnly существующие собрания, Skype для бизнеса, которые он организовывал, по умолчанию преобразуются в Teams. При назначении пользователю режима TeamsOnly можно отключить поведение по умолчанию. При перемещении пользователей из локальной системы собрания необходимо перенести в облако для работы с учетной записью пользователя в сети, но если не указать -MoveToTeams, собрания будут перенесены как собрания Skype для бизнеса, а не преобразованы в Teams. 

При назначении режима TeamsOnly на уровне клиента перенос собраний не запускается для пользователей. Если вы хотите назначить режим TeamsOnly на уровне клиента и перенести собрания, вы можете использовать PowerShell для получения списка пользователей в клиенте (например, с помощью Get-CsOnlineUser с нужными фильтрами), а затем цикличной миграции для каждого из них, чтобы запустить перенос собраний с помощью Start-CsExMeetingMigration. Подробные сведения см. в том, как использовать службу [переноса собраний (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Связанные ссылки

[Режимы сосуществования — справка](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы переноса собраний (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)