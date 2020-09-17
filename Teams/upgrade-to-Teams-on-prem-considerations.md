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
ms.openlocfilehash: c7156c02dff45e170efde9314c15b5688fd43058
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940677"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Рекомендации по обновлению для организаций с локальной версией Skype для бизнеса Server &mdash; для ИТ-администраторов

В этой статье описаны дополнительные вопросы для организаций с локальным приложением Skype для бизнеса Server. Эта статья является четвертой из нескольких описанных выше принципов и реализации обновлений для ИТ – администраторов.  

- [Обзор](upgrade-to-teams-on-prem-overview.md)
- [Способы обновления](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Инструменты для управления обновлением](upgrade-to-teams-on-prem-tools.md)
- **Дополнительные рекомендации для организаций с локальными приложениями Skype для бизнеса (в** этой статье)
- [Реализация обновления](upgrade-to-teams-on-prem-implement.md)
- [Общие сведения о коммутируемых телефонных сетях (КТСОП)](upgrade-to-teams-on-prem-pstn-considerations.md)

Кроме того, в следующих статьях описаны важные концепции обновления и поведение сосуществования.

- [Сосуществование Teams и Skype для бизнеса](upgrade-to-teams-on-prem-coexistence.md)
- [Режимы сосуществования — справочные материалы](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Рекомендации для организаций с локальным подключением Skype для бизнеса Server

- Настройка гибридного развертывания Skype для бизнеса является обязательным условием для перехода в режим TeamsOnly. Несмотря на то что вы можете использовать Teams в режиме "острова" без гибридного развертывания, переход в режим TeamsOnly невозможно, пока пользователь не перейдет из Skype для бизнеса локально в Skype для бизнеса Online (с помощью функции [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)). Дополнительные сведения можно найти в разделе [Настройка гибридного подключения](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Если в вашей организации используется приложение Skype для бизнеса и вы не настроили гибридное подключение, но вы по-прежнему хотите использовать Teams для управления функциями Teams, необходимо использовать учетную запись администратора с onmicrosoft.com доменом. 

- Пользователи Teams, у которых есть учетная запись Skype для бизнеса, локально (то есть они еще не были перемещены в облако с помощью функции Move-CsUser), не могут взаимодействовать с пользователями Skype для бизнеса, а также не могут использовать их вместе с внешними пользователями. Эта функция доступна только в том случае, если пользователи перемещаются в облако (как в режиме острова, так и в качестве пользователей TeamsOnly). 

- Если у вас есть пользователи с локальными учетными записями Skype для бизнеса, вам не нужно назначать режим TeamsOnly на уровне клиента, если вы явно не назначаете какой-либо другой режим для всех пользователей в локальной учетной записи Skype для бизнеса. 

- Вы должны убедиться, что ваши пользователи правильно синхронизируются с Azure AD с правильными атрибутами Skype для бизнеса. Эти атрибуты являются всеми префиксами с помощью "msRTCSIP-". Если пользователи не будут правильно синхронизованы с Azure AD, средства управления в Teams не смогут управлять этими пользователями. (Например, вы не сможете назначать политики для локальных пользователей, если только они не синхронизируются должным образом.) Дополнительные сведения можно найти в разделе [Настройка Azure AD Connect для Teams и Skype для бизнеса](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Чтобы создать в гибридной организации нового пользователя TeamsOnly или Skype для бизнеса Online, *необходимо сначала включить пользователя в локальной среде Skype для бизнеса Server*, а затем переместить пользователя из локальной сети в облако с помощью функции Move-CsUser.  Предварительное создание пользователя в локальной системе гарантирует, что все остальные пользователи Skype для бизнеса смогут перенаправляться на только что созданному пользователю. После того как все пользователи будут перемещены в сеть, вам больше не нужно, чтобы они были включены в локальную версию.

- Когда пользователь перемещается из локальной сети в облако, собрания, упорядоченные по этому пользователю, переносятся в Skype для бизнеса Online или Teams, в зависимости от того, указан ли параметр-MoveToTeams.

- Если вы хотите, чтобы уведомления отображались в клиенте Skype для бизнеса для локальных пользователей, необходимо использовать TeamsUpgradePolicy в локальном наборе инструментов. Для локальных пользователей применим только параметр NotifySfbUsers.  Локальные пользователи получают доступ к своим режимам из Интернет-экземпляров TeamsUpgradePolicy. Ознакомьтесь с заметками в [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Все новые клиенты, созданные после сентября 3, 2019 создаются как клиенты TeamsOnly, если в Организации уже не настроено локальное развертывание Skype для бизнеса Server. Корпорация Майкрософт использует записи DNS для идентификации локальных организаций в Skype для бизнеса Server. Если в вашей организации есть локальный сервер Skype для бизнеса, в котором нет общедоступных DNS-записей, вам потребуется позвонить в службу поддержки Майкрософт, чтобы понизить уровень нового клиента. 



















## <a name="related-links"></a>Дополнительные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридной связи между Skype для бизнеса Server и Microsoft 365 или Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы миграции собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

