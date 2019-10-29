---
title: Гостевой доступ в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
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
ms.openlocfilehash: 7a0bba0c8893ee706061b989f95d4e22619fa4f9
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753284"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="80bf8-103">Гостевой доступ в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80bf8-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="80bf8-104">Гостевой доступ позволяет добавлять отдельных пользователей из-за пределов организации в команды и каналы Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="80bf8-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="80bf8-105">Чтобы сравнить внешний доступ (федерацию) с гостевым доступом (и выбрать нужный), ознакомьтесь со статьей [Общение с пользователями из других организаций в Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="80bf8-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="80bf8-106">Если вы готовы включить гостевой доступ в организации, начните с [контрольного списка гостевого доступа](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="80bf8-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="80bf8-107">Обзор гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="80bf8-107">Guest access overview</span></span>

<span data-ttu-id="80bf8-108">Гостевой доступ позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к существующим командам и каналам в Teams.</span><span class="sxs-lookup"><span data-stu-id="80bf8-108">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="80bf8-109">Любой пользователь с корпоративной или потребительской учетной записью Outlook, Gmail или других служб может участвовать в Teams в качестве гостя с полным доступом к командным чатам, собраниям и файлам.</span><span class="sxs-lookup"><span data-stu-id="80bf8-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="80bf8-110">Администратор Teams определяет, какие функции доступны для гостей в Teams. См. статью [Управление гостевым доступом](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="80bf8-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="80bf8-111">Гостевой доступ настраивается в Teams для всей организации и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="80bf8-111">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="80bf8-112">На гостевой доступ распространяются ограничения служб Azure AD и Office 365.</span><span class="sxs-lookup"><span data-stu-id="80bf8-112">Guest access is subject to Azure AD and Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="80bf8-113">Гостевые пользователи используют параметры Teams на уровне организации в режиме обновления сосуществования.</span><span class="sxs-lookup"><span data-stu-id="80bf8-113">Guest users follow Org-wide settings for coexistence mode.</span></span> <span data-ttu-id="80bf8-114">Изменить их невозможно.</span><span class="sxs-lookup"><span data-stu-id="80bf8-114">This cannot be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="80bf8-115">Лицензии для гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="80bf8-115">Licensing for guest access</span></span>

<span data-ttu-id="80bf8-116">Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="80bf8-116">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="80bf8-117">Дополнительная лицензия Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="80bf8-117">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="80bf8-118">В Teams не ограничивается число гостей, которых можно добавить.</span><span class="sxs-lookup"><span data-stu-id="80bf8-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="80bf8-119">Однако общее число гостей, которых можно добавить в клиент, зависит от разрешений лицензии Azure AD — обычно 5 гостей на пользователя с лицензией.</span><span class="sxs-lookup"><span data-stu-id="80bf8-119">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="80bf8-120">Дополнительные сведения см. в статье [Руководство по лицензированию службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="80bf8-120">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="80bf8-121">Пользователей из вашей организации, у которых есть только отдельные планы подписки на Office 365, например на Exchange Online (план 2), нельзя пригласить в качестве гостей в организацию, так как Teams считает, что они относятся к одной организации.</span><span class="sxs-lookup"><span data-stu-id="80bf8-121">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="80bf8-122">Чтобы использовать Teams для этих пользователей, им должна быть назначена подписка на Office 365 бизнес премиум, Office 365 корпоративный или Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="80bf8-122">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="80bf8-123">Кто такой гость?</span><span class="sxs-lookup"><span data-stu-id="80bf8-123">Who is a guest?</span></span>

<span data-ttu-id="80bf8-124">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="80bf8-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="80bf8-125">У него нет учебной или рабочей учетной записи, предоставленной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="80bf8-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="80bf8-126">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="80bf8-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="80bf8-127">Любого пользователя, не состоящего в вашей организации, можно добавить в качестве гостя в Teams.</span><span class="sxs-lookup"><span data-stu-id="80bf8-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="80bf8-128">Это означает, что любой пользователь с корпоративной учетной записью (т. е. учетной записью Azure Active Directory) или потребительской учетной записью электронной почты (Outlook.com, Gmail.com или других служб) может участвовать в Teams в качестве гостя с полным доступом к возможностям команд и каналов.</span><span class="sxs-lookup"><span data-stu-id="80bf8-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="80bf8-129">Дополнительные сведения о возможностях гостей см. в статье [Авторизация гостевого доступа в Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="80bf8-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="80bf8-130">Или ознакомьтесь с таблицей [сравнения возможностей участников команды и гостей](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="80bf8-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="80bf8-131">Наконец, для всех гостевых пользователей в Teams применяется такая же защита на основе средств для обеспечения соответствия требованиям и аудита, что и для остальной части Office 365. Кроме того, гостями можно безопасно управлять в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80bf8-131">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="80bf8-132">Для чего нужен гостевой доступ?</span><span class="sxs-lookup"><span data-stu-id="80bf8-132">Why use guest access?</span></span>

<span data-ttu-id="80bf8-133">С помощью гостевого доступа организации, использующие Teams, могут предоставлять своим партнерам доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя полный контроль над своими корпоративными данными.</span><span class="sxs-lookup"><span data-stu-id="80bf8-133">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="80bf8-134">Для всех гостей в Teams применяется та же защита на базе соответствия и аудита, что и для остальной части Office 365, кроме того, гостями можно безопасно управлять в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80bf8-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="80bf8-135">Общие сведения об ограничениях для гостей</span><span class="sxs-lookup"><span data-stu-id="80bf8-135">Understand the limitations for guests</span></span>

<span data-ttu-id="80bf8-136">Гостевое взаимодействие предусматривает ограничения.</span><span class="sxs-lookup"><span data-stu-id="80bf8-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="80bf8-137">Ознакомьтесь с гостевым взаимодействием, чтобы не устранять несуществующих проблем.</span><span class="sxs-lookup"><span data-stu-id="80bf8-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="80bf8-138">Например, ниже приведен список некоторых функций, недоступных для гостей в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="80bf8-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="80bf8-139">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="80bf8-139">OneDrive for Business Standalone SKU</span></span>
- <span data-ttu-id="80bf8-140">Поиск людей за пределами Teams</span><span class="sxs-lookup"><span data-stu-id="80bf8-140">People search outside of Teams</span></span>
- <span data-ttu-id="80bf8-141">Календарь, запланированные собрания или сведения о собрании</span><span class="sxs-lookup"><span data-stu-id="80bf8-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="80bf8-142">ТСОП</span><span class="sxs-lookup"><span data-stu-id="80bf8-142">PSTN</span></span>
- <span data-ttu-id="80bf8-143">Организационная диаграмма</span><span class="sxs-lookup"><span data-stu-id="80bf8-143">Organization Chart</span></span>
- <span data-ttu-id="80bf8-144">Создание или изменение команды</span><span class="sxs-lookup"><span data-stu-id="80bf8-144">Create or revise a team</span></span>
- <span data-ttu-id="80bf8-145">Поиск команды</span><span class="sxs-lookup"><span data-stu-id="80bf8-145">Browse for a team</span></span>
- <span data-ttu-id="80bf8-146">Отправка файлов в приватный чат</span><span class="sxs-lookup"><span data-stu-id="80bf8-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="80bf8-147">Гости по-прежнему могут искать и находить пользователей (за пределами команды), если они знают полный идентификатор электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="80bf8-147">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="80bf8-148">Чтобы заблокировать эту возможность, ИТ-администраторы могут использовать шаблоны, например [поиск в области каталога](teams-scoped-directory-search.md), чтобы ограничить гостей их собственным виртуальным глобальным списком адресов (GAL).</span><span class="sxs-lookup"><span data-stu-id="80bf8-148">To prevent this, IT admins can use patterns like [scoped directory search](teams-scoped-directory-search.md) that have the ability to restrict guests to their own virtual GAL.</span></span>

<span data-ttu-id="80bf8-149">Полный список возможностей, доступных и недоступных для гостей в Teams, см. в таблице [сравнения возможностей участников команд и гостей](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="80bf8-149">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="80bf8-150">Дополнительные сведения о гостевом доступе на уровне Office 365 см. в статье [Добавление гостей в группы Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="80bf8-150">To learn more about guest access at the Office 365 level, read [Adding guests to Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

## <a name="how-does-external-access-federation-compare-to-guest-access"></a><span data-ttu-id="80bf8-151">Чем внешний доступ (федерация) отличается от гостевого доступа?</span><span class="sxs-lookup"><span data-stu-id="80bf8-151">How does external access (federation) compare to guest access?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="80bf8-152">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="80bf8-152">More information</span></span>

[<span data-ttu-id="80bf8-153">Обращение в службу поддержки продуктов для бизнеса. Справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="80bf8-153">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="80bf8-154">Гостевой доступ в группах Office 365</span><span class="sxs-lookup"><span data-stu-id="80bf8-154">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
