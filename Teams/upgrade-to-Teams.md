---
title: Общие сведения о внедрении обновления в Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Определите оптимальный способ обновления для Microsoft Teams в соответствии с текущим развертыванием Skype для бизнеса.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578362"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="5cf46-103">Общие сведения о реализации обновления</span><span class="sxs-lookup"><span data-stu-id="5cf46-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="5cf46-104">![Этапы поездки на обновление, акцент на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="5cf46-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="5cf46-105">Эта статья входит в стадию развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="5cf46-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="5cf46-106">Необходимые действия по планированию</span><span class="sxs-lookup"><span data-stu-id="5cf46-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cf46-107">Прежде чем приступить к реализации обновления, подтвердите, что вы прочитали содержимое планирования, начиная с [плана обновления](upgrade-plan-journey.md) , чтобы убедиться, что вы выполнили все необходимые требования к планированию activites.</span><span class="sxs-lookup"><span data-stu-id="5cf46-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="5cf46-108">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="5cf46-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5cf46-109">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="5cf46-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="5cf46-110">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="5cf46-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="5cf46-111">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="5cf46-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="5cf46-112">Планирование пилотной версии пользователя</span><span class="sxs-lookup"><span data-stu-id="5cf46-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="5cf46-113">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="5cf46-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="5cf46-114">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="5cf46-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="5cf46-115">Выбор начальной точки обновления</span><span class="sxs-lookup"><span data-stu-id="5cf46-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="5cf46-116">Действия, которые необходимо выполнить для перехода на Teams, зависят от текущего развертывания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5cf46-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="5cf46-117">В соответствии с текущей средой выберите отправную точку.</span><span class="sxs-lookup"><span data-stu-id="5cf46-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="5cf46-118">**Если вы обновляете Skype для бизнеса Online в Teams**, выполните действия, описанные в статье [Переход с Skype для бизнеса Online на Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span><span class="sxs-lookup"><span data-stu-id="5cf46-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="5cf46-119">**Если вы обновляете локальную среду Skype для бизнеса**, вам потребуется выполнить дополнительные действия, чтобы настроить связь между локальными и Интернет-средами перед перемещением пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="5cf46-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="5cf46-120">Дополнительные сведения можно найти [в разделе Обновление локальной версии Skype для бизнеса для Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="5cf46-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
