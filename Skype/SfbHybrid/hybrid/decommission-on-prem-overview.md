---
title: Прекращение использования локальной среды Skype для бизнеса
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
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656685"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="5e676-103">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5e676-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="5e676-104">Если ваша организация использует Teams или Skype для бизнеса Online с локальной развертыванием Skype для бизнеса Server, вы можете полностью перенести эти среды в облако, а затем завершить локальное развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5e676-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="5e676-105">Перед выводом из эксплуатации локальной среды [](configure-hybrid-connectivity.md) необходимо настроить гибридную связь между локальной развертыванием и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e676-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="5e676-106">После настройки гибридного подключения можно перенести пользователей в облако, перенося собрания из локального и перенося любые контакты из Skype для бизнеса Server в Teams.</span><span class="sxs-lookup"><span data-stu-id="5e676-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="5e676-107">Настройка гибридного подключения — это необходимый шаг для переноса пользователей из локального в облако и обеспечения полной функциональности Teams.</span><span class="sxs-lookup"><span data-stu-id="5e676-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="5e676-108">Чтобы завершить переход из локальной среды в облако и вычистить локальное окружение Skype для бизнеса Server, необходимо выполнить следующие действия в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="5e676-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="5e676-109">**Этап 1.**</span><span class="sxs-lookup"><span data-stu-id="5e676-109">**Step 1.**</span></span> <span data-ttu-id="5e676-110">[Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="5e676-110">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="5e676-111">**Шаг 2.**</span><span class="sxs-lookup"><span data-stu-id="5e676-111">**Step 2.**</span></span> <span data-ttu-id="5e676-112">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="5e676-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="5e676-113">**Шаг 3.**</span><span class="sxs-lookup"><span data-stu-id="5e676-113">**Step 3.**</span></span> <span data-ttu-id="5e676-114">[Перемещение конечных точек гибридного приложения из локального в интернет.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="5e676-114">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="5e676-115">**Этап 4.**</span><span class="sxs-lookup"><span data-stu-id="5e676-115">**Step 4.**</span></span> <span data-ttu-id="5e676-116">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="5e676-116">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

