---
title: Управление доступом к Teams приложениям в Microsoft 365
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
description: Управляйте доступом к Teams приложениям в Microsoft 365.
ms.openlocfilehash: 981dd4a36cad46085aa7e620ea893f5b62bbaa96
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584324"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Управление доступом к Teams приложениям в Microsoft 365

Разработчики приложений могут обновлять свои Microsoft Teams приложения для работы в Outlook и на сайте Office.com, в дополнение к приложению, которое работает в Teams. Пользователи могут использовать обновленные приложения на Teams, в Microsoft Outlook и Microsoft Office.com после обновления. В настоящее время просматривать и использовать эти приложения на веб-сайте Teams, Outlook и Office.com могут только конечные пользователи в целевом выпуске. Существующий Teams применяется для управления доступом к этим приложениям. Уведомление об этом изменении доступно в [центре сообщений](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Как администратор Teams вы можете разрешить определенным конечным пользователям использовать обновленные приложения или управлять их доступом к обновленным приложениям в Teams, Outlook и на Office.com. Teams администраторы используют центр администрирования Teams для управления доступом к приложениям.

Для использования в Outlook и Office.com в обновленном приложении по-прежнему используются существующие разрешения, предоставленные Teams. Разрешения [обновленного приложения не изменяются](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Вы можете управлять доступом конечных пользователей к приложениям Teams с помощью следующих методов: Если вы администратор Office приложений, обратитесь к глобальному администратору или администратору Teams, чтобы управлять доступом к приложениям.

| Параметры управления доступом |Портал|Глобальный администратор|Teams администратора|
|--|---|---|--|
| Только конечные пользователи в целевом выпуске могут получить доступ к новому приложению. Перемещение пользователей в стандартный выпуск. См[. настройка стандартных или целевых выпусков](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true). | Центр администрирования Microsoft 365 | Да | Нет |
| Управление доступом к новому приложению для определенных пользователей. См [. добавление настраиваемой политики разрешений](teams-app-permission-policies.md#create-a-custom-app-permission-policy) [и назначение настраиваемой политики пользователю](policy-assignment-overview.md). | Teams центре администрирования | Да | Да |
| Управляйте доступом к новым приложениям для всех пользователей в организации. См [. разрешение и блокировка приложений](manage-apps.md#allow-and-block-apps). | Teams центре администрирования | Да | Да |

> [!NOTE]
> Мы рекомендуем использовать [стандартный выпуск для](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) управления доступом конечных пользователей. Другие параметры удаляют доступ конечных пользователей, и они больше не смогут использовать существующее приложение в Teams.

> [!NOTE]
> Пользователи, которые установили существующие надстройки того же приложения в Outlook и Office будут по-прежнему использовать это приложение. Надстройки не являются Teams и Teams не могут управлять доступом.

Ниже приводится список обновленных приложений, которые работают на различных Microsoft 365 surfaces.

* [Фреска](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Surveymonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)

## <a name="see-also"></a>См. также

* [Роли администраторов в Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [О Outlook надстройки](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Как разработчики расширяют Teams приложения для работы в Microsoft 365](/microsoftteams/platform/m365-apps/overview)
