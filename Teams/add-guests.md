---
title: Добавление гостя в команду
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/31/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: Вы можете узнать о доступных администратору средствах для добавления новых гостевых пользователей в организацию, включая классический и веб-клиент Microsoft Teams, а также портал для совместной работы Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9a4418600b3ce6d0da99b8b3f18fba186c8b49f
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706285"
---
<a name="add-a-guest-to-a-team"></a>Добавление гостя в команду
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Лица, имеющие business потребитель электронной почты учетной записи или, например, Outlook, Gmail или другим пользователям, могут участвовать в качестве гостя в группах.

Являясь администратором, вы можете добавить нового гостевого пользователя в организацию несколькими способами. 
- Владельцы команды или являющиеся ими глобальные администраторы могут добавить гостя в команду с помощью классического или веб-клиента Microsoft Teams.
- Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory B2B. Она позволяет глобальному администратору пригласить и авторизовать набор внешних пользователей, отправив на портал совместной работы B2B файл данных с разделителями-запятыми (CSV) длиной не больше 2000 строк. Дополнительные сведения см. в статье [Совместная работа Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).

С помощью службы совместной работы Azure Active Directory B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA). Эти политики можно применить на уровне клиента, приложения или отдельного пользователя, следуя тем же процедурам, что и при задании их для штатных сотрудников и участников организации. Эти политики применяются в ресурсной организации. Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](https://go.microsoft.com/fwlink/?linkid=857454). Отдельных гостевых пользователей блокировать невозможно.

Гости, которые уже были добавлены с помощью Azure Active Directory B2B, группы Office 365 или SharePoint Online готовы перейти. Администратор Office 365 или владелец команды может добавить их в свои команды. Если команда уже имеет группу Office 365, куда добавляется гость, он получит доступ к этой команде. Добавление гостя через группу Office 365 не приводит к отправке ему приглашения по электронной почте, поэтому гостя должен уведомить один из участников команды.

> [!NOTE]
> На гостей распространяются ограничения служб [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Вы можете отслеживать добавление гостей в Azure Active Directory или Центре безопасности &amp;и соответствия требованиям Office 365. Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу). Дополнительные сведения см. в статьях [Аудит и отчеты для пользователя службы совместной работы B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) и [Поиск журнала аудита в Центре безопасности &amp;и соответствия требованиям Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="guest-access-vs-external-access-federation"></a>Доступ в качестве гостя и внешнего доступа (федерации)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Дополнительная информация

[Авторизация гостевого доступа в Microsoft Teams](teams-dependencies.md)</br>
[Включение и отключение гостевой доступ в группах Майкрософт](set-up-guests.md)</br>
[Использование PowerShell для управления гостевым доступом в команде](guest-access-powershell.md)