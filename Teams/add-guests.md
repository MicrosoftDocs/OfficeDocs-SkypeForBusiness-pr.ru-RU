---
title: Добавление гостя в команду
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: Вы можете узнать о доступных администратору средствах для добавления новых гостевых пользователей в организацию, включая классический и веб-клиент Microsoft Teams, а также портал для совместной работы Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: acf62fe23a5b22f2cbe07e94e073037e1f95b041
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236323"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="53e0f-103">Добавление гостя в команду</span><span class="sxs-lookup"><span data-stu-id="53e0f-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="53e0f-104">Любой человек с учетной записью электронной почты для организации или пользователя, такой как Outlook, Gmail или другой, может участвовать в Teams в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="53e0f-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="53e0f-105">Являясь администратором, вы можете добавить нового гостевого пользователя в организацию несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="53e0f-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span>
- <span data-ttu-id="53e0f-106">Владельцы команды или являющиеся ими глобальные администраторы могут добавить гостя в команду с помощью классического или веб-клиента Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="53e0f-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="53e0f-107">Дополнительные сведения см. в статье [Добавление гостей в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="53e0f-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>

> [!NOTE] 
> <span data-ttu-id="53e0f-108">Это не применяется, если включен параметр **Администраторы и пользователи с ролью приглашающего гостей могут приглашать**,</span><span class="sxs-lookup"><span data-stu-id="53e0f-108">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="53e0f-109">так как роль приглашающего гостей не поддерживается в Teams.</span><span class="sxs-lookup"><span data-stu-id="53e0f-109">This is because the guest invitor role isn't supported in Teams.</span></span>

- <span data-ttu-id="53e0f-110">Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory (Azure AD) B2B.</span><span class="sxs-lookup"><span data-stu-id="53e0f-110">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="53e0f-111">Она позволяет глобальному администратору пригласить и авторизовать набор внешних пользователей, отправив на портал совместной работы B2B файл данных с разделителями-запятыми (CSV) длиной не больше 2000 строк.</span><span class="sxs-lookup"><span data-stu-id="53e0f-111">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="53e0f-112">Дополнительные сведения см. в статье [Совместная работа Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="53e0f-112">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="53e0f-113">С помощью службы совместной работы Azure AD B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="53e0f-113">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="53e0f-114">Эти политики можно применять на уровне клиента, приложения или отдельных пользователей точно так же, как для штатных сотрудников и членов организации.</span><span class="sxs-lookup"><span data-stu-id="53e0f-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="53e0f-115">Эти политики применяются в ресурсной организации.</span><span class="sxs-lookup"><span data-stu-id="53e0f-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="53e0f-116">Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="53e0f-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="53e0f-117">Отдельных гостевых пользователей блокировать невозможно.</span><span class="sxs-lookup"><span data-stu-id="53e0f-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="53e0f-118">Гостевые пользователи, добавленные через Azure AD B2B, группы Office 365 или SharePoint Online, готовы к работе.</span><span class="sxs-lookup"><span data-stu-id="53e0f-118">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="53e0f-119">Администратор Office 365 или владелец команды может добавить их в свои команды.</span><span class="sxs-lookup"><span data-stu-id="53e0f-119">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="53e0f-120">Если команда уже имеет группу Office 365, куда добавляется гость, он получит доступ к этой команде.</span><span class="sxs-lookup"><span data-stu-id="53e0f-120">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="53e0f-121">Добавление гостя через группу Office 365 не приводит к отправке ему приглашения по электронной почте, поэтому гостя должен уведомить один из участников команды.</span><span class="sxs-lookup"><span data-stu-id="53e0f-121">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="53e0f-122">На гостей распространяются ограничения служб [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="53e0f-122">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="53e0f-123">Вы можете отслеживать добавление гостей в Azure AD или Центре безопасности и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="53e0f-123">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="53e0f-124">Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу).</span><span class="sxs-lookup"><span data-stu-id="53e0f-124">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="53e0f-125">Дополнительные сведения см. в статьях [Аудит и отчеты для пользователя службы совместной работы B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) и [Поиск журнала аудита в Центре безопасности &amp;и соответствия требованиям Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="53e0f-125">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="53e0f-126">Сравнение гостевого и внешнего доступа (федерация)</span><span class="sxs-lookup"><span data-stu-id="53e0f-126">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="53e0f-127">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="53e0f-127">More information</span></span>

[<span data-ttu-id="53e0f-128">Авторизация гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53e0f-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="53e0f-129">Включение и отключение гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53e0f-129">Turn on or off guest access to Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="53e0f-130">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="53e0f-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
