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
description: Переход со Skype для бизнеса на Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533596"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Вопросы обновления для организаций с локальной учетной записью Skype для бизнеса Server &mdash; для ИТ-администраторов

В этой статье описаны дополнительные факторы, которые могут учитываться для организаций с локальной учетной записью Skype для бизнеса Server. Эта статья является четвертой из нескольких, в статье описаны концепции обновления и реализации для ИТ-администраторов.  

- [Обзор](upgrade-to-teams-on-prem-overview.md)
- [Способы обновления](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Инструменты для управления обновлением](upgrade-to-teams-on-prem-tools.md)
- **Дополнительные вопросы для организаций с локальной** учетной записью Skype для бизнеса (в этой статье)
- [Реализация обновления](upgrade-to-teams-on-prem-implement.md)
- [Вопросы, которые следует учесть при переходе на телефонную сеть общего перейти на телефонную сеть (ПС)](upgrade-to-teams-on-prem-pstn-considerations.md)

Кроме того, в следующих статьях описаны важные понятия обновления и принципы сосуществования.

- [Совместное сосуществование Teams и Skype для бизнеса](upgrade-to-teams-on-prem-coexistence.md)
- [Режимы сосуществования — ссылки](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Вопросы, которые рассматриваются организациями, у нас есть локальное приложение Skype для бизнеса Server

- Для перехода в режим TeamsOnly необходимо настраивать гибридное приложение Skype для бизнеса. Хотя можно использовать Teams в режиме "О-ва" без гибридного решения, переход в режим TeamsOnly невозможен, пока пользователь не будет перемещен из локальной системы Skype для бизнеса в Skype для бизнеса Online (с помощью [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) Дополнительные сведения см. [в сведениях о настройке гибридного подключения.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Если в вашей организации используется Skype для бизнеса Server и вы не настроили гибридное подключение, но все равно хотите использовать Teams, для администрирования функций Teams необходимо использовать административную учетную запись с доменом .onmicrosoft.com. 

- Пользователи Teams с локальной учетной записью Skype для бизнеса (то есть еще не перемещены в облако с помощью Move-CsUser) не могут работать вместе с пользователями Skype для бизнеса и не могут федерировать их с внешними пользователями. Эта функция доступна только после того, как пользователи перемещаются в облако (в режиме "Острова" или как пользователи TeamsOnly). 

- Если у вас есть пользователи с локальной учетной записью Skype для бизнеса, назначить режим TeamsOnly на уровне клиента невозможно. Для завершения миграции в облако необходимо сначала переместить всех пользователей с локальной учетной записью Skype для бизнеса в облако, а затем отключить гибридную `Move-CsUser` [долю.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` не будет работать на уровне клиента, если обнаружена запись DNS lyncdiscover, которая указывает на расположение, которое не является Office 365.

- Убедитесь, что пользователи правильно синхронизированы с Azure AD с правильными атрибутами Skype для бизнеса. Все эти атрибуты являются префиксами msRTCSIP-. Если пользователи не синхронизированы с Azure AD надлежащим образом, средства управления в Teams не смогут управлять этими пользователями. (Например, вы не сможете назначать политики Teams пользователям локальной сети, если не синхронизируете эти атрибуты надлежащим образом.) Дополнительные сведения см. в [настройках Azure AD Connect для Teams и Skype для бизнеса.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Чтобы создать нового пользователя TeamsOnly или Skype для бизнеса Online в гибридной организации, необходимо сначала включить его в локальной организации Skype для бизнеса *Server,* а затем переместить его из локальной сети в облако с помощью Move-CsUser.  Создавая пользователя в локальной сети, вы гарантируете, что все остальные оставшиеся пользователи локальной системы Skype для бизнеса смогут перена должны маршрутить его созданному пользователю. После того как все пользователи будут перемещены в сеть, их не нужно сначала включить в локальной сети.

- При перемещении пользователя из локальной службы в облако собрания, организованные этим пользователем, переносются в Skype для бизнеса Online или Teams в зависимости от того, указан ли переключатель -MoveToTeams.

- Если вы хотите, чтобы в клиенте Skype для бизнеса отображались уведомления для пользователей локальной сети, используйте TeamsUpgradePolicy в локальном средстве. Для пользователей локальной сети имеет значение только параметр NotifySfbUsers.  Пользователи локальной сети получают свой режим от интернет-экземпляров TeamsUpgradePolicy. См. примечания [в Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> Все новые клиенты, созданные после 3 сентября 2019 г., создаются как клиенты TeamsOnly, если в организации не развернуто локальное развертывание Skype для бизнеса Server. Корпорация Майкрософт использует записи DNS для идентификации локальной организации Skype для бизнеса Server. Если в вашей организации есть локальное приложение Skype для бизнеса Server без общедоступных записей DNS, вам потребуется позвонить в службу поддержки Майкрософт, чтобы получить более новую ссылку на клиент. 













## <a name="related-links"></a>Связанные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы переноса собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

