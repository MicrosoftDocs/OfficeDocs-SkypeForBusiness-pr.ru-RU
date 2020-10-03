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
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Администраторы могут узнать, как добавлять новых гостевых пользователей в организацию в классическом и веб-клиенте Microsoft Teams, а также на портале для совместной работы Azure Active Directory B2B.
ms.openlocfilehash: e74819ba46af8a9f6bcf3b2198f78354bf7bfb79
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346180"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="2f74d-103">Добавление гостя в команду</span><span class="sxs-lookup"><span data-stu-id="2f74d-103">Add a guest to a team</span></span>

<span data-ttu-id="2f74d-104">Любой человек с учетной записью электронной почты для организации или пользователя, такой как Outlook, Gmail или другой, может участвовать в Teams в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="2f74d-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="2f74d-105">Являясь администратором, вы можете добавить нового гостевого пользователя в организацию несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="2f74d-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>

- <span data-ttu-id="2f74d-106">Глобальные администраторы или администраторы Teams, а также владельцы команд могут добавлять гостей в команду из клиентов Teams или Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="2f74d-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="2f74d-107">Дополнительные сведения см. в статье [Добавление гостей в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="2f74d-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="2f74d-108">Если гостевой доступ еще не настроен, выполните действия, указанные в статье [Совместная работа с гостями в команде](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="2f74d-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="2f74d-109">Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory (Azure AD) B2B.</span><span class="sxs-lookup"><span data-stu-id="2f74d-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="2f74d-110">Подробности можно найти в разделе [Краткое руководство: Добавление гостевых пользователей в каталог на портале Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="2f74d-110">For details, check out [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="2f74d-111">Кроме того, администратор может делегировать разрешения на добавление гостей другому пользователю в организации, назначив ему роль приглашающего гостей.</span><span class="sxs-lookup"><span data-stu-id="2f74d-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="2f74d-112">Подробнее см. в статье [Включение внешней совместной работы B2B и управление ролями приглашающих](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="2f74d-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="2f74d-113">С помощью службы совместной работы Azure AD B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="2f74d-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="2f74d-114">Эти политики можно применять на уровне клиента, приложения или отдельных пользователей точно так же, как для штатных сотрудников и членов организации.</span><span class="sxs-lookup"><span data-stu-id="2f74d-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="2f74d-115">Эти политики применяются в ресурсной организации.</span><span class="sxs-lookup"><span data-stu-id="2f74d-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="2f74d-116">Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="2f74d-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="2f74d-117">Отдельных гостевых пользователей блокировать невозможно.</span><span class="sxs-lookup"><span data-stu-id="2f74d-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="2f74d-118">Гостевые пользователи, уже добавленные через Azure AD B2B, группы Microsoft 365 или SharePoint готовы к работе.</span><span class="sxs-lookup"><span data-stu-id="2f74d-118">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="2f74d-119">Администратор Microsoft 365 или владелец группы может добавить этих гостей в соответствующие команды.</span><span class="sxs-lookup"><span data-stu-id="2f74d-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="2f74d-120">Если добавить гостя непосредственно в группу Microsoft 365, связанную с группой, гостевой пользователь сможет получить доступ к группе, но в группе Microsoft 365 не будет создаваться приглашение на гость, так что кто-то из участников группы должен уведомлять гостя.</span><span class="sxs-lookup"><span data-stu-id="2f74d-120">If add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="2f74d-121">На гостей распространяются ограничения служб [Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="2f74d-121">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="2f74d-122">Вы можете отслеживать добавление гостей в Azure AD или Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f74d-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="2f74d-123">Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу).</span><span class="sxs-lookup"><span data-stu-id="2f74d-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="2f74d-124">Дополнительные сведения можно найти в разделе [Аудит и создание отчетов о пользователях совместной работы в B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) и [Поиск в журнале аудита в центре соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span><span class="sxs-lookup"><span data-stu-id="2f74d-124">For more details, see [Auditing and reporting a B2B collaboration user](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="2f74d-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2f74d-125">Related topics</span></span>

[<span data-ttu-id="2f74d-126">Авторизация гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f74d-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="2f74d-127">Включение и отключение гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f74d-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)
