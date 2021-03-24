---
title: Инструменты для перехода с локального развертывания Skype для бизнеса на Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Инструменты для обновления Skype для бизнеса до Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5585a2d2995b2f7d470c4d07eab3f5bb7f1934c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097505"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Инструменты для обновления до Teams &mdash; для ИТ-администраторов

В этой статье описаны средства перехода с Skype для бизнеса на Teams. 

Перед началом обновления корпорация Майкрософт рекомендует следующие статьи, в которые описываются важные понятия обновления и принципы сосуществования.

- [Совместное сосуществование Teams и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Режимы сосуществования — ссылки](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Инструменты для управления обновлением

Какой бы способ обновления вы ни выбрали, для пользователей, у которых уже есть Skype для бизнеса Online, вы управляете переходом на TeamsOnly с помощью [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)который управляет режимом сосуществования пользователей. Для пользователей с локальной учетной записью в Skype для бизнеса Server их также можно использовать для перемещения `Move-CsUser` [в облако.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Дополнительные сведения о каждом из режимов см. в режиме [сосуществования.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> Если вы используете Соединитель Skype для бизнеса Online для управления службами, вам потребуется перейти в модуль Teams PowerShell и обновить существующие сценарии PowerShell. Дополнительные сведения см. в модуле [Teams PowerShell](teams-powershell-move-from-sfbo.md) для перемещения между соединительами Skype для бизнеса Online.

Независимо от того, выполняете ли вы переход с выбора возможностей в режимах Skype для бизнеса или просто переходите из конфигурации "Острова" в режим TeamsOnly по умолчанию, TeamsUpgradePolicy является основным инструментом для пользователей, у которых уже есть Skype для бизнеса Online. Как и любую другую политику в Teams, вы можете назначать TeamsUpgradePolicy напрямую пользователю. Вы также можете использовать политику по умолчанию для всего клиента. Любое назначение пользователю имеет приоритет над параметром клиента по умолчанию.  Вы можете управлять политикой в консоли администрирования Teams и PowerShell.

Вы также можете назначить любой режим TeamsUpgradePolicy, кроме режима TeamsOnly, пользователям, которые работают в локальной сети Skype для бизнеса. **Режим TeamsOnly можно** нать только пользователю, который уже находится в Skype для бизнеса Online. Это нужно, так как функциональность телефонной системы и федерации Skype для бизнеса, а также функции телефонной системы Microsoft 365 возможны только в том случае, если пользователь находится в Skype для бизнеса Online. Кроме того, режим **TeamsOnly** нельзя назначить по умолчанию для всего клиента, если у вас есть локальное развертывание Skype для бизнеса (которое обнаруживается наличием DNS-записи lyncdiscover, которая указывает на другое расположение, кроме Office 365).

Пользователей с учетными записьми Skype для бизнеса, которые были домашней, необходимо перенаправить через Интернет [(в](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) Skype для бизнеса Online или прямо в Teams), используя Move-CsUser в локальном средстве Skype для бизнеса. Этих пользователей можно 3 или 2 шага 3.

-   1 шаг. Укажите переключатель -MoveToTeams в Move-CsUser. Для этого требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с CU8 или более поздней.

-   2 шага: после запуска Move-CsUser предоставить пользователю TeamsUpgradePolicy режим TeamsOnly.

В отличие от других политик, в Microsoft 365 и Office 365 невозможно создавать новые экземпляры TeamsUpgradePolicy. Все существующие экземпляры встроены в службу.  (Обратите внимание, что режим — это свойство в TeamsUpgradePolicy, а не имя экземпляра политики.) В некоторых случаях (но не для всех) имя экземпляра политики такое же, как в режиме. В частности, чтобы назначить пользователю режим TeamsOnly, вы предоставляете этому пользователю экземпляр UpgradeToTeams TeamsUpgradePolicy. Чтобы увидеть список всех экземпляров, можно выполнить следующую команду:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Чтобы обновить интернет-пользователя до режима TeamsOnly, назначьте экземпляр UpgradeToTeams: 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Чтобы обновить локального пользователя Skype для бизнеса до режима TeamsOnly, используйте Move-CsUser в локальном средстве:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Чтобы изменить режим для всех пользователей в клиенте, кроме тех, у которых явное разрешение "на пользователя" (которое имеет приоритет), запустите следующую команду:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Если у вас есть пользователи с локальной учетной записью Skype для бизнеса, назначить режим TeamsOnly на уровне клиента невозможно. Их необходимо перемещать в облако по отдельности с помощью Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Использование уведомлений в клиентах Skype для бизнеса

Администраторы могут предоставлять уведомления конечным пользователям в клиенте Skype для бизнеса, чтобы сообщить пользователям о скором обновлении до Teams, как показано на приведенной ниже схеме. Например, за неделю до того, как администратор планирует обновить группу пользователей до режима TeamsOnly, администратор может включить эти уведомления для этой группы пользователей. Эти уведомления включены с использованием экземпляра TeamsUpgradePolicy с NotifySfbUsers=true.  Для всех режимов, кроме TeamsOnly, в одном режиме фактически два экземпляра, соответствующие двум значениям NotifySfbUsers.  Для всех режимов, кроме TeamsOnly, в одном режиме фактически два экземпляра, соответствующие двум значениям NotifySfbUsers. 

![Схема с уведомлениями](media/teams-upgrade-sfb-with-notifications.png)

Если ваши пользователи находятся в Skype для бизнеса Online, просто назначьте экземпляр политики, который имеет тот же режим, что и у пользователя, но с notifySfbUsers=true. 

Если ваши пользователи находятся в локальной компании Skype для бизнеса Server, вам потребуется использовать локальное приложение, а вам — Skype для бизнеса Server 2019 или CU8 для Skype для бизнеса Server 2015. Для пользователей, домашних в локальной сети Skype для бизнеса Server, с учетом свойства mode сетевого экземпляра TeamsUpgradePolicy, но не свойства NotifySfbUsers. При желании вы должны создать локальное экземпляр TeamsUpgradePolicy, чтобы контролировать поведение клиента. 

В локальном окне PowerShell создайте новый экземпляр TeamsUpgradePolicy с notifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Затем в том же локальном окне PowerShell назначьте новую политику нужным пользователям:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Перенос собраний

При переходе пользователя в режим TeamsOnly существующие собрания Skype для бизнеса, которые он организовывал, по умолчанию преобразуются в Teams. При назначении пользователю режима TeamsOnly можно отключить поведение по умолчанию. При перемещении пользователей из локальной системы собрания необходимо перенести в облако для работы с учетной записью пользователя в сети, но если не указать -MoveToTeams, собрания будут перенесены как собрания Skype для бизнеса, а не преобразованы в Teams. 

При назначении режима TeamsOnly на уровне клиента перенос собраний не запускается для пользователей. Если вы хотите назначить режим TeamsOnly на уровне клиента и перенести собрания, вы можете с помощью PowerShell получить список пользователей в клиенте (например, с помощью Get-CsOnlineUser с нужными фильтрами), а затем переходить между этими пользователями для запуска переноса собраний с помощью start-CsExMeetingMigration. Подробные сведения см. [в службе переноса собраний (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Связанные ссылки

[Режимы сосуществования — ссылки](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы переноса собраний (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)