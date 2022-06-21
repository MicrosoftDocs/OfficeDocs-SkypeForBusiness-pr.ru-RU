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
description: Узнайте, как управлять доступом к Teams приложениям в Microsoft 365.
ms.openlocfilehash: 34587bd02f9fddb73bce8e159b9df317b3bc619a
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190611"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Управление доступом к Teams приложениям в Microsoft 365

Разработчики приложений могут улучшить свои Microsoft Teams приложения для работы в Outlook и на Office.com, в дополнение к приложению, которое работает в Teams. Конечные пользователи могут использовать расширенные приложения на Teams, в Microsoft Outlook и Microsoft Office.com после улучшения. В настоящее время только конечные пользователи в целевом выпуске могут просматривать и использовать эти приложения в Teams, Outlook и Office.com. Существующий Teams администратора применяется для управления доступом к этим приложениям. Уведомление об этом изменении доступно в [центре сообщений](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Как администратор Teams вы можете разрешить определенным конечным пользователям использовать расширенные приложения или управлять их доступом к расширенным приложениям в Teams, Outlook и на Office.com. Teams администраторы используют центр администрирования Teams для управления доступом к приложениям.

Для использования в Outlook и Office.com расширенное приложение продолжает использовать существующие разрешения, предоставленные в Teams. Разрешения [расширенного приложения не изменяются](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Ниже приведен список расширенных приложений.

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Фреска](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

Вы можете управлять доступом конечных пользователей к приложениям Teams с помощью следующих методов. Если вы являетесь администратором Office приложений, обратитесь к глобальному администратору или Teams администратору, чтобы управлять доступом к приложениям.

| Параметры управления доступом |Портал|Глобальный администратор|Teams администратора|
|--|---|---|--|
| Только конечные пользователи в целевом выпуске могут получить доступ к новому приложению. Перемещение пользователей в стандартный выпуск. См [. раздел "Настройка стандартных или целевых выпусков"](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Центр администрирования Microsoft 365 | Да | Нет |
| Управление доступом к новому приложению для определенных конечных пользователей. См [. раздел "Добавление настраиваемой политики разрешений](teams-app-permission-policies.md#create-a-custom-app-permission-policy) и [назначение настраиваемой политики пользователю"](policy-assignment-overview.md). | Центр администрирования Teams | Да | Да |
| Управление доступом к новым приложениям для всех конечных пользователей в организации. См [. раздел "Разрешить или заблокировать приложения"](manage-apps.md#allow-and-block-apps). | Центр администрирования Teams | Да | Да |

> [!NOTE]
> Для управления [доступом](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) конечных пользователей рекомендуется использовать стандартный выпуск. Другие параметры удаляют доступ пользователей, и они больше не смогут использовать существующее приложение в Teams.

> [!NOTE]
> Пользователи, которые установили существующие на рынке надстройки того же приложения в Outlook и Office будут продолжать использовать это приложение. Надстройки не являются Teams и Teams администраторы не могут управлять доступом.

## <a name="see-also"></a>См. также

* [Microsoft Teams приложения, предназначенные для Microsoft 365 предварительной версии, Outlook и Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Общие сведения о ролях администраторов в Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Сведения Outlook надстройки](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Как разработчики расширяют Teams приложения для работы в Microsoft 365](/microsoftteams/platform/m365-apps/overview)
