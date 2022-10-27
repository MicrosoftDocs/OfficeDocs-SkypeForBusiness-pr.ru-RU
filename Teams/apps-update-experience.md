---
title: Интерфейс обновления приложений в Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Из этой статьи вы узнаете, как обновляются приложения Майкрософт, пользовательские приложения и сторонние приложения в Microsoft Teams и как администраторы способствуют этому.
ms.openlocfilehash: 0f5631abcd773f09c5a926bf3459d56e8f9f92bf
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738615"
---
# <a name="teams-app-updates-and-admin-role"></a>Обновления приложений Teams и роль администратора

Администраторы Teams могут помочь конечным пользователям получить последнюю версию приложений. Для этого они выполняют одну или обе из следующих задач:

* [Обновите сторонние приложения](#updates-to-third-party-apps) , доступные в магазине Teams, когда разработчик или поставщик предоставляет новую версию приложения.
* [Обновите пользовательские приложения](#updates-to-custom-apps) , доступные только в вашей организации, когда разработчик отправляет новую версию.

## <a name="updates-to-third-party-apps"></a>Обновления к сторонним приложениям

Чтобы пользователи устанавливали и использовали приложение, они должны предоставить приложению разрешения на доступ к необходимым службам и сведениям. В большинстве случаев, когда новая версия установленного приложения доступна в магазине Teams, приложение автоматически обновляется для всех пользователей. Однако для некоторых конкретных изменений в новой версии приложения требуется повторное разрешение пользователя. Это повторное принятие пользователем гарантирует осведомленность об изменениях, таких как функциональные возможности или доступ к личной информации. Администраторы Teams могут [предоставлять разрешения приложению от имени пользователей](app-permissions-admin-center.md).

Если разработчики приложений вносят одно или несколько следующих изменений в свои приложения, пользователи должны утвердить обновление приложения.

* Добавьте бота. Измените идентификатор бота с помощью `botId` свойства .
* Измените `isNotificationOnly` свойство существующего бота, которое может изменить уведомления бота.
* Измените `SupportsCalling`свойства , `SupportsVideo`и `SupportsFiles` существующего бота, чтобы добавить возможность вызова, воспроизведения видео, а также отправки или скачивания файлов.
* Добавление или удаление разрешений в авторизации.
* Добавьте или удалите расширение для обмена сообщениями, добавьте вкладку группы, добавьте соединитель или добавьте канал.
* Измените [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) параметры в файле манифеста.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Обновления пользовательских приложений

Пользовательские приложения, созданные и развернутые в организации, доступны пользователям в вашем клиенте или организации. Администратор Teams обновляет пользовательские приложения до новых версий, предоставляемых разработчиками в организации. Дополнительные сведения см. в статье о [том, как администраторы управляют пользовательскими приложениями](custom-app-overview.md).

## <a name="related-article"></a>Связанная статья

* [Базовые сведения о схеме манифеста для обновлений, выполненных в приложениях.](/microsoftteams/platform/resources/schema/manifest-schema).
* [Узнайте о пользовательском управлении приложениями](custom-app-overview.md).
