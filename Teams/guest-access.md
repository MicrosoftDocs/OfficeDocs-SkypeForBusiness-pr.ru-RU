---
title: Гостевой доступ в Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c2e13a97c367a61559a33ea0229d7ef682744c7
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706269"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="a14e1-103">Гостевой доступ в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a14e1-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="a14e1-104">Обзор доступа гостя</span><span class="sxs-lookup"><span data-stu-id="a14e1-104">Guest access overview</span></span>

<span data-ttu-id="a14e1-105">Доступ в качестве гостя — это один из компонентов, которые клиенты и ответы по наиболее.</span><span class="sxs-lookup"><span data-stu-id="a14e1-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="a14e1-106">Ниже приведен способ справиться с ход работы на доступ в качестве гостя и сообщите нам свои мысли.</span><span class="sxs-lookup"><span data-stu-id="a14e1-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="a14e1-107">Если у вас возникают проблемы с гостевым доступом, см. раздел [Известные проблемы для Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a14e1-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="a14e1-108">Узнавайте о новых и усовершенствованных функциях из [Стратегии развития Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="a14e1-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="a14e1-109">Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="a14e1-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="a14e1-110">Поделитесь своим опытом в разделе комментариев ниже.</span><span class="sxs-lookup"><span data-stu-id="a14e1-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="a14e1-111">Доступ в качестве гостя позволяет группам в организации совместной работы с людьми за пределами вашей организации, предоставив им доступ к существующей группы и каналы на одном или нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="a14e1-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="a14e1-112">Любой пользователь с корпоративной или потребительской учетной записью Outlook, Gmail или других служб может участвовать в Teams в качестве гостя с полным доступом к командным чатам, собраниям и файлам.</span><span class="sxs-lookup"><span data-stu-id="a14e1-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="a14e1-113">Доступ в качестве гостя входит в состав всех бизнеса расширенный Office 365, Office 365 для предприятия и Office 365 Education подписки с без дополнительных требований лицензирования.</span><span class="sxs-lookup"><span data-stu-id="a14e1-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="a14e1-114">До 5 Гости на лицензированным пользователя может иметь в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a14e1-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="a14e1-115">Дополнительные сведения о лицензировании можно [лицензирования руководство Azure Active Directory B2B совместной работы](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="a14e1-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="a14e1-116">Гостевой доступ в Microsoft Teams настраивается на уровне клиента и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="a14e1-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="a14e1-117">Доступ в качестве гостя — это может быть Azure AD и ограничения для службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="a14e1-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="a14e1-118">Пользователей в вашей организации, имеющих планы подписки Office 365 автономных только, такие как Exchange Online план 2, не может присоединиться к как гости для вашей организации групп учитывает этих пользователей, принадлежащим той же организации.</span><span class="sxs-lookup"><span data-stu-id="a14e1-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="a14e1-119">Эти пользователи могли использовать команды им необходимо назначить подписки на Office 365 бизнеса расширенный, Office 365 корпоративный или Office 365 образования.</span><span class="sxs-lookup"><span data-stu-id="a14e1-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="a14e1-120">Кто является гостя?</span><span class="sxs-lookup"><span data-stu-id="a14e1-120">Who is a guest?</span></span>

<span data-ttu-id="a14e1-121">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a14e1-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="a14e1-122">У него нет учебной или рабочей учетной записи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a14e1-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="a14e1-123">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="a14e1-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="a14e1-124">Всем пользователям, которые не являются сотрудниками организации можно добавить как гости в группах.</span><span class="sxs-lookup"><span data-stu-id="a14e1-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="a14e1-125">Это означает, что лица, имеющие учетную запись business (то есть, учетной записи Azure Active Directory) или учетная запись электронной почты получателя (с Outlook.com, Gmail.com или другими пользователями) может участвовать в качестве гостя в группах, полный доступ к группам и канала среды взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="a14e1-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="a14e1-126">(Можно прочитать об ограничениях гостевой в [авторизовать гостевой доступ в группах Майкрософт](teams-dependencies.md).) Все гости в группах охвачено же соответствие требованиям и аудита защиты, что остальную часть Office 365 и может управляться безопасно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a14e1-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="a14e1-127">Причины использования гостевой доступ?</span><span class="sxs-lookup"><span data-stu-id="a14e1-127">Why use guest access?</span></span>
      
<span data-ttu-id="a14e1-128">С гостевым доступом организации, использующие команды можно обеспечить внешний доступ к группам, документов в каналы, ресурсы, чаты и приложениям партнерами, сохраняя полный контроль над корпоративной информации.</span><span class="sxs-lookup"><span data-stu-id="a14e1-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="a14e1-129">Все гости в группах охвачено же соответствие требованиям и аудита защиты, что остальную часть Office 365 и гости могут безопасное управление в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a14e1-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="a14e1-130">Команды построен на Office 365 групп и предоставляет новый способ доступа к общих ресурсов для группы с Office 365.</span><span class="sxs-lookup"><span data-stu-id="a14e1-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="a14e1-131">Teams является оптимальным решением для сохраняемого чата между участниками группы или команды.</span><span class="sxs-lookup"><span data-stu-id="a14e1-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="a14e1-132">Группы Office 365 — это служба, предоставляющая членство на несколько приложений для набора общих активов команды, таких как сайт SharePoint или панель мониторинга Power BI, чтобы обеспечить эффективную и безопасную работу команды.</span><span class="sxs-lookup"><span data-stu-id="a14e1-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="a14e1-133">Как доступ в качестве гостя сравнения для внешнего доступа (федерации)</span><span class="sxs-lookup"><span data-stu-id="a14e1-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="a14e1-134">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="a14e1-134">More information</span></span>
    
[<span data-ttu-id="a14e1-135">Ресурсы поддержки для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a14e1-135">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="a14e1-136">Гостевая доступа в Office 365 групп</span><span class="sxs-lookup"><span data-stu-id="a14e1-136">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="a14e1-137">Общие сведения о гостевой доступа</span><span class="sxs-lookup"><span data-stu-id="a14e1-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="a14e1-138">Глубокое погружение в доступ в качестве гостя</span><span class="sxs-lookup"><span data-stu-id="a14e1-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="a14e1-139">Добавление гости в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a14e1-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

