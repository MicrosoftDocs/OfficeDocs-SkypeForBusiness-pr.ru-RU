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
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="5988f-103">Добавление гостя в команду</span><span class="sxs-lookup"><span data-stu-id="5988f-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="5988f-104">Лица, имеющие business потребитель электронной почты учетной записи или, например, Outlook, Gmail или другим пользователям, могут участвовать в качестве гостя в группах.</span><span class="sxs-lookup"><span data-stu-id="5988f-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="5988f-105">Являясь администратором, вы можете добавить нового гостевого пользователя в организацию несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="5988f-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="5988f-106">Владельцы команды или являющиеся ими глобальные администраторы могут добавить гостя в команду с помощью классического или веб-клиента Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5988f-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="5988f-107">Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory B2B.</span><span class="sxs-lookup"><span data-stu-id="5988f-107">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="5988f-108">Она позволяет глобальному администратору пригласить и авторизовать набор внешних пользователей, отправив на портал совместной работы B2B файл данных с разделителями-запятыми (CSV) длиной не больше 2000 строк.</span><span class="sxs-lookup"><span data-stu-id="5988f-108">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="5988f-109">Дополнительные сведения см. в статье [Совместная работа Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="5988f-109">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="5988f-110">С помощью службы совместной работы Azure Active Directory B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="5988f-110">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="5988f-111">Эти политики можно применить на уровне клиента, приложения или отдельного пользователя, следуя тем же процедурам, что и при задании их для штатных сотрудников и участников организации.</span><span class="sxs-lookup"><span data-stu-id="5988f-111">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="5988f-112">Эти политики применяются в ресурсной организации.</span><span class="sxs-lookup"><span data-stu-id="5988f-112">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="5988f-113">Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="5988f-113">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="5988f-114">Отдельных гостевых пользователей блокировать невозможно.</span><span class="sxs-lookup"><span data-stu-id="5988f-114">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="5988f-115">Гости, которые уже были добавлены с помощью Azure Active Directory B2B, группы Office 365 или SharePoint Online готовы перейти.</span><span class="sxs-lookup"><span data-stu-id="5988f-115">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="5988f-116">Администратор Office 365 или владелец команды может добавить их в свои команды.</span><span class="sxs-lookup"><span data-stu-id="5988f-116">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="5988f-117">Если команда уже имеет группу Office 365, куда добавляется гость, он получит доступ к этой команде.</span><span class="sxs-lookup"><span data-stu-id="5988f-117">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="5988f-118">Добавление гостя через группу Office 365 не приводит к отправке ему приглашения по электронной почте, поэтому гостя должен уведомить один из участников команды.</span><span class="sxs-lookup"><span data-stu-id="5988f-118">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="5988f-119">На гостей распространяются ограничения служб [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="5988f-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="5988f-120">Вы можете отслеживать добавление гостей в Azure Active Directory или Центре безопасности &amp;и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="5988f-120">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="5988f-121">Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу).</span><span class="sxs-lookup"><span data-stu-id="5988f-121">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="5988f-122">Дополнительные сведения см. в статьях [Аудит и отчеты для пользователя службы совместной работы B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) и [Поиск журнала аудита в Центре безопасности &amp;и соответствия требованиям Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="5988f-122">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="5988f-123">Доступ в качестве гостя и внешнего доступа (федерации)</span><span class="sxs-lookup"><span data-stu-id="5988f-123">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="5988f-124">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="5988f-124">More information</span></span>

[<span data-ttu-id="5988f-125">Авторизация гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5988f-125">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="5988f-126">Включение и отключение гостевой доступ в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5988f-126">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="5988f-127">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="5988f-127">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)