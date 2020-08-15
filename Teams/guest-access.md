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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761245"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="04715-103">Гостевой доступ в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04715-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="04715-104">Гостевой доступ позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к существующим командам и каналам в Teams.</span><span class="sxs-lookup"><span data-stu-id="04715-104">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="04715-105">Любой пользователь, у которого есть учетная запись электронной почты для бизнеса или получателя, например Microsoft 365, Outlook, Gmail или другие, может выступать в качестве гостя в Teams с полным доступом к разговорам групп, собраниям и файлам.</span><span class="sxs-lookup"><span data-stu-id="04715-105">Anyone with a business or consumer email account, such as Microsoft 365, Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="04715-106">Администратор Teams определяет, какие функции доступны для гостей в Teams. См. статью [Управление гостевым доступом](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="04715-106">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="04715-107">Чтобы сравнить внешний доступ (федерацию) с гостевым доступом (и выбрать нужный), ознакомьтесь со статьей [Общение с пользователями из других организаций в Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="04715-107">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="04715-108">Гостевой доступ настраивается в Teams для всей организации и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="04715-108">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="04715-109">(Вы можете контролировать гостевой доступ к отдельным командам, используя [метки чувствительности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span><span class="sxs-lookup"><span data-stu-id="04715-109">(You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="04715-110">Если вы готовы приступить к приглашению гостей в Teams, ознакомьтесь с одним из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="04715-110">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="04715-111">Чтобы настроить гостевой доступ для Teams для общего использования, ознакомьтесь со сведениями о [совместной работе с гостями в группе](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="04715-111">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="04715-112">Для совместной работы с партнерской организацией, использующей Azure Active Directory и разрешающей самостоятельной регистрации гостей для доступа группы, ознакомьтесь со статьей [Создание экстрасети с управляемыми гостями](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span><span class="sxs-lookup"><span data-stu-id="04715-112">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="04715-113">На гостевой доступ распространяются ограничения служб Azure AD и Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="04715-113">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04715-114">Гостевые пользователи используют параметры Teams на уровне организации в режиме обновления сосуществования.</span><span class="sxs-lookup"><span data-stu-id="04715-114">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="04715-115">Изменить их невозможно.</span><span class="sxs-lookup"><span data-stu-id="04715-115">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="04715-116">Лицензии для гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="04715-116">Licensing for guest access</span></span>

<span data-ttu-id="04715-117">Функция гостевого доступа включена во все подписки Microsoft 365 бизнес стандарт, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="04715-117">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="04715-118">Дополнительная лицензия Microsoft 365 или Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="04715-118">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="04715-119">В Teams не ограничивается число гостей, которых можно добавить.</span><span class="sxs-lookup"><span data-stu-id="04715-119">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="04715-120">Однако общее число гостей, которых можно добавить в клиент, может быть ограничено платными функциями Azure AD.</span><span class="sxs-lookup"><span data-stu-id="04715-120">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="04715-121">Дополнительные сведения см. в статье [Руководство по лицензированию службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="04715-121">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="04715-122">Пользователей из вашей организации, у которых есть только отдельные планы подписки на Microsoft 365 или Office 365, например на Exchange Online (план 2), нельзя пригласить в качестве гостей в организацию, так как Teams считает, что они относятся к одной организации.</span><span class="sxs-lookup"><span data-stu-id="04715-122">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="04715-123">Чтобы использовать Teams для этих пользователей, им должна быть назначена подписка на Microsoft 365 бизнес стандарт, Office 365 корпоративный или Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="04715-123">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="04715-124">Кто такой гость?</span><span class="sxs-lookup"><span data-stu-id="04715-124">Who is a guest?</span></span>

<span data-ttu-id="04715-125">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="04715-125">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="04715-126">У него нет учебной или рабочей учетной записи, предоставленной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="04715-126">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="04715-127">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="04715-127">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="04715-128">Любого пользователя, не состоящего в вашей организации, можно добавить в качестве гостя в Teams.</span><span class="sxs-lookup"><span data-stu-id="04715-128">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="04715-129">Это означает, что любой пользователь с корпоративной учетной записью (т. е. учетной записью Azure Active Directory) или потребительской учетной записью электронной почты (Outlook.com, Gmail.com или других служб) может участвовать в Teams в качестве гостя с полным доступом к возможностям команд и каналов.</span><span class="sxs-lookup"><span data-stu-id="04715-129">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="04715-130">Дополнительные сведения о возможностях гостей см. в статье [Авторизация гостевого доступа в Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="04715-130">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="04715-131">Или ознакомьтесь с таблицей [сравнения возможностей участников команды и гостей](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="04715-131">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="04715-132">Наконец, все гости в Teams обрабатываются с помощью одной и той же защиты соответствия требованиям и аудита в рамках Microsoft 365 и которыми можно управлять в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="04715-132">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="04715-133">Для чего нужен гостевой доступ?</span><span class="sxs-lookup"><span data-stu-id="04715-133">Why use guest access?</span></span>

<span data-ttu-id="04715-134">С помощью гостевого доступа организации, использующие Teams, могут предоставлять своим партнерам доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя полный контроль над своими корпоративными данными.</span><span class="sxs-lookup"><span data-stu-id="04715-134">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> 

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="04715-135">Общие сведения об ограничениях для гостей</span><span class="sxs-lookup"><span data-stu-id="04715-135">Understand the limitations for guests</span></span>

<span data-ttu-id="04715-136">Гостевое взаимодействие предусматривает ограничения.</span><span class="sxs-lookup"><span data-stu-id="04715-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="04715-137">Ознакомьтесь с гостевым взаимодействием, чтобы не устранять несуществующих проблем.</span><span class="sxs-lookup"><span data-stu-id="04715-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="04715-138">Ниже приведен список некоторых функциональных возможностей, недоступных для гостей в Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="04715-138">Here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="04715-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="04715-139">OneDrive</span></span>
- <span data-ttu-id="04715-140">Поиск людей за пределами Teams</span><span class="sxs-lookup"><span data-stu-id="04715-140">People search outside of Teams</span></span>
- <span data-ttu-id="04715-141">Календарь, запланированные собрания или сведения о собрании</span><span class="sxs-lookup"><span data-stu-id="04715-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="04715-142">ТСОП</span><span class="sxs-lookup"><span data-stu-id="04715-142">PSTN</span></span>
- <span data-ttu-id="04715-143">Организационная диаграмма</span><span class="sxs-lookup"><span data-stu-id="04715-143">Organization chart</span></span>
- <span data-ttu-id="04715-144">Создание или изменение команды</span><span class="sxs-lookup"><span data-stu-id="04715-144">Create or revise a team</span></span>
- <span data-ttu-id="04715-145">Поиск команды</span><span class="sxs-lookup"><span data-stu-id="04715-145">Browse for a team</span></span>
- <span data-ttu-id="04715-146">Отправка файлов в приватный чат</span><span class="sxs-lookup"><span data-stu-id="04715-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="04715-147">В настоящее время в Teams поддерживаются только [Типы гостевых пользователей состояния 1 и состояния 2](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="04715-147">Currently, Teams supports only [State 1 and State 2 types of guest users](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="04715-148">Полный список возможностей, доступных и недоступных для гостей в Teams, см. в таблице [сравнения возможностей участников команд и гостей](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="04715-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="04715-149">Чтобы узнать больше о гостевом доступе на уровне Microsoft 365, читайте в разделе [Совместная работа с людьми за пределами Организации](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span><span class="sxs-lookup"><span data-stu-id="04715-149">To learn more about guest access at the Microsoft 365 level, read [Collaborating with people outside your organization](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span></span>


## <a name="related-topics"></a><span data-ttu-id="04715-150">См. также</span><span class="sxs-lookup"><span data-stu-id="04715-150">Related topics</span></span>

[<span data-ttu-id="04715-151">Обращение в службу поддержки продуктов для бизнеса. Справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="04715-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="04715-152">Настройка групп с тремя уровнями защиты</span><span class="sxs-lookup"><span data-stu-id="04715-152">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
