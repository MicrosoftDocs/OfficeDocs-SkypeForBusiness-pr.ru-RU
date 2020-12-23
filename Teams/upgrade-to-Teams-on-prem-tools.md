---
title: Обновление до Teams из локального развертывания Skype для бизнеса — Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Обновление Skype для бизнеса до Teams — инструменты для обновления
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952214d615b62d0175841e2c7b24b45f1ae2d2b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533576"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Инструменты для обновления до Teams &mdash; для ИТ-администраторов

В этой статье описаны инструменты для перехода на Teams. Эта статья — третья из нескольких статей, описывать понятия обновления и реализацию для ИТ-администраторов.  

- [Обзор](upgrade-to-teams-on-prem-overview.md)
- [Способы обновления](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Инструменты для управления обновлением**   (эта статья)
- [Дополнительные соображения для организаций с локальной учетной записью Skype для бизнеса](upgrade-to-teams-on-prem-considerations.md)
- [Реализация перехода](upgrade-to-teams-on-prem-implement.md)
- [Вопросы, которые следует учесть при переходе на телефонную сеть общего перейти на телефонную сеть (ПС)](upgrade-to-teams-on-prem-pstn-considerations.md)

Кроме того, в следующих статьях описаны важные понятия обновления и принципы сосуществования.

- [Совместное сосуществование Teams и Skype для бизнеса](upgrade-to-teams-on-prem-coexistence.md)
- [Режимы сосуществования — ссылки](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Инструменты для управления обновлением

Какой бы способ обновления вы ни выбрали, для пользователей, у которых уже есть Skype для бизнеса Online, вы управляете переходом на TeamsOnly с помощью [TeamsUpgradePolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)который управляет режимом сосуществования пользователей. Для пользователей с локальной учетной записью в Skype для бизнеса Server их также можно использовать для перемещения `Move-CsUser` [в облако.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Дополнительные сведения о каждом из режимов см. в режиме [сосуществования.](migration-interop-guidance-for-teams-with-skype.md)  

Независимо от того, выполняете ли вы переход с выбора возможностей в режимах Skype для бизнеса или просто переходите из конфигурации "Острова" в режим TeamsOnly по умолчанию, TeamsUpgradePolicy является основным инструментом для пользователей, у которых уже есть Skype для бизнеса Online. Как и любую другую политику в Teams, вы можете назначать TeamsUpgradePolicy напрямую пользователю. Вы также можете использовать политику по умолчанию для всего клиента. Любое назначение пользователю имеет приоритет над параметром клиента по умолчанию.  Вы можете управлять политикой в консоли администрирования Teams и PowerShell.

Кроме режима TeamsOnly, можно назначить любой режим TeamsUpgradePolicy пользователям, которые работают в локальной сети Skype для бизнеса. **Режим TeamsOnly можно** на условиях только для пользователя, который уже находится в Skype для бизнеса Online. Это нужно, так как функции телефонной системы и службы Федерации, Skype для бизнеса и Microsoft 365 возможны только в том случае, если пользователь находится в Skype для бизнеса Online. Кроме того, режим **TeamsOnly** невозможно назначить по умолчанию для всего клиента, если у вас развернуто локальное развертывание Skype для бизнеса (обнаружено наличием записи DNS lyncdiscover, которая указывает на расположение, которое не является Office 365).

Пользователей с учетными записьми Skype для бизнеса, которые были домашней, необходимо перенаправить через Интернет [(в](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) Skype для бизнеса Online или прямо в Teams), используя Move-CsUser в локальном средстве Skype для бизнеса. Этих пользователей можно 3 или 2 шага 3:

-   1 шаг. Указание переключателя -MoveToTeams в Move-CsUser. Для этого требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с CU8 или более поздней.

-   2 шага: после запуска Move-CsUser предоставить пользователю TeamsUpgradePolicy режим TeamsOnly.

В отличие от других политик, в Microsoft 365 и Office 365 невозможно создавать новые экземпляры TeamsUpgradePolicy. Все существующие экземпляры встроены в службу.  (Обратите внимание, что режим — это свойство в TeamsUpgradePolicy, а не имя экземпляра политики.) В некоторых случаях (но не для всех) имя экземпляра политики такое же, как в режиме. В частности, чтобы назначить пользователю режим TeamsOnly, вы предоставляете этому пользователю экземпляр UpgradeToTeams TeamsUpgradePolicy. Чтобы увидеть список всех экземпляров, можно выполнить следующую команду:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Чтобы обновить интернет-пользователя до режима TeamsOnly, назначьте экземпляр UpgradeToTeams: 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Чтобы обновить локального пользователя Skype для бизнеса до режима TeamsOnly, Move-CsUser на локальном сервисном сайте:

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

Затем в том же локальном окне PowerShell назначьте новую политику нужным пользователям.

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Перенос собраний

При переходе пользователя в режим TeamsOnly существующие собрания Skype для бизнеса, которые он организовывал, по умолчанию преобразуются в Teams. При назначении пользователю режима TeamsOnly можно отключить поведение по умолчанию. При перемещении пользователей из локальной системы собрания необходимо перенести в облако для работы с учетной записью пользователя в сети, но если не указать -MoveToTeams, собрания будут перенесены как собрания Skype для бизнеса, а не преобразованы в Teams. 

При назначении режима TeamsOnly на уровне клиента перенос собраний не запускается для пользователей. Если вы хотите назначить режим TeamsOnly на уровне клиента и перенести собрания, вы можете с помощью PowerShell получить список пользователей в клиенте (например, с помощью Get-CsOnlineUser с нужными фильтрами), а затем переходить между этими пользователями для запуска переноса собраний с помощью start-CsExMeetingMigration. Подробные сведения см. [в службе переноса собраний (MMS).](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Связанные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы переноса собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

