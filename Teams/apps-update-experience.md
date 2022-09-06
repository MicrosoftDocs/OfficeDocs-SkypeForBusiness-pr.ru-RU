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
ms.openlocfilehash: b947e8b77bc167ccbdfb6a90bfa7c4ab96476efc
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606098"
---
# <a name="teams-app-updates-and-admin-role"></a>Обновления приложений Teams и роль администратора

Администраторы Teams могут помочь конечным пользователям получить последнюю версию приложений. Для этого они выполняют одну или обе из следующих задач:

* [Обновите сторонние приложения](#updates-to-third-party-apps) , доступные в Магазине Teams, когда разработчик или поставщик приложений предоставляет новую версию.
* [Обновите пользовательские](#updates-to-custom-apps) приложения, доступные только в вашей организации, когда разработчик отправляет новую версию.

## <a name="updates-to-third-party-apps"></a>Обновления приложениям сторонних производителей

Чтобы пользователи могли установить и использовать приложение, они должны предоставить приложению разрешения на доступ к необходимым службам и информации. В большинстве случаев, когда в магазине Teams доступна новая версия установленного приложения, приложение автоматически обновляется для всех пользователей. Однако для некоторых определенных изменений в новой версии приложения требуется повторное разрешение пользователя. Такое повторное принятие пользователем условий гарантирует осведомленность об изменениях, таких как функциональные возможности или доступ к личной информации. Администраторы Teams [могут предоставлять разрешения приложению от имени пользователей](app-permissions-admin-center.md).

Если разработчики приложений внесите одно или несколько следующих изменений в свои приложения, конечные пользователи должны утвердить обновление приложения.

* Добавление или удаление бота. Измените идентификатор бота с помощью свойства `botId` .
* Измените `isNotificationOnly` свойство существующего бота, которое может изменить уведомления бота.
* Измените `SupportsCalling`, `SupportsVideo`и свойства `SupportsFiles` существующего бота, чтобы добавить возможность вызова, воспроизведения видео, а также отправки или скачивания файлов.
* Добавление или удаление разрешений в авторизации.
* Добавление или удаление расширения для обмена сообщениями, добавление вкладки группы, добавление соединителя или добавление канала.
* Измените параметры в файле [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) манифеста.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>Обновления в пользовательские приложения

Пользовательские приложения, созданные и развернутые в организации, доступны пользователям в клиенте или организации. Администратор Teams обновляет пользовательские приложения до новых версий, предоставляемых разработчиками в организации. Дополнительные сведения см. [в статье об управлении пользовательскими приложениями администраторами](custom-app-overview.md).

## <a name="related-article"></a>Связанная статья

* [Базовые сведения о схеме манифеста для обновлений, выполненных в приложениях.](/microsoftteams/platform/resources/schema/manifest-schema).
* [Сведения о пользовательском управлении приложениями](custom-app-overview.md).
