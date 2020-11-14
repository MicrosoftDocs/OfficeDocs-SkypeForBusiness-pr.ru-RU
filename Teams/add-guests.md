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
description: Администраторы могут узнать, как добавлять новых гостевых пользователей в организацию в классическом и веб-клиенте Microsoft Teams, а также на портале для совместной работы Azure Active Directory B2B.
ms.openlocfilehash: 21f8e733a87474888f2b33f8a23a063fa00b4b11
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030815"
---
# <a name="add-a-guest-to-a-team"></a>Добавление гостя в команду

Любой человек с учетной записью электронной почты для организации или пользователя, такой как Outlook, Gmail или другой, может участвовать в Teams в качестве гостя.

Являясь администратором, вы можете добавить нового гостевого пользователя в организацию несколькими способами.

- Глобальные администраторы или администраторы Teams, а также владельцы команд могут добавлять гостей в команду из клиентов Teams или Центра администрирования Teams. Дополнительные сведения см. в статье [Добавление гостей в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Если гостевой доступ еще не настроен, выполните действия, указанные в статье [Совместная работа с гостями в команде](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

- Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory (Azure AD) B2B. Подробности можно найти в разделе [Краткое руководство: Добавление гостевых пользователей в каталог на портале Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

Кроме того, администратор может делегировать разрешения на добавление гостей другому пользователю в организации, назначив ему роль приглашающего гостей. Подробнее см. в статье [Включение внешней совместной работы B2B и управление ролями приглашающих](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).

С помощью службы совместной работы Azure AD B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA). Эти политики можно применять на уровне клиента, приложения или отдельных пользователей точно так же, как для штатных сотрудников и членов организации. Эти политики применяются в ресурсной организации. Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](https://go.microsoft.com/fwlink/?linkid=857454). Отдельных гостевых пользователей блокировать невозможно.

Гостевые пользователи, уже добавленные через Azure AD B2B, группы Microsoft 365 или SharePoint готовы к работе. Администратор Microsoft 365 или владелец группы может добавить этих гостей в соответствующие команды. Если добавить гостя непосредственно в группу Microsoft 365, связанную с группой, гостевой пользователь сможет получить доступ к группе, но в группе Microsoft 365 не будет создаваться приглашение на гость, так что кто-то из участников группы должен уведомлять гостя.

> [!NOTE]
> На гостей распространяются ограничения служб [Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Вы можете отслеживать добавление гостей в Azure AD или Центре безопасности Microsoft 365. Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу). Дополнительные сведения можно найти в разделе [Аудит и создание отчетов о пользователях совместной работы в B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) и [Поиск в журнале аудита в центре соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).


## <a name="related-topics"></a>Статьи по теме

[Авторизация гостевого доступа в Microsoft Teams](teams-dependencies.md)

[Включение и отключение гостевого доступа в Microsoft Teams](set-up-guests.md)
