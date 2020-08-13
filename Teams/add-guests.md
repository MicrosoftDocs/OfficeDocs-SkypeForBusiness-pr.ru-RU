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
ms.openlocfilehash: 099e7a0a1fd7368385d564f46e2df12d5aced4b2
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656130"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="cb55c-103">Добавление гостя в команду</span><span class="sxs-lookup"><span data-stu-id="cb55c-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="cb55c-104">Любой человек с учетной записью электронной почты для организации или пользователя, такой как Outlook, Gmail или другой, может участвовать в Teams в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="cb55c-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="cb55c-105">Являясь администратором, вы можете добавить нового гостевого пользователя в организацию несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="cb55c-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="cb55c-106">Глобальные администраторы или администраторы Teams, а также владельцы команд могут добавлять гостей в команду из клиентов Teams или Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="cb55c-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="cb55c-107">Дополнительные сведения см. в статье [Добавление гостей в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="cb55c-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="cb55c-108">Если гостевой доступ еще не настроен, выполните действия, указанные в статье [Контрольный список гостевого доступа](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="cb55c-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="cb55c-109">Это не применяется, если включен параметр **Администраторы и пользователи с ролью приглашающего гостей могут приглашать**,</span><span class="sxs-lookup"><span data-stu-id="cb55c-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="cb55c-110">так как роль приглашающего гостей не поддерживается в Teams.</span><span class="sxs-lookup"><span data-stu-id="cb55c-110">This is because the guest inviter role isn't supported in Teams.</span></span>

- <span data-ttu-id="cb55c-111">Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory (Azure AD) B2B.</span><span class="sxs-lookup"><span data-stu-id="cb55c-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="cb55c-112">Она позволяет глобальному администратору пригласить и авторизовать набор внешних пользователей, отправив на портал совместной работы B2B файл данных с разделителями-запятыми (CSV) длиной не больше 2000 строк.</span><span class="sxs-lookup"><span data-stu-id="cb55c-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="cb55c-113">Дополнительные сведения см. в статье [Совместная работа Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="cb55c-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="cb55c-114">С помощью службы совместной работы Azure AD B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="cb55c-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="cb55c-115">Эти политики можно применять на уровне клиента, приложения или отдельных пользователей точно так же, как для штатных сотрудников и членов организации.</span><span class="sxs-lookup"><span data-stu-id="cb55c-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="cb55c-116">Эти политики применяются в ресурсной организации.</span><span class="sxs-lookup"><span data-stu-id="cb55c-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="cb55c-117">Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="cb55c-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="cb55c-118">Отдельных гостевых пользователей блокировать невозможно.</span><span class="sxs-lookup"><span data-stu-id="cb55c-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="cb55c-119">Гостевые пользователи, добавленные через Azure AD B2B, группы Microsoft 365 или SharePoint Online, готовы к работе.</span><span class="sxs-lookup"><span data-stu-id="cb55c-119">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="cb55c-120">Администратор Microsoft 365 или Office 365 либо владелец команды может добавить их в свои команды.</span><span class="sxs-lookup"><span data-stu-id="cb55c-120">The Microsoft 365 or Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="cb55c-121">Если команда уже имеет группу Microsoft 365, куда добавляется гость, он получит доступ к этой команде.</span><span class="sxs-lookup"><span data-stu-id="cb55c-121">If a team is already with a Microsoft 365 group and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="cb55c-122">Добавление гостя через группу Microsoft 365 не приводит к отправке ему приглашения по электронной почте, поэтому гостя должен уведомить один из участников команды.</span><span class="sxs-lookup"><span data-stu-id="cb55c-122">Adding a guest via the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="cb55c-123">На гостей распространяются ограничения служб [Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="cb55c-123">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="cb55c-124">Вы можете отслеживать добавление гостей в Azure AD или Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb55c-124">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="cb55c-125">Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу).</span><span class="sxs-lookup"><span data-stu-id="cb55c-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="cb55c-126">Дополнительные сведения см. в статьях [Аудит и отчеты для пользователя службы совместной работы B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) и [Поиск по журналу аудита в Центре безопасности Microsoft 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="cb55c-126">For more details, see [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Microsoft 365 security center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="cb55c-127">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="cb55c-127">More information</span></span>

[<span data-ttu-id="cb55c-128">Авторизация гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb55c-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="cb55c-129">Включение и отключение гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb55c-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="cb55c-130">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="cb55c-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
