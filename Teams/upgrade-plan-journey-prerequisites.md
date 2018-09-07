---
title: Необходимые условия и окружающей среды зависимостей для групп Майкрософт - группами Майкрософт
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Используйте данное руководство, чтобы узнать о необходимых компонентов и окружающей среды зависимости, чтобы развернуть группами в организации
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9db3bcc8e9171670288d0e5b14e120a9dd3692f0
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851057"
---
<span data-ttu-id="dfec5-103">![Этапы обновления пути с акцентом на стадии технической готовности] (media/upgrade-banner-tech-readiness.png "Этапы обновления пути с акцентом на стадии технической готовности")</span><span class="sxs-lookup"><span data-stu-id="dfec5-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="dfec5-104">В этой статье является частью технической готовности этапа обновления пути, действия, которые выполнить параллельно с рабочей области готовность пользователей.</span><span class="sxs-lookup"><span data-stu-id="dfec5-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="dfec5-105">Прежде чем продолжить, убедитесь, что вы выполните эти действия из предыдущих этапов:</span><span class="sxs-lookup"><span data-stu-id="dfec5-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

-   [<span data-ttu-id="dfec5-106">Прикреплено другие заинтересованные стороны проекта</span><span class="sxs-lookup"><span data-stu-id="dfec5-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="dfec5-107">Определенные области проекта</span><span class="sxs-lookup"><span data-stu-id="dfec5-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="dfec5-108">Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="dfec5-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="dfec5-109">Выбранные обновления пути</span><span class="sxs-lookup"><span data-stu-id="dfec5-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="dfec5-110">Необходимые условия и окружающей среды зависимостей для групп</span><span class="sxs-lookup"><span data-stu-id="dfec5-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="dfec5-111">Команды объединяет несколько служб Office 365 и таким образом, зависит от правильного внедрения и эксплуатации этих служб.</span><span class="sxs-lookup"><span data-stu-id="dfec5-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="dfec5-112">Эти службы включают —, но не ограничиваются ими — SharePoint Online, Exchange Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dfec5-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="dfec5-113">Хотя не все службы необходимы, настоятельно рекомендуется реализовать все из них.</span><span class="sxs-lookup"><span data-stu-id="dfec5-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="dfec5-114">Реализовать определенных служб не выбрано, будет влияет на функциональность, команды можно предоставить пользователям организации.</span><span class="sxs-lookup"><span data-stu-id="dfec5-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="dfec5-115">Например, на то, что у вас нет для реализации SharePoint Online, группами полагаться на SharePoint Online для некоторых возможностей такие как общий доступ к файлам в беседах группы, поэтому не реализация этой службы повлечет за собой уменьшение функциональные возможности, предоставляемые в клиент.</span><span class="sxs-lookup"><span data-stu-id="dfec5-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="dfec5-116">Обратитесь к следующим документам, чтобы узнать о необходимых условиях и взаимодействие с другими технологиями групп:</span><span class="sxs-lookup"><span data-stu-id="dfec5-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

-   <span data-ttu-id="dfec5-117">Если ваша организация еще не развернут любой рабочих нагрузок Office 365, ознакомьтесь со [Приступая к работе с Office 365 для бизнеса](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="dfec5-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

-   <span data-ttu-id="dfec5-118">Если ваша организация еще не добавлена или настроен подтвержденным доменом для Office 365, из раздела [Verify вашему домену Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="dfec5-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="dfec5-119">Если ваша организация не синхронизирована удостоверения для Azure Active Directory, просмотрите [модели идентификации и проверки подлинности в группах Майкрософт](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="dfec5-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="dfec5-120">Если doesn¹t вашей организации Exchange Online, просмотрите [Общие сведения о взаимодействие Exchange и группами Майкрософт](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="dfec5-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="dfec5-121">Если организация не имеет SharePoint Online, видеть [тщательно изучите взаимодействия SharePoint Online и OneDrive для бизнеса с группами Майкрософт](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="dfec5-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

-   <span data-ttu-id="dfec5-122">Узнайте, как [группы Office 365 и группами Майкрософт взаимодействия](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="dfec5-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

-   <span data-ttu-id="dfec5-123">Если ваша организация заведения и используйте систему сведений учебы, [Развертывание синхронизации данных School](https://docs.microsoft.com/schooldatasync) перед развертыванием группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dfec5-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>
                                                                           

<span data-ttu-id="dfec5-124">По окончании проверки, что среда соответствует всех соответствующих необходимых компонентов, [оценить текущую среду для групп](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="dfec5-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>