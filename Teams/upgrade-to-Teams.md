---
title: Переход на Microsoft Teams | Планы Skype для бизнеса Teams
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 381a4475a4e6464586e25e5cc8b6c9b7902acc2f
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523392"
---
# <a name="overview"></a><span data-ttu-id="a0408-103">Обзор</span><span class="sxs-lookup"><span data-stu-id="a0408-103">Overview</span></span>

<span data-ttu-id="a0408-104">![Этапы поездки на обновление, акцент на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="a0408-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="a0408-105">Эта статья входит в стадию развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="a0408-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="a0408-106">Перед продолжением убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a0408-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="a0408-107">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="a0408-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="a0408-108">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="a0408-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="a0408-109">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="a0408-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="a0408-110">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="a0408-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="a0408-111">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="a0408-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="a0408-112">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="a0408-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

<span data-ttu-id="a0408-113">Действия, которые необходимо выполнить для перехода на Teams, зависят от текущего развертывания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a0408-113">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

1. <span data-ttu-id="a0408-114">Перед началом обновления убедитесь, что вы выполняете [пробную версию пользователя](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="a0408-114">Before beginning your upgrade, be sure you [conduct a user pilot](pilot-essentials.md).</span></span>

2.  <span data-ttu-id="a0408-115">На основе текущей среды выберите свою начальную точку:</span><span class="sxs-lookup"><span data-stu-id="a0408-115">Next, based on your current environment, choose your starting point:</span></span>  

    - <span data-ttu-id="a0408-116">**Если вы обновляете Skype для бизнеса Online в Teams**, выполните действия, описанные в статье [Переход с Skype для бизнеса Online на Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span><span class="sxs-lookup"><span data-stu-id="a0408-116">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

    -  <span data-ttu-id="a0408-117">**Если вы обновляете локальную среду Skype для бизнеса**, вам потребуется выполнить дополнительные действия, чтобы настроить связь между локальными и Интернет-средами перед перемещением пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="a0408-117">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="a0408-118">Дополнительные сведения можно найти [в разделе Обновление локальной версии Skype для бизнеса для Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="a0408-118">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
