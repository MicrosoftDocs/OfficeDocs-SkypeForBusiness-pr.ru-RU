---
title: Переход на Microsoft Teams | Планы Skype для бизнеса Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
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
ms.openlocfilehash: 030081b4fbf633e808e1c340f7b88b8224c13700
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905191"
---
# <a name="overview"></a><span data-ttu-id="4a361-103">Обзор</span><span class="sxs-lookup"><span data-stu-id="4a361-103">Overview</span></span>

<span data-ttu-id="4a361-104">![Этапы поездки на обновление, акцент на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="4a361-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="4a361-105">Эта статья входит в стадию развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="4a361-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="4a361-106">Перед продолжением убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4a361-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="4a361-107">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="4a361-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="4a361-108">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="4a361-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="4a361-109">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="4a361-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="4a361-110">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="4a361-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="4a361-111">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="4a361-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="4a361-112">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="4a361-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

<span data-ttu-id="4a361-113">Действия, которые необходимо выполнить для перехода на Teams, зависят от текущего развертывания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4a361-113">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

1. <span data-ttu-id="4a361-114">Перед началом обновления убедитесь, что вы выполняете [пробную версию пользователя](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="4a361-114">Before beginning your upgrade, be sure you [conduct a user pilot](pilot-essentials.md).</span></span>

2.  <span data-ttu-id="4a361-115">На основе текущей среды выберите свою начальную точку:</span><span class="sxs-lookup"><span data-stu-id="4a361-115">Next, based on your current environment, choose your starting point:</span></span>  

    - <span data-ttu-id="4a361-116">**Если вы обновляете Skype для бизнеса Online в Teams**, выполните действия, описанные в статье [Переход с Skype для бизнеса Online на Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span><span class="sxs-lookup"><span data-stu-id="4a361-116">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

    -  <span data-ttu-id="4a361-117">**Если вы обновляете локальную среду Skype для бизнеса**, вам потребуется выполнить дополнительные действия, чтобы настроить связь между локальными и Интернет-средами перед перемещением пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="4a361-117">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="4a361-118">Дополнительные сведения можно найти [в разделе Обновление локальной версии Skype для бизнеса для Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="4a361-118">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
