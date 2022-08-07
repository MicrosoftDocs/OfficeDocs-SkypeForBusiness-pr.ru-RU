---
title: Управление доступом к приложениям Teams в Microsoft 365
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
description: Узнайте, как управлять доступом к приложениям Teams в Microsoft 365.
ms.openlocfilehash: 114b16dad2a574b217ebc9bf815f42e579b740e8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271414"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Управление доступом к приложениям Teams в Microsoft 365

Разработчики приложений могут улучшить свои приложения Microsoft Teams для работы в Outlook и на Office.com в дополнение к приложению, которое работает в Teams. После улучшения конечные пользователи могут использовать улучшенные приложения в Teams, Microsoft Outlook и на Microsoft Office.com. В настоящее время только конечные пользователи в целевом выпуске могут просматривать и использовать эти определенные приложения в Teams, Outlook и Office.com. Существующий интерфейс администратора Teams применяется для управления доступом к этим приложениям. Уведомление об этом изменении доступно в [центре сообщений](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Как администратор Teams, вы можете разрешить определенным конечным пользователям использовать улучшенные приложения или управлять их доступом к улучшенным приложениям в Teams, Outlook и Office.com. Администраторы Teams используют Центр администрирования Teams для управления доступом к приложениям.

Для использования в Outlook и Office.com улучшенное приложение продолжает использовать существующие разрешения, предоставленные в Teams. Разрешения [улучшенного приложения не изменяются](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Ниже приведен список улучшенных приложений.

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

Вы можете управлять доступом конечных пользователей к приложениям Teams с помощью следующих методов. Если вы являетесь администратором приложений Office, обратитесь к глобальному администратору или администратору Teams, чтобы управлять доступом к приложениям.

| Параметры управления доступом |Портал|Глобальный администратор|Администратор Teams|
|--|---|---|--|
| Только конечные пользователи в целевом выпуске могут получить доступ к новому приложению. Перемещение пользователей в стандартный выпуск. См. раздел [Настройка параметров стандартных или целевых выпусков](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Центр администрирования Microsoft 365 | Да | Нет |
| Управление доступом к новому приложению для определенных конечных пользователей. См. раздел [Добавление настраиваемой политики разрешений](teams-app-permission-policies.md#create-a-custom-app-permission-policy) и [назначение настраиваемой политики пользователю](policy-assignment-overview.md). | Центр администрирования Teams | Да | Да |
| Управление доступом к новым приложениям для всех конечных пользователей в организации. См. раздел [Разрешение или блокировка приложений](manage-apps.md#allow-and-block-apps). | Центр администрирования Teams | Да | Да |

> [!NOTE]
> Для управления доступом конечных пользователей рекомендуется использовать [стандартный выпуск](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true). Другие параметры удаляют доступ пользователей, и они больше не смогут использовать существующее приложение в Teams.

> [!NOTE]
> Пользователи, установившие существующие надстройки того же приложения в Outlook и Office, продолжат использовать это приложение. Надстройки не являются приложениями Teams, и администраторы Teams не могут управлять доступом.

## <a name="see-also"></a>См. также

* [Приложения Microsoft Teams, предназначенные для Microsoft 365, доступны в предварительной версии для Outlook и Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Общие сведения о ролях администраторов в Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Сведения о надстройках Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Как разработчики расширяют возможности приложений Teams для работы в Microsoft 365](/microsoftteams/platform/m365-apps/overview)
