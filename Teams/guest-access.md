---
title: Гостевой доступ в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67ddc045c04c1c3d8cb9bffa0ee15ebf71c70c2f
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656110"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="20a9c-103">Гостевой доступ в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20a9c-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="20a9c-104">Гостевой доступ позволяет добавлять отдельных пользователей из-за пределов организации в команды и каналы Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="20a9c-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="20a9c-105">Чтобы сравнить внешний доступ (федерацию) с гостевым доступом (и выбрать нужный), ознакомьтесь со статьей [Общение с пользователями из других организаций в Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="20a9c-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="20a9c-106">Если вы готовы включить гостевой доступ в организации, начните с [контрольного списка гостевого доступа](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="20a9c-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="20a9c-107">Обзор гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="20a9c-107">Guest access overview</span></span>

<span data-ttu-id="20a9c-108">Гостевой доступ позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к существующим командам и каналам в Teams.</span><span class="sxs-lookup"><span data-stu-id="20a9c-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="20a9c-109">Любой пользователь с корпоративной или потребительской учетной записью Outlook, Gmail или других служб может участвовать в Teams в качестве гостя с полным доступом к командным чатам, собраниям и файлам.</span><span class="sxs-lookup"><span data-stu-id="20a9c-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="20a9c-110">Администратор Teams определяет, какие функции доступны для гостей в Teams. См. статью [Управление гостевым доступом](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="20a9c-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="20a9c-111">Гостевой доступ настраивается в Teams для всей организации и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="20a9c-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="20a9c-112">На гостевой доступ распространяются ограничения служб Azure AD и Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="20a9c-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="20a9c-113">Гостевые пользователи используют параметры Teams на уровне организации в режиме обновления сосуществования.</span><span class="sxs-lookup"><span data-stu-id="20a9c-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="20a9c-114">Изменить их невозможно.</span><span class="sxs-lookup"><span data-stu-id="20a9c-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="20a9c-115">Лицензии для гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="20a9c-115">Licensing for guest access</span></span>

<span data-ttu-id="20a9c-116">Функция гостевого доступа включена во все подписки Microsoft 365 бизнес стандарт, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="20a9c-116">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="20a9c-117">Дополнительная лицензия Microsoft 365 или Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="20a9c-117">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="20a9c-118">В Teams не ограничивается число гостей, которых можно добавить.</span><span class="sxs-lookup"><span data-stu-id="20a9c-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="20a9c-119">Однако общее число гостей, которых можно добавить в клиент, может быть ограничено платными функциями Azure AD.</span><span class="sxs-lookup"><span data-stu-id="20a9c-119">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="20a9c-120">Дополнительные сведения см. в статье [Руководство по лицензированию службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="20a9c-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="20a9c-121">Пользователей из вашей организации, у которых есть только отдельные планы подписки на Microsoft 365 или Office 365, например на Exchange Online (план 2), нельзя пригласить в качестве гостей в организацию, так как Teams считает, что они относятся к одной организации.</span><span class="sxs-lookup"><span data-stu-id="20a9c-121">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="20a9c-122">Чтобы использовать Teams для этих пользователей, им должна быть назначена подписка на Microsoft 365 бизнес стандарт, Office 365 корпоративный или Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="20a9c-122">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="20a9c-123">Кто такой гость?</span><span class="sxs-lookup"><span data-stu-id="20a9c-123">Who is a guest?</span></span>

<span data-ttu-id="20a9c-124">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="20a9c-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="20a9c-125">У него нет учебной или рабочей учетной записи, предоставленной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="20a9c-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="20a9c-126">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="20a9c-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="20a9c-127">Любого пользователя, не состоящего в вашей организации, можно добавить в качестве гостя в Teams.</span><span class="sxs-lookup"><span data-stu-id="20a9c-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="20a9c-128">Это означает, что любой пользователь с корпоративной учетной записью (т. е. учетной записью Azure Active Directory) или потребительской учетной записью электронной почты (Outlook.com, Gmail.com или других служб) может участвовать в Teams в качестве гостя с полным доступом к возможностям команд и каналов.</span><span class="sxs-lookup"><span data-stu-id="20a9c-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="20a9c-129">Дополнительные сведения о возможностях гостей см. в статье [Авторизация гостевого доступа в Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="20a9c-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="20a9c-130">Или ознакомьтесь с таблицей [сравнения возможностей участников команды и гостей](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="20a9c-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="20a9c-131">Наконец, для всех гостевых пользователей в Teams применяется такая же защита на основе средств для обеспечения соответствия требованиям и аудита, что и для остальной части Microsoft 365 и Office 365. Кроме того, гостями можно безопасно управлять в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="20a9c-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="20a9c-132">Для чего нужен гостевой доступ?</span><span class="sxs-lookup"><span data-stu-id="20a9c-132">Why use guest access?</span></span>

<span data-ttu-id="20a9c-133">С помощью гостевого доступа организации, использующие Teams, могут предоставлять своим партнерам доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя полный контроль над своими корпоративными данными.</span><span class="sxs-lookup"><span data-stu-id="20a9c-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="20a9c-134">Для всех гостевых пользователей в Teams применяется такая же защита на основе средств для обеспечения соответствия требованиям и аудита, что и для остальной части Microsoft 365 и Office 365. Кроме того, гостями можно безопасно управлять в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="20a9c-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="20a9c-135">Общие сведения об ограничениях для гостей</span><span class="sxs-lookup"><span data-stu-id="20a9c-135">Understand the limitations for guests</span></span>

<span data-ttu-id="20a9c-136">Гостевое взаимодействие предусматривает ограничения.</span><span class="sxs-lookup"><span data-stu-id="20a9c-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="20a9c-137">Ознакомьтесь с гостевым взаимодействием, чтобы не устранять несуществующих проблем.</span><span class="sxs-lookup"><span data-stu-id="20a9c-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="20a9c-138">Например, ниже приведен список некоторых функций, недоступных для гостей в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="20a9c-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="20a9c-139">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="20a9c-139">OneDrive for Business</span></span>
- <span data-ttu-id="20a9c-140">Поиск людей за пределами Teams</span><span class="sxs-lookup"><span data-stu-id="20a9c-140">People search outside of Teams</span></span>
- <span data-ttu-id="20a9c-141">Календарь, запланированные собрания или сведения о собрании</span><span class="sxs-lookup"><span data-stu-id="20a9c-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="20a9c-142">ТСОП</span><span class="sxs-lookup"><span data-stu-id="20a9c-142">PSTN</span></span>
- <span data-ttu-id="20a9c-143">Организационная диаграмма</span><span class="sxs-lookup"><span data-stu-id="20a9c-143">Organization chart</span></span>
- <span data-ttu-id="20a9c-144">Создание или изменение команды</span><span class="sxs-lookup"><span data-stu-id="20a9c-144">Create or revise a team</span></span>
- <span data-ttu-id="20a9c-145">Поиск команды</span><span class="sxs-lookup"><span data-stu-id="20a9c-145">Browse for a team</span></span>
- <span data-ttu-id="20a9c-146">Отправка файлов в приватный чат</span><span class="sxs-lookup"><span data-stu-id="20a9c-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="20a9c-147">В настоящее время Teams поддерживает гостевых пользователей только с состояниями 1 и 2 [согласно определению Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="20a9c-147">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="20a9c-148">Полный список возможностей, доступных и недоступных для гостей в Teams, см. в таблице [сравнения возможностей участников команд и гостей](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="20a9c-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="20a9c-149">Дополнительные сведения о гостевом доступе на уровне Microsoft 365 и Office 365 см. в статье [Добавление гостей в группы Microsoft 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="20a9c-149">To learn more about guest access at the Microsoft 365 and Office 365 levels, read [Adding guests to Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="20a9c-150">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="20a9c-150">More information</span></span>

[<span data-ttu-id="20a9c-151">Обращение в службу поддержки продуктов для бизнеса. Справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="20a9c-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)  
[<span data-ttu-id="20a9c-152">Гостевой доступ в группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20a9c-152">Guest access in Microsoft 365 Groups</span></span>](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
