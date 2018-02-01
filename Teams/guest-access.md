---
title: "Гостевой доступ в Microsoft Teams"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 07dbb6faca20fd39fc65c6508489500dda143040
ms.sourcegitcommit: d62b48ee2c21435555255afe78db6349139b070c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="61853-103">Гостевой доступ в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61853-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="61853-104">Гостевой доступ — новая функция Teams.</span><span class="sxs-lookup"><span data-stu-id="61853-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="61853-105">О ней особенно часто просили наши клиенты.</span><span class="sxs-lookup"><span data-stu-id="61853-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="61853-106">Мы все еще дорабатываем и совершенствуем ее возможности.</span><span class="sxs-lookup"><span data-stu-id="61853-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="61853-107">Вы можете отслеживать наш ход работы над гостевым доступом и сообщать свое мнение.</span><span class="sxs-lookup"><span data-stu-id="61853-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>
- <span data-ttu-id="61853-108">Если у вас возникают проблемы с гостевым доступом, см. раздел [Известные проблемы для Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="61853-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="61853-109">Узнавайте о новых и усовершенствованных функциях из [Стратегии развития Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="61853-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="61853-110">Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="61853-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="61853-111">Поделитесь своим опытом в разделе комментариев ниже.</span><span class="sxs-lookup"><span data-stu-id="61853-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="61853-112">Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.</span><span class="sxs-lookup"><span data-stu-id="61853-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="61853-113">Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="61853-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="61853-114">Дополнительная лицензия Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="61853-114">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="61853-115">Гостевой доступ в Microsoft Teams настраивается на уровне клиента и по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="61853-115">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>


<span data-ttu-id="61853-116">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="61853-116">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="61853-117">У него нет учебной или рабочей учетной записи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="61853-117">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="61853-118">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="61853-118">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="61853-119">В качестве гостей можно добавить только пользователей с адресом электронной почты, соответствующим рабочей или учебной учетной записи Office 365 или Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="61853-119">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
       

<span data-ttu-id="61853-120">Организации, использующие Teams, могут предоставлять своим партнерам внешний доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя полный контроль над своими корпоративными данными.</span><span class="sxs-lookup"><span data-stu-id="61853-120">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span>

<span data-ttu-id="61853-121">Продукт Teams основан на Группах Office 365 и предоставляет новый способ доступа к общим активам для группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="61853-121">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="61853-122">Teams является оптимальным решением для сохраняемого чата между участниками группы или команды.</span><span class="sxs-lookup"><span data-stu-id="61853-122">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="61853-123">Группы Office 365 — это служба, предоставляющая членство на несколько приложений для набора общих активов команды, таких как сайт SharePoint или панель мониторинга Power BI, чтобы обеспечить эффективную и безопасную работу команды.</span><span class="sxs-lookup"><span data-stu-id="61853-123">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

    

## <a name="more-information"></a><span data-ttu-id="61853-124">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="61853-124">More information</span></span>

 
  
    
  [<span data-ttu-id="61853-125">Ресурсы поддержки для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61853-125">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="61853-126">Подробный обзор гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="61853-126">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="61853-127">Включение гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61853-127">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/7T54KmlIHQk" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="61853-128">Добавление гостей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61853-128">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

