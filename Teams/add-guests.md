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
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: Администраторы могут узнать, как добавлять новых гостевых пользователей в организацию в классическом и веб-клиенте Microsoft Teams, а также на портале для совместной работы Azure Active Directory B2B.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: baac3c7c7e83547672b8baeb0915081523e5bfe8
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761285"
---
<a name="add-a-guest-to-a-team"></a>Добавление гостя в команду
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Любой человек с учетной записью электронной почты для организации или пользователя, такой как Outlook, Gmail или другой, может участвовать в Teams в качестве гостя.

Являясь администратором, вы можете добавить нового гостевого пользователя в организацию несколькими способами.
- Глобальные администраторы или администраторы Teams, а также владельцы команд могут добавлять гостей в команду из клиентов Teams или Центра администрирования Teams. Дополнительные сведения см. в статье [Добавление гостей в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Если гостевой доступ еще не настроен, выполните действия, указанные в статье [Совместная работа с гостями в команде](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

> [!NOTE] 
> Это не применяется, если включен параметр **Администраторы и пользователи с ролью приглашающего гостей могут приглашать**, так как роль приглашающего гостей не поддерживается в Teams.

- Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory (Azure AD) B2B. Она позволяет глобальному администратору пригласить и авторизовать набор внешних пользователей, отправив на портал совместной работы B2B файл данных с разделителями-запятыми (CSV) длиной не больше 2000 строк. Дополнительные сведения см. в статье [Совместная работа Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).

С помощью службы совместной работы Azure AD B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA). Эти политики можно применять на уровне клиента, приложения или отдельных пользователей точно так же, как для штатных сотрудников и членов организации. Эти политики применяются в ресурсной организации. Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](https://go.microsoft.com/fwlink/?linkid=857454). Отдельных гостевых пользователей блокировать невозможно.

Гостевые пользователи, добавленные через Azure AD B2B, группы Microsoft 365 или SharePoint Online, готовы к работе. Администратор Microsoft 365 или Office 365 либо владелец команды может добавить их в свои команды. Если команда уже имеет группу Microsoft 365, куда добавляется гость, он получит доступ к этой команде. Добавление гостя через группу Microsoft 365 не приводит к отправке ему приглашения по электронной почте, поэтому гостя должен уведомить один из участников команды.

> [!NOTE]
> На гостей распространяются ограничения служб [Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Вы можете отслеживать добавление гостей в Azure AD или Центре безопасности Microsoft 365. Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу). Дополнительные сведения см. в статьях [Аудит и отчеты для пользователя службы совместной работы B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) и [Поиск по журналу аудита в Центре безопасности Microsoft 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).


## <a name="more-information"></a>Дополнительные сведения

[Авторизация гостевого доступа в Microsoft Teams](teams-dependencies.md)</br>
[Включение и отключение гостевого доступа в Microsoft Teams](set-up-guests.md)</br>
[Использование PowerShell для управления гостевым доступом в команде](guest-access-powershell.md)
