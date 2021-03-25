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
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="dd33e-103">Добавление гостя в команду</span><span class="sxs-lookup"><span data-stu-id="dd33e-103">Add a guest to a team</span></span>

<span data-ttu-id="dd33e-104">Любой человек с учетной записью электронной почты для организации или пользователя, такой как Outlook, Gmail или другой, может участвовать в Teams в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="dd33e-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="dd33e-105">Как администратор вы можете добавить нового гостя в организацию несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="dd33e-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="dd33e-106">Глобальные администраторы или администраторы Teams, а также владельцы команд могут добавлять гостей в команду из клиентов Teams или Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="dd33e-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="dd33e-107">Дополнительные сведения см. в статье [Добавление гостей в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="dd33e-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="dd33e-108">Если гостевой доступ еще не настроен, выполните действия, указанные в статье [Совместная работа с гостями в команде](/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="dd33e-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="dd33e-109">Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory (Azure AD) B2B.</span><span class="sxs-lookup"><span data-stu-id="dd33e-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="dd33e-110">Дополнительные сведения можно найти [в кратком кратком видео: добавление](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)гостей в каталог на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="dd33e-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="dd33e-111">Кроме того, администратор может делегировать разрешения на добавление гостей другому пользователю в организации, назначив ему роль приглашающего гостей.</span><span class="sxs-lookup"><span data-stu-id="dd33e-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="dd33e-112">Подробнее см. в статье [Включение внешней совместной работы B2B и управление ролями приглашающих](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="dd33e-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="dd33e-113">С помощью службы совместной работы Azure AD B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="dd33e-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="dd33e-114">Эти политики можно применять на уровне клиента, приложения или отдельных пользователей точно так же, как для штатных сотрудников и членов организации.</span><span class="sxs-lookup"><span data-stu-id="dd33e-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="dd33e-115">Эти политики применяются в ресурсной организации.</span><span class="sxs-lookup"><span data-stu-id="dd33e-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="dd33e-116">Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](/azure/active-directory/external-identities/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="dd33e-116">For more information, see  [Conditional access for B2B collaboration users](/azure/active-directory/external-identities/conditional-access).</span></span> <span data-ttu-id="dd33e-117">Отдельных гостей нельзя заблокировать.</span><span class="sxs-lookup"><span data-stu-id="dd33e-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="dd33e-118">Гости, которые вы уже добавили через Azure AD B2B, Группы Microsoft 365 или SharePoint, готовы к добавлению.</span><span class="sxs-lookup"><span data-stu-id="dd33e-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="dd33e-119">Администратор Microsoft 365 или владелец команды может добавить таких гостей в свои команды.</span><span class="sxs-lookup"><span data-stu-id="dd33e-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="dd33e-120">Если вы добавляете гостя непосредственно в группу Microsoft 365, связанную с командой, он получает доступ к команде, но группа Microsoft 365 не создает ему сообщение с приглашением, поэтому кто-то из команды должен уведомить гостя.</span><span class="sxs-lookup"><span data-stu-id="dd33e-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="dd33e-121">На гостей распространяются ограничения служб [Microsoft 365 или Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) и [Azure Active Directory](/azure/active-directory/external-identities/current-limitations).</span><span class="sxs-lookup"><span data-stu-id="dd33e-121">Guests are subject to  [Microsoft 365 or Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) and [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) service limits.</span></span>

<span data-ttu-id="dd33e-122">Вы можете отслеживать добавление гостей в Azure AD или Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd33e-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="dd33e-123">Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу).</span><span class="sxs-lookup"><span data-stu-id="dd33e-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="dd33e-124">Дополнительные сведения см. в записях аудита и отчетности для пользователей совместной работы [B2B,](/azure/active-directory/external-identities/auditing-and-reporting) а также в журнале аудита [в Центре соответствия требованиям.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="dd33e-124">For more details, see [Auditing and reporting a B2B collaboration user](/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="dd33e-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dd33e-125">Related topics</span></span>

[<span data-ttu-id="dd33e-126">Авторизация гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd33e-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="dd33e-127">Включение и отключение гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd33e-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)