---
title: Интерфейс обновления приложений в Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Из этой статьи вы узнаете, как обновляются приложения Майкрософт, пользовательские приложения и сторонние приложения в Microsoft Teams.
ms.openlocfilehash: 27d51a487af918e6fcee2b7806c81d31506bd1af
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958044"
---
# <a name="update-apps-in-microsoft-teams"></a>Обновление приложений в Microsoft Teams

В большинстве случаев после того, как разработчики приложений опубликует обновление приложения, для пользователей автоматически появится новая версия. Однако существуют некоторые обновления манифеста [Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema) , которые требуют принятия пользователем условий.

* Бот был добавлен или удален.
* Изменено свойство botId существующего бота.
* Изменено свойство isNotificationOnly существующего бота.
* Добавлены возможности SupportsCalling, SupportsVideo и SupportsFiles бота.
* Добавлено расширение для обмена сообщениями.
* Добавлен новый соединитель.
* Разрешения внутри "Авторизация" были добавлены или изменены.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Доступна новая версия." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Параметр обновления для приложения." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> Процесс обновления применяется ко всем обновлениям приложений Майкрософт, пользовательских приложений и сторонних приложений.
