---
title: Общие сведения о внедрении обновления до Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Определите оптимальный путь обновления Microsoft Teams с учетом текущего Skype для бизнеса развертывания.
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
ms.openlocfilehash: 1774b8bebc1330e69a611e64d4f0a8e01f05febb
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282376"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="c82df-103">Общие сведения о внедрении обновления</span><span class="sxs-lookup"><span data-stu-id="c82df-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="c82df-104">![Этапы пути обновления с акцентом на этапе развертывания и внедрения](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и внедрения")</span><span class="sxs-lookup"><span data-stu-id="c82df-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="c82df-105">Эта статья является частью этапа развертывания и реализации, на который вы входите.</span><span class="sxs-lookup"><span data-stu-id="c82df-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="c82df-106">Необходимые действия по планированию</span><span class="sxs-lookup"><span data-stu-id="c82df-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c82df-107">Прежде чем приперейти к реализации обновления, убедитесь, [](upgrade-plan-journey.md) что вы прочитали статью о планировании, начиная с плана обновления, чтобы убедиться, что все необходимые действия по планированию завершены.</span><span class="sxs-lookup"><span data-stu-id="c82df-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="c82df-108">Привлечение заинтересованных лиц по проекту</span><span class="sxs-lookup"><span data-stu-id="c82df-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="c82df-109">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="c82df-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="c82df-110">Понятное сосуществование и совместное Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="c82df-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="c82df-111">Выбор пути обновления</span><span class="sxs-lookup"><span data-stu-id="c82df-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="c82df-112">Запланированный пилотный проект пользователя</span><span class="sxs-lookup"><span data-stu-id="c82df-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="c82df-113">Подготовьте свою среду</span><span class="sxs-lookup"><span data-stu-id="c82df-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="c82df-114">Подготовленные организации</span><span class="sxs-lookup"><span data-stu-id="c82df-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="c82df-115">Выбор начальной точки обновления</span><span class="sxs-lookup"><span data-stu-id="c82df-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="c82df-116">Действия, которые необходимо выполнить для обновления до Teams, зависят от текущего развертывания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c82df-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="c82df-117">В зависимости от текущей среды выберите отправную точку:</span><span class="sxs-lookup"><span data-stu-id="c82df-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="c82df-118">**Если вы обновляете** Skype для бизнеса Online до Teams, выполните действия, которые можно найти в Skype для бизнеса [Online Teams.](./upgrade-to-teams-execute-skypeforbusinessonline.md)</span><span class="sxs-lookup"><span data-stu-id="c82df-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="c82df-119">**При переходе** с локальной среды Skype для бизнеса вам потребуется выполнить дополнительные действия, чтобы настроить подключение между локальной и сетевой средами, прежде чем перемещать пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="c82df-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="c82df-120">Дополнительные сведения см. в [Skype для бизнеса локальной Teams.](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="c82df-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]