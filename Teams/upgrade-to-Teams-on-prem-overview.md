---
title: Переход на Teams из локального развертывания Skype для бизнеса (Microsoft Teams)
author: msdmaguire
ms.author: dmaguire
manager: serdars
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
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578402"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Переход с Skype для бизнеса на Teams &mdash; для ИТ-администраторов

## <a name="overview"></a>Обзор

При переходе с Skype для бизнеса на Teams для некоторых организаций требуется прогрессивный выпуск, который планируется и управляется ИТ-подразделениями. Статьи в этом разделе предназначены преимущественно для ИТ – администраторов в крупных организациях. Эти организации обычно являются локальными, но они также могут быть крупными организациями Skype для бизнеса Online. Перед тем как читать эти статьи, ознакомьтесь со статьей начало [работы с обновлением Teams](upgrade-start-here.md) и [средой обновления](upgrade-framework.md).


В следующих статьях вы найдете инструкции по обновлению для своей организации: 

- [Способы обновления](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Инструменты для управления обновлением](upgrade-to-teams-on-prem-tools.md)
- [Дополнительные рекомендации для организаций с локальными приложениями Skype для бизнеса](upgrade-to-teams-on-prem-considerations.md)
- [Реализация перехода](upgrade-to-teams-on-prem-implement.md)
- [Общие сведения о коммутируемых телефонных сетях (КТСОП)](upgrade-to-teams-on-prem-pstn-considerations.md)

Кроме того, в следующих статьях описаны важные концепции обновления и поведение сосуществования.

- [Сосуществование Teams и Skype для бизнеса](upgrade-to-teams-on-prem-coexistence.md)
- [Режимы сосуществования — справочные материалы](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>В этих статьях используются условия использования Skype для бизнеса Online, Skype для бизнеса Server и Skype для бизнеса. Последний термин относится как к сети, так и к локальным версиям.

Прежде чем приступить к работе, имейте в виду, что пользователь, который выполнил миграцию в Teams, больше не использует клиент Skype для бизнеса, за исключением присоединения к собранию, размещенному в Skype для бизнеса.  Все входящие разговоры и звонки, находящиеся в клиенте Teams пользователя, независимо от того, использует ли отправитель Teams или Skype для бизнеса. Все новые собрания, упорядоченные из мигрировавших пользователей, будут планироваться как собрания Teams. Если пользователь попытается использовать клиент Skype для бизнеса, инициирование чатов и звонков блокируется.  Тем не менее, пользователь может (и должен) по-прежнему использовать клиент Skype для бизнеса для присоединения к собраниям Skype для бизнеса, на которые они приглашены. (Старые клиенты Skype для бизнеса, которые поставлялись до 2017, не соблюдают TeamsUpgradePolicy. Убедитесь, что вы используете новейшую версию клиента Skype для бизнеса.)
 
Управление переходом пользователя в Teams осуществляется с помощью концепции [mode](migration-interop-guidance-for-teams-with-skype.md), которая является свойством [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Пользователь, который был перенесен в Teams, как описано выше, находится в режиме "TeamsOnly".  Для Организации, которая переносится в Teams, конечная цель состоит в том, чтобы переместить всех пользователей в режим TeamsOnly.

>[!NOTE]
>Пользователи, у которых есть учетная запись в локальной среде Skype для бизнеса, не могут быть TeamsOnly. Несмотря на то что эти пользователи могут [использовать Teams в режиме острова](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), это не предоставляет полный набор функциональных возможностей Teams, доступных в режиме TeamsOnly. Чтобы эти пользователи TeamsOnly, они должны быть перемещены в облако с помощью `Move-CsUser` локальных средств Skype для бизнеса Server.

Хорошо. Приступим!  Первый шаг — общее представление о [доступных вам методах обновления](upgrade-to-teams-on-prem-upgrade-methods.md).







   

## <a name="related-links"></a>Дополнительные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридной связи между Skype для бизнеса Server и Microsoft 365 или Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы миграции собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

