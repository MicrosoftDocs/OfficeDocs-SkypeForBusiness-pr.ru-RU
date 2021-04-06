---
title: Вывод из эксплуатации локальной среды Skype для бизнеса
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Инструкции по выводу из эксплуатации локальной среды Skype для бизнеса.
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593902"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="1daca-103">Вывод из эксплуатации локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1daca-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="1daca-104">Если ваша организация использует Teams или Skype для бизнеса Online с локальной развертыванием Skype для бизнеса Server, вы можете полностью перенести эти среды в облако, а затем завершить локальное развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1daca-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="1daca-105">Перед выводом из эксплуатации локальной среды [](configure-hybrid-connectivity.md) необходимо настроить гибридную связь между локальной развертыванием и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1daca-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="1daca-106">После настройки гибридного подключения можно перенести пользователей в облако, перенося собрания из локального и перенося любые контакты из Skype для бизнеса Server в Teams.</span><span class="sxs-lookup"><span data-stu-id="1daca-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="1daca-107">Настройка гибридного подключения — это необходимый шаг для переноса пользователей из локального в облако и обеспечения полной функциональности Teams.</span><span class="sxs-lookup"><span data-stu-id="1daca-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="1daca-108">Чтобы завершить переход из локальной среды в облако и вычистить локальное окружение Skype для бизнеса Server, необходимо выполнить следующие действия в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="1daca-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="1daca-109">**Этап 1.**</span><span class="sxs-lookup"><span data-stu-id="1daca-109">**Step 1.**</span></span> <span data-ttu-id="1daca-110">[Перемещение всех необходимых пользователей и конечных точек приложения](decommission-move-on-prem-users.md)из локального в интернет.</span><span class="sxs-lookup"><span data-stu-id="1daca-110">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="1daca-111">**Шаг 2.**</span><span class="sxs-lookup"><span data-stu-id="1daca-111">**Step 2.**</span></span> <span data-ttu-id="1daca-112">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="1daca-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="1daca-113">**Шаг 3.**</span><span class="sxs-lookup"><span data-stu-id="1daca-113">**Step 3.**</span></span> <span data-ttu-id="1daca-114">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="1daca-114">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

