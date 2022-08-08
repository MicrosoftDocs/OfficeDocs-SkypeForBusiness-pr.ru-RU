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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Из этой статьи вы узнаете, как обновляются приложения Майкрософт, пользовательские приложения и сторонние приложения в Microsoft Teams.
ms.openlocfilehash: bcd06b9814b03d917014d8136f51a280e30007d1
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272064"
---
# <a name="update-apps-in-microsoft-teams"></a>Обновление приложений в Microsoft Teams

В большинстве случаев после публикации обновления приложения разработчиками новая версия автоматически отображается для пользователей. Однако существуют некоторые обновления [манифеста Microsoft Teams](/microsoftteams/platform/resources/schema/manifest-schema), для которых требуется согласие пользователя:

* Добавлен или удален бот.
* Изменено свойство "botId" существующего бота.
* Изменено свойство "isNotificationOnly" существующего бота.
* Добавлены возможности SupportsCalling, SupportsVideo и SupportsFiles бота.
* Добавлено расширение для обмена сообщениями.
* Добавлен новый соединитель.
* Добавлены или изменены разрешения внутри "Авторизации".

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="Доступна новая версия." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Параметр обновления для приложения." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> Процесс обновления действует для всех обновлений приложений Майкрософт, пользовательских приложений и сторонних приложений.
