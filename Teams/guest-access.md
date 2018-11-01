---
title: Гостевой доступ в Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 10/31/2017
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d13a48856aae71634ed6588a714d578416ed594
ms.sourcegitcommit: 6d30cfdd8c8b8908d4e4f278c39fd22062f4a888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890558"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="321bb-103">Гостевой доступ в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321bb-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="321bb-104">Гостевой доступ — новая функция Teams.</span><span class="sxs-lookup"><span data-stu-id="321bb-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="321bb-105">О ней особенно часто просили наши клиенты.</span><span class="sxs-lookup"><span data-stu-id="321bb-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="321bb-106">Мы все еще дорабатываем и совершенствуем ее возможности.</span><span class="sxs-lookup"><span data-stu-id="321bb-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="321bb-107">Вы можете отслеживать наш ход работы над гостевым доступом и сообщать свое мнение.</span><span class="sxs-lookup"><span data-stu-id="321bb-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>

- <span data-ttu-id="321bb-108">Если у вас возникают проблемы с гостевым доступом, см. раздел [Известные проблемы для Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="321bb-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="321bb-109">Узнавайте о новых и усовершенствованных функциях из [Стратегии развития Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="321bb-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="321bb-110">Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="321bb-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="321bb-111">Поделитесь своим опытом в разделе комментариев ниже.</span><span class="sxs-lookup"><span data-stu-id="321bb-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="321bb-112">Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.</span><span class="sxs-lookup"><span data-stu-id="321bb-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="321bb-113">Лица, имеющие business потребитель электронной почты учетной записи или, например, Outlook, Gmail или другим пользователям, могут участвовать в качестве гостя в группах с полным доступом для групп обсуждения, собраний и файлы.</span><span class="sxs-lookup"><span data-stu-id="321bb-113">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="321bb-114">Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="321bb-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="321bb-115">Дополнительная лицензия Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="321bb-115">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="321bb-116">Гостевой доступ в Microsoft Teams настраивается на уровне клиента и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="321bb-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>


## <a name="what-is-a-guest"></a><span data-ttu-id="321bb-117">Кто такой гость?</span><span class="sxs-lookup"><span data-stu-id="321bb-117">What is a guest?</span></span>

<span data-ttu-id="321bb-118">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="321bb-118">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="321bb-119">У него нет учебной или рабочей учетной записи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="321bb-119">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="321bb-120">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="321bb-120">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="321bb-121">Всем пользователям можно добавить как гости в группах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="321bb-121">Anyone can be added as guest in Microsoft Teams.</span></span> <span data-ttu-id="321bb-122">Это означает, что лица, имеющие business (с использованием учетной записи Azure Active Directory) или учетная запись электронной почты получателя (с Outlook.com, Gmail.com или другими пользователями) могут принимать участие как гости в группах с полный доступ к группам бесед, собраний и файлы.</span><span class="sxs-lookup"><span data-stu-id="321bb-122">This means that anyone with a business (with an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams with full access to teams chats, meetings and files.</span></span>

<span data-ttu-id="321bb-123">Все гости в группах охвачено же соответствие требованиям и аудита защиты, что остальную часть Office 365 и может управляться безопасно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="321bb-123">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

> [!NOTE]
> <span data-ttu-id="321bb-124">Пользователей в вашей организации с планами подписки на Office 365 автономных только, такие как Exchange Online план 2, не может пригласить как гости в вашей организации с момента команды считает этих пользователей, принадлежащим той же организации.</span><span class="sxs-lookup"><span data-stu-id="321bb-124">Users in your organization with standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization since Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="321bb-125">Эти пользователи могли использовать команды им необходимо назначить подписки на Office 365 бизнеса расширенный, Office 365 корпоративный или Office 365 образования.</span><span class="sxs-lookup"><span data-stu-id="321bb-125">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span>  
      
<span data-ttu-id="321bb-126">Организации, использующие Teams, могут предоставлять своим партнерам внешний доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя полный контроль над своими корпоративными данными.</span><span class="sxs-lookup"><span data-stu-id="321bb-126">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="321bb-127">Все гости в группах охвачено же соответствие требованиям и аудита защиты, что остальную часть Office 365 и гости могут безопасное управление в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="321bb-127">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure Active Directory.</span></span> 

## <a name="how-does-guest-access-compare-to-federation-external-access"></a><span data-ttu-id="321bb-128">Как доступ в качестве гостя сравнения для федерации (внешний доступ)</span><span class="sxs-lookup"><span data-stu-id="321bb-128">How does guest access compare to federation (external access)?</span></span>

<span data-ttu-id="321bb-129">Доступ в качестве гостя отличается от внешнего доступа (так называемая федерация) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="321bb-129">Guest access differs from external access (also known as federation) as follows:</span></span>

-   <span data-ttu-id="321bb-130">С гостевым доступом Гость имеет права на конкретными группами группам, что приглашение в пользователя и можно получить доступ к зависящие от группы ресурсов, таких как файлы и каналы.</span><span class="sxs-lookup"><span data-stu-id="321bb-130">With guest access, a guest user has access to a specific Teams team that the user is invited into, and can access team-specific resources such as channels and files.</span></span> <span data-ttu-id="321bb-131">Гости можно общаться с и вызова членов группы.</span><span class="sxs-lookup"><span data-stu-id="321bb-131">The guest user can also chat with and call members of the team.</span></span>

-   <span data-ttu-id="321bb-132">С федерации или внешнего доступа внешних пользователей может иметь чаты 1:1 и звонки с пользователем в другой организации с помощью группы или Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="321bb-132">With federation or external access, an external user can have 1:1 chats and calls with a user in another organization by using either Teams or Skype for Business.</span></span> <span data-ttu-id="321bb-133">Федеративный пользователь не может получить доступ к любой ресурсы группы.</span><span class="sxs-lookup"><span data-stu-id="321bb-133">The federated user cannot access any team resources.</span></span> <span data-ttu-id="321bb-134">По сравнению с гостевой доступ, внешний доступ разрешает передачу данных перекрестные организации (если это разрешено политиками) без явного приглашения, но не может превышать чата и вызвать только.</span><span class="sxs-lookup"><span data-stu-id="321bb-134">Compared to guest access, external access allows cross organization communication (if permitted by policies) without an explicit invitation, but is limited to chat and call only.</span></span>

## <a name="teams-and-office-365-groups"></a><span data-ttu-id="321bb-135">Группы и группы Office 365</span><span class="sxs-lookup"><span data-stu-id="321bb-135">Teams and Office 365 Groups</span></span>

<span data-ttu-id="321bb-136">Команды построен на Office 365 групп и предоставляет новый способ доступа к общих ресурсов для группы с Office 365.</span><span class="sxs-lookup"><span data-stu-id="321bb-136">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="321bb-137">Teams является оптимальным решением для сохраняемого чата между участниками группы или команды.</span><span class="sxs-lookup"><span data-stu-id="321bb-137">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="321bb-138">Группы Office 365 — это служба, предоставляющая членство на несколько приложений для набора общих активов команды, таких как сайт SharePoint или панель мониторинга Power BI, чтобы обеспечить эффективную и безопасную работу команды.</span><span class="sxs-lookup"><span data-stu-id="321bb-138">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

## <a name="more-information"></a><span data-ttu-id="321bb-139">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="321bb-139">More information</span></span>

 
  
    
  [<span data-ttu-id="321bb-140">Ресурсы поддержки для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321bb-140">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="321bb-141">Подробный обзор гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="321bb-141">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="321bb-142">Включение гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321bb-142">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/g21Hcqdl5tI" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="321bb-143">Добавление гостей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321bb-143">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

