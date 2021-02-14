---
title: Подготовка ИТ-персонала к microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как подготовить ИТ-персонал в организации к развертыванию и поддержке Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 680106618d610d0adc3f93658e3a522d63850e24
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578462"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="1ee7a-103">Подготовка ИТ-персонала к microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ee7a-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="1ee7a-104">![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")</span><span class="sxs-lookup"><span data-stu-id="1ee7a-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="1ee7a-105">Эта статья является частью этапа технической готовности, которое вы завершаете параллельно с этапом подготовки пользователя.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="1ee7a-106">Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:</span><span class="sxs-lookup"><span data-stu-id="1ee7a-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="1ee7a-107">Привлечение заинтересованных лиц проекта</span><span class="sxs-lookup"><span data-stu-id="1ee7a-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1ee7a-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="1ee7a-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="1ee7a-109">Понимание сосуществования и совместной работы Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="1ee7a-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="1ee7a-110">Вы решили перейти на нее</span><span class="sxs-lookup"><span data-stu-id="1ee7a-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="1ee7a-111">Администраторы microsoft 365 или Office 365, технические специалисты и служба поддержки должны учитывать качество работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-111">Your Microsoft 365 or Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="1ee7a-112">Это включает в себя обеспечение готовности сети к поддержке Teams, настройке Teams для пользователей, а также эффективному устранению возникающих неполадок и устранению возникающих проблем.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="1ee7a-113">Поделитесь следующими ресурсами с ИТ-сотрудниками и подтвердите, что они готовы оказать поддержку пользователям, прежде чем начать обновление до Teams:</span><span class="sxs-lookup"><span data-stu-id="1ee7a-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="1ee7a-114">Обучение администратора для работы с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ee7a-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="1ee7a-115">Обращение в службу поддержки продуктов для бизнеса. Справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="1ee7a-115">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [<span data-ttu-id="1ee7a-116">Устранение проблем связи с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ee7a-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="1ee7a-117">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ee7a-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)



| | |
|---|---|
| ![Значок, изображающий точки принятия решений](media/audio_conferencing_image7.png) <br/><span data-ttu-id="1ee7a-119">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="1ee7a-119">Decision points</span></span>|<ul><li><span data-ttu-id="1ee7a-120">Вы вовлечены ли все сотрудники службы поддержки, которые, вероятнее всего, будут участвовать в развертывании и поддержке Teams?</span><span class="sxs-lookup"><span data-stu-id="1ee7a-120">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="1ee7a-121">Вы разработали план обучения по переубору дополнительных сотрудников по мере обновления?</span><span class="sxs-lookup"><span data-stu-id="1ee7a-121">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![Значок, изображающий дальнейшие действия](media/audio_conferencing_image9.png)<br/><span data-ttu-id="1ee7a-123">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1ee7a-123">Next steps</span></span>|<ul><li><span data-ttu-id="1ee7a-124">Убедитесь, что ИТ-персонал обладает необходимой информацией.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-124">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="1ee7a-125">Возвращаясь к планам обучения и подготовки по мере выпуска новых функций.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-125">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="1ee7a-126">Подготовив ИТ-персонал для Teams, убедитесь, что ваша среда соответствует всем [необходимым требованиям.](upgrade-plan-journey-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="1ee7a-126">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>
