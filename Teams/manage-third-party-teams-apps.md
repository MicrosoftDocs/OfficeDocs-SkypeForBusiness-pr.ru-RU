---
title: Управление доступом к приложениям Teams в Microsoft 365
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/24/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Узнайте, как управлять доступом к приложениям Teams в Microsoft 365.
ms.openlocfilehash: ae11a72324bb4382012c751150a254773c9145b7
ms.sourcegitcommit: c627bd1df17aefdc353bc4da6db169dfe169031e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2022
ms.locfileid: "68680560"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Управление доступом к приложениям Teams в Microsoft 365

Разработчики приложений могут улучшить свои приложения Microsoft Teams для работы в Outlook и на Office.com в дополнение к приложению, которое работает в Teams. После улучшения конечные пользователи могут использовать улучшенные приложения в Teams, Microsoft Outlook и на Microsoft Office.com. В настоящее время только конечные пользователи в [целевом выпуске](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) могут просматривать и использовать эти приложения в Teams, Outlook и Office.com. Уведомление об этом изменении доступно в [центре сообщений](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280).

## <a name="manage-the-enhanced-apps-access-microsoft-365"></a>Управление доступом к расширенным приложениям Microsoft 365

Существующий интерфейс администратора Teams применяется для управления доступом к этим приложениям. Администраторы Teams используют Центр администрирования Teams для управления доступом к приложениям. Как администратор Teams, вы можете разрешить определенным конечным пользователям использовать улучшенные приложения или управлять их доступом к улучшенным приложениям в Teams, Outlook и Office.com.

Для использования в Outlook и Office.com улучшенное приложение продолжает использовать существующие разрешения, предоставленные в Teams. Разрешения расширенного приложения не изменяются. Пользователи, установившие существующие на рынке надстройки того же приложения в Outlook и Office, будут продолжать использовать это приложение. Надстройки не являются приложениями Teams, и администраторы Teams не могут управлять доступом.

Администраторы Office Apps могут обратиться к глобальному администратору или администратору Teams для управления доступом к расширенным приложениям. Дополнительные сведения см [. в статье Роли администратора в Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true).

Вы можете управлять доступом конечных пользователей с помощью следующих методов.

| Параметры управления доступом |Портал|Глобальный администратор|Администратор Teams|
|--|---|---|--|
| Только конечные пользователи в целевом выпуске могут получить доступ к новому приложению. Перемещение пользователей в стандартный выпуск. См. раздел [Настройка параметров стандартных или целевых выпусков](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Центр администрирования Microsoft 365 | Да | Нет |
| Управление доступом к новому приложению для определенных конечных пользователей. См. раздел [Добавление настраиваемой политики разрешений](teams-app-permission-policies.md#create-an-app-permission-policy) и [назначение настраиваемой политики пользователю](policy-assignment-overview.md). | Центр администрирования Teams | Да | Да |
| Управление доступом к новым приложениям для всех конечных пользователей в организации. См. раздел [Разрешение или блокировка приложений](manage-apps.md#allow-and-block-apps). | Центр администрирования Teams | Да | Да |

> [!NOTE]
> Для управления доступом конечных пользователей рекомендуется использовать [стандартный выпуск](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true). Другие параметры удаляют доступ пользователей, и они больше не смогут использовать существующее приложение в Teams.

## <a name="list-of-enhanced-apps"></a>Список расширенных приложений

Ниже приведен список расширенных приложений:

* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)
* [Большие мозги eLearning](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [e2e-assure](https://teams.microsoft.com/l/app/8bdf3437-e038-4a93-abdc-00461630f6c3?source=app-details-dialog)
* [ESi-Tik](https://teams.microsoft.com/l/app/fe9627db-f23e-42b1-b454-d4d1ca5af33e?source=app-details-dialog)
* [Объектив](https://teams.microsoft.com/l/app/cfaeb687-adc7-4e36-a847-39bb35bfb631?source=app-details-dialog)
* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Мои наклейки](https://teams.microsoft.com/l/app/46fae4d0-faf5-11e9-80f3-53ad33b77bce?source=app-details-dialog)
* [Инструменты PDF](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [Priority Matrix](https://teams.microsoft.com/l/app/5be2b320-a5b7-4221-893c-dee506e4e365?source=app-details-dialog)
* [Smart Connect для Jira](https://teams.microsoft.com/l/app/6402de97-ce33-4386-bf28-b37e9e139c09?source=app-details-dialog)
* [Планирование в ближайшее время](https://teams.microsoft.com/l/app/bf280b0d-b87d-4158-9f2a-70b63674cd27?source=app-details-dialog)
* [Оптимизация](https://teams.microsoft.com/l/app/aa6e7fb6-34ac-4947-9c13-3565c66e368b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Помощник по транскрибированию TNA2](https://teams.microsoft.com/l/app/32c31ccd-b878-470e-9259-98c079ae5528?source=app-details-dialog)
* [Умбико](https://teams.microsoft.com/l/app/23fc1de6-dda0-4043-9ebb-a555e845843d?source=app-details-dialog)
* [Уолдо](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)

## <a name="related-articles"></a>Статьи по теме

* [Приложения Microsoft Teams, предназначенные для Microsoft 365, доступны в предварительной версии для Outlook и Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Общие сведения о ролях администраторов в Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Сведения о надстройках Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Как разработчики расширяют возможности приложений Teams для работы в Microsoft 365](/microsoftteams/platform/m365-apps/overview)
