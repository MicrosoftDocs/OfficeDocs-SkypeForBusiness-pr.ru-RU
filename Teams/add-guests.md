---
title: Добавление гостя в команду
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Администраторы могут узнать, как добавлять новых гостей в организацию в классических и веб-клиентах Microsoft Teams и на портале совместной работы Azure Active Directory B2B.
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109085"
---
# <a name="add-a-guest-to-a-team"></a>Добавление гостя в команду

Любой человек с учетной записью электронной почты для организации или пользователя, такой как Outlook, Gmail или другой, может участвовать в Teams в качестве гостя.

Как администратор вы можете добавить нового гостя в организацию несколькими способами:

- Глобальные администраторы или администраторы Teams, а также владельцы команд могут добавлять гостей в команду из клиентов Teams или Центра администрирования Teams. Дополнительные сведения см. в статье [Добавление гостей в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Если гостевой доступ еще не настроен, выполните действия, указанные в статье [Совместная работа с гостями в команде](/microsoft-365/solutions/collaborate-as-team).

- Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory (Azure AD) B2B. Дополнительные сведения можно найти [в кратком кратком видео: добавление](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)гостей в каталог на портале Azure.

Кроме того, администратор может делегировать разрешения на добавление гостей другому пользователю в организации, назначив ему роль приглашающего гостей. Подробнее см. в статье [Включение внешней совместной работы B2B и управление ролями приглашающих](/azure/active-directory/external-identities/delegate-invitations).

С помощью службы совместной работы Azure AD B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA). Эти политики можно применять на уровне клиента, приложения или отдельных пользователей точно так же, как для штатных сотрудников и членов организации. Эти политики применяются в ресурсной организации. Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](/azure/active-directory/external-identities/conditional-access). Отдельных гостей нельзя заблокировать.

Гости, которые вы уже добавили через Azure AD B2B, Группы Microsoft 365 или SharePoint, готовы к добавлению. Администратор Microsoft 365 или владелец команды может добавить таких гостей в свои команды. Если вы добавляете гостя непосредственно в группу Microsoft 365, связанную с командой, он получает доступ к команде, но группа Microsoft 365 не создает ему сообщение с приглашением, поэтому кто-то из команды должен уведомить гостя.

> [!NOTE]
> На гостей распространяются ограничения служб [Microsoft 365 или Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) и [Azure Active Directory](/azure/active-directory/external-identities/current-limitations).

Вы можете отслеживать добавление гостей в Azure AD или Центре безопасности Microsoft 365. Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу). Дополнительные сведения см. в записях аудита и отчетности для пользователей совместной работы [B2B,](/azure/active-directory/external-identities/auditing-and-reporting) а также в журнале аудита [в Центре соответствия требованиям.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)


## <a name="related-topics"></a>Статьи по теме

[Авторизация гостевого доступа в Microsoft Teams](teams-dependencies.md)

[Включение и отключение гостевого доступа в Microsoft Teams](set-up-guests.md)