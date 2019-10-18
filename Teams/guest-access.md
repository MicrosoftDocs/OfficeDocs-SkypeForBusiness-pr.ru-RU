---
title: Гостевой доступ в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1787d2f310ebf7ed0afafa41e8b730346a54ec
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37565109"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="385d5-103">Гостевой доступ в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="385d5-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="385d5-104">Гостевой доступ — это функция, о которой особенно часто просили наши клиенты.</span><span class="sxs-lookup"><span data-stu-id="385d5-104">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="385d5-105">Вы можете отслеживать наш ход работы над гостевым доступом и сообщать свое мнение.</span><span class="sxs-lookup"><span data-stu-id="385d5-105">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="385d5-106">Если у вас возникают проблемы с гостевым доступом, см. раздел [Известные проблемы для Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="385d5-106">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="385d5-107">Узнавайте о новых и усовершенствованных функциях из [Стратегии развития Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="385d5-107">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="385d5-108">Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="385d5-108">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="385d5-109">Поделитесь своим опытом в разделе комментариев ниже.</span><span class="sxs-lookup"><span data-stu-id="385d5-109">Share your experience in the Comments section below.</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="385d5-110">Обзор гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="385d5-110">Guest access overview</span></span>

<span data-ttu-id="385d5-111">Гостевой доступ позволяет командам в вашей организации взаимодействовать с людьми, находящимися за пределами организации, предоставляя им доступ к существующим командам и каналам одного или нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="385d5-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="385d5-112">Любой пользователь с корпоративной или потребительской учетной записью Outlook, Gmail или других служб может участвовать в Teams в качестве гостя с полным доступом к командным чатам, собраниям и файлам.</span><span class="sxs-lookup"><span data-stu-id="385d5-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="385d5-113">Гостевой доступ предоставляется вместе со многими вариантами подписки на Office 365 без дополнительных условий лицензирования.</span><span class="sxs-lookup"><span data-stu-id="385d5-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="385d5-114">Дополнительные сведения о лицензировании см. в статье [Руководство по лицензированию службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="385d5-114">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="385d5-115">Гостевой доступ в Microsoft Teams настраивается на уровне клиента и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="385d5-115">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="385d5-116">На гостевой доступ распространяются ограничения служб Azure AD и Office 365.</span><span class="sxs-lookup"><span data-stu-id="385d5-116">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="385d5-117">Пользователей из вашей организации, у которых есть только отдельные планы подписки на Office 365, например на Exchange Online (план 2), нельзя пригласить в качестве гостей в организацию, так как Teams считает, что они относятся к одной организации.</span><span class="sxs-lookup"><span data-stu-id="385d5-117">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="385d5-118">Чтобы использовать Teams для этих пользователей, им должна быть назначена подписка на Office 365 бизнес премиум, Office 365 корпоративный или Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="385d5-118">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="385d5-119">Кто такой гость?</span><span class="sxs-lookup"><span data-stu-id="385d5-119">Who is a guest?</span></span>

<span data-ttu-id="385d5-120">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="385d5-120">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="385d5-121">У него нет учебной или рабочей учетной записи, предоставленной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="385d5-121">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="385d5-122">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="385d5-122">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="385d5-123">Любого пользователя, не состоящего в вашей организации, можно добавить в качестве гостя в Teams.</span><span class="sxs-lookup"><span data-stu-id="385d5-123">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="385d5-124">Это означает, что любой пользователь с корпоративной учетной записью (т. е. учетной записью Azure Active Directory) или потребительской учетной записью электронной почты (Outlook.com, Gmail.com или других служб) может участвовать в Teams в качестве гостя с полным доступом к возможностям команд и каналов.</span><span class="sxs-lookup"><span data-stu-id="385d5-124">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="385d5-125">(Сведения об ограничениях для гостей см. в статье [Авторизация гостевого доступа в Microsoft Teams](teams-dependencies.md).) Для всех гостей в Teams применяется та же защита на базе соответствия и аудита, что и для остальной части Office 365, кроме того, ими можно безопасно управлять в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="385d5-125">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="385d5-126">Для чего нужен гостевой доступ?</span><span class="sxs-lookup"><span data-stu-id="385d5-126">Why use guest access?</span></span>

<span data-ttu-id="385d5-127">С помощью гостевого доступа организации, использующие Teams, могут предоставлять своим партнерам внешний доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя полный контроль над своими корпоративными данными.</span><span class="sxs-lookup"><span data-stu-id="385d5-127">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="385d5-128">Для всех гостей в Teams применяется та же защита на базе соответствия и аудита, что и для остальной части Office 365, кроме того, гостями можно безопасно управлять в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="385d5-128">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="385d5-129">Продукт Teams основан на Группах Office 365 и предоставляет новый способ доступа к общим ресурсам для группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="385d5-129">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="385d5-130">Teams является оптимальным решением для сохраняемого чата между участниками группы или команды.</span><span class="sxs-lookup"><span data-stu-id="385d5-130">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="385d5-131">Группы Office 365 — это служба, предоставляющая членство на несколько приложений для набора общих ресурсов команды, таких как сайт SharePoint или панель мониторинга Power BI, чтобы обеспечить эффективную и безопасную работу команды.</span><span class="sxs-lookup"><span data-stu-id="385d5-131">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="385d5-132">Чем гостевой доступ отличается от внешнего доступа (федерации)?</span><span class="sxs-lookup"><span data-stu-id="385d5-132">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="385d5-133">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="385d5-133">More information</span></span>

[<span data-ttu-id="385d5-134">Обращение в службу поддержки продуктов для бизнеса. Справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="385d5-134">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="385d5-135">Гостевой доступ в группах Office 365</span><span class="sxs-lookup"><span data-stu-id="385d5-135">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
