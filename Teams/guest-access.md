---
title: Гостевой доступ в Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ac614aa35e3aa453a7522559e6fda8045404ae9
ms.sourcegitcommit: 70fc5217f588e10ab0edb400f329ea597efaab52
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2018
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="6a5d0-103">Гостевой доступ в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a5d0-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="6a5d0-104">Гостевой доступ — новая функция Teams.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="6a5d0-105">О ней особенно часто просили наши клиенты.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="6a5d0-106">Мы все еще дорабатываем и совершенствуем ее возможности.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="6a5d0-107">Вы можете отслеживать наш ход работы над гостевым доступом и сообщать свое мнение.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>
- <span data-ttu-id="6a5d0-108">Если у вас возникают проблемы с гостевым доступом, см. раздел [Известные проблемы для Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6a5d0-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="6a5d0-109">Узнавайте о новых и усовершенствованных функциях из [Стратегии развития Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="6a5d0-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="6a5d0-110">Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="6a5d0-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="6a5d0-111">Поделитесь своим опытом в разделе комментариев ниже.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="6a5d0-112">Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="6a5d0-113">Лица, имеющие business потребитель электронной почты учетной записи или, например, Outlook, Gmail или другим пользователям, могут участвовать в качестве гостя в группах с полным доступом для групп обсуждения, собраний и файлы.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-113">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="6a5d0-114">Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="6a5d0-115">Дополнительная лицензия Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-115">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="6a5d0-116">Гостевой доступ в Microsoft Teams настраивается на уровне клиента и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>



<span data-ttu-id="6a5d0-117">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-117">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="6a5d0-118">У него нет учебной или рабочей учетной записи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-118">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="6a5d0-119">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-119">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="6a5d0-120">Всем пользователям можно добавить как гости в группах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-120">Anyone can be added as guest in Microsoft Teams.</span></span> <span data-ttu-id="6a5d0-121">Это означает, что лица, имеющие business (с использованием учетной записи Azure Active Directory) или учетная запись электронной почты получателя (с Outlook.com, Gmail.com или другими пользователями) могут принимать участие как гости в группах с полный доступ к группам бесед, собраний и файлы.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-121">This means that anyone with a business (with an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams with full access to teams chats, meetings and files.</span></span>
<span data-ttu-id="6a5d0-122">Все гости в группах охвачено же соответствие требованиям и аудита защиты, что остальную часть Office 365 и может управляться безопасно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-122">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

  
      

<span data-ttu-id="6a5d0-123">Организации, использующие Teams, могут предоставлять своим партнерам внешний доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя полный контроль над своими корпоративными данными.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-123">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="6a5d0-124">Все гости в группах охвачено же соответствие требованиям и аудита защиты, что остальную часть Office 365 и гости могут безопасное управление в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-124">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure Active Directory.</span></span>  

<span data-ttu-id="6a5d0-125">Продукт Teams основан на Группах Office 365 и предоставляет новый способ доступа к общим активам для группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-125">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="6a5d0-126">Teams является оптимальным решением для сохраняемого чата между участниками группы или команды.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-126">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="6a5d0-127">Группы Office 365 — это служба, предоставляющая членство на несколько приложений для набора общих активов команды, таких как сайт SharePoint или панель мониторинга Power BI, чтобы обеспечить эффективную и безопасную работу команды.</span><span class="sxs-lookup"><span data-stu-id="6a5d0-127">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

    

## <a name="more-information"></a><span data-ttu-id="6a5d0-128">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="6a5d0-128">More information</span></span>

 
  
    
  [<span data-ttu-id="6a5d0-129">Ресурсы поддержки для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a5d0-129">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="6a5d0-130">Подробный обзор гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="6a5d0-130">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="6a5d0-131">Включение гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a5d0-131">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/g21Hcqdl5tI" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="6a5d0-132">Добавление гостей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a5d0-132">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

