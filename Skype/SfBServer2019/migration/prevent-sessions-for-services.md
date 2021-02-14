---
title: Запрет сеансов для служб
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы можете использовать устаревшую панель управления для предотвращения новых сеансов для всех устаревших служб, запущенных на определенном компьютере, или для предотвращения новых сеансов для определенной устаревшей службы.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752291"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="92eec-103">Запрет сеансов для служб</span><span class="sxs-lookup"><span data-stu-id="92eec-103">Prevent sessions for services</span></span>

<span data-ttu-id="92eec-104">Вы можете использовать устаревшую панель управления для предотвращения новых сеансов для всех устаревших служб, запущенных на определенном компьютере, или для предотвращения новых сеансов для определенной устаревшей службы.</span><span class="sxs-lookup"><span data-stu-id="92eec-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="92eec-105">Предотвращение новых сеансов для служб на компьютере</span><span class="sxs-lookup"><span data-stu-id="92eec-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="92eec-106">С помощью учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначенной роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, на котором развернут Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="92eec-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="92eec-107">Откройте панель управления Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="92eec-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="92eec-108">В левой панели навигации щелкните **"Топология"** и выберите **"Состояние".**</span><span class="sxs-lookup"><span data-stu-id="92eec-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="92eec-109">На странице **Состояние** выполните сортировку или поиск по списку, чтобы найти компьютер, на котором выполняются службы, для которых нужно запретить новые сеансы, а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="92eec-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="92eec-110">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="92eec-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="92eec-111">Щелкните **Запретить новые сеансы для всех служб**.</span><span class="sxs-lookup"><span data-stu-id="92eec-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="92eec-112">Запрет новых сеансов для определенной службы</span><span class="sxs-lookup"><span data-stu-id="92eec-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="92eec-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="92eec-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="92eec-114">Откройте панель управления Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="92eec-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="92eec-115">В левой панели навигации щелкните **"Топология"** и выберите **"Состояние".**</span><span class="sxs-lookup"><span data-stu-id="92eec-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="92eec-116">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="92eec-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="92eec-117">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="92eec-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="92eec-118">Отсортируйте список служб, если это необходимо, и щелкните службу, для которой вы хотите запретить новые сеансы.</span><span class="sxs-lookup"><span data-stu-id="92eec-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="92eec-119">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="92eec-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="92eec-120">Щелкните **Запретить новые сеансы для службы**.</span><span class="sxs-lookup"><span data-stu-id="92eec-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="92eec-121">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="92eec-121">Click **Close**.</span></span>
    

