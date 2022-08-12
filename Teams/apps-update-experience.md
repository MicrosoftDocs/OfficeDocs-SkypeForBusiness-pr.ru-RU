---
title: Интерфейс обновления приложений в Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Из этой статьи вы узнаете, как обновляются приложения Майкрософт, пользовательские приложения и сторонние приложения в Microsoft Teams и как администраторы способствуют этому.
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299048"
---
# <a name="update-apps-in-microsoft-teams"></a>Обновление приложений в Microsoft Teams

В большинстве случаев после появления новой версии приложения в магазине Teams оно автоматически обновляется для пользователей. Однако некоторые конкретные изменения в новой версии приложения требуют согласия пользователя для обновления приложения. Согласие пользователя обеспечивает осведомленность об изменениях, таких как функциональность или доступ. Если разработчики приложений внести следующие изменения в приложения Microsoft Teams, конечные пользователи должны одобрить обновление приложения:

* Бот добавлен.
* Изменено свойство `botId` или свойство `isNotificationOnly` существующего бота.
* Добавлены возможности бота `SupportsCalling`, `SupportsVideo` и `SupportsFiles`.
* Добавлено расширение для обмена сообщениями.
* Добавлены или изменены разрешения внутри "Авторизации".
* `Id` или `ApplicationPermissionsHash`, или и то и другое изменены в `webApplicationInfo`.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>Статьи по теме

* [Базовые сведения о схеме манифеста для обновлений, выполненных в приложениях.](/microsoftteams/platform/resources/schema/manifest-schema).
