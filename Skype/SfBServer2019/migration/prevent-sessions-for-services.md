---
title: Запрет сеансов для служб
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Вы можете использовать панель управления "старые" для предотвращения новых сеансов для всех устаревших служб, запущенных на конкретном компьютере, или для предотвращения новых сеансов для определенной устаревшей службы.
ms.openlocfilehash: 4728f68c8f7b9392b99a6a49eefe699fa48a4d47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301218"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="5e42e-103">Запрет сеансов для служб</span><span class="sxs-lookup"><span data-stu-id="5e42e-103">Prevent sessions for services</span></span>

<span data-ttu-id="5e42e-104">Вы можете использовать панель управления "старые" для предотвращения новых сеансов для всех устаревших служб, запущенных на конкретном компьютере, или для предотвращения новых сеансов для определенной устаревшей службы.</span><span class="sxs-lookup"><span data-stu-id="5e42e-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="5e42e-105">Запрещение новых сеансов для служб на компьютере</span><span class="sxs-lookup"><span data-stu-id="5e42e-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="5e42e-106">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. 2019.</span><span class="sxs-lookup"><span data-stu-id="5e42e-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="5e42e-107">Откройте панель управления "Skype для бизнеса".</span><span class="sxs-lookup"><span data-stu-id="5e42e-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="5e42e-108">В левой панели навигации щелкните **Топология**, а затем **Состояние**. </span><span class="sxs-lookup"><span data-stu-id="5e42e-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="5e42e-109">На странице " **состояние** " выполните сортировку или поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущены службы, для которых вы хотите запретить новые сеансы, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="5e42e-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="5e42e-110">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="5e42e-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="5e42e-111">Нажмите кнопку **запретить новые сеансы для всех служб**.</span><span class="sxs-lookup"><span data-stu-id="5e42e-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="5e42e-112">Запрещение новых сеансов для конкретной службы</span><span class="sxs-lookup"><span data-stu-id="5e42e-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="5e42e-113">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. 2019.</span><span class="sxs-lookup"><span data-stu-id="5e42e-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="5e42e-114">Откройте панель управления "Skype для бизнеса".</span><span class="sxs-lookup"><span data-stu-id="5e42e-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="5e42e-115">В левой панели навигации щелкните **Топология**, а затем **Состояние**. </span><span class="sxs-lookup"><span data-stu-id="5e42e-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="5e42e-116">На странице " **состояние** " выполните сортировку и поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущена служба, которую вы хотите запустить или остановить, а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="5e42e-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="5e42e-117">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5e42e-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="5e42e-118">При необходимости отсортируйте список служб и выберите службу, для которой вы хотите запретить новые сеансы.</span><span class="sxs-lookup"><span data-stu-id="5e42e-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="5e42e-119">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="5e42e-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="5e42e-120">Выберите команду **запретить новые сеансы для службы**.</span><span class="sxs-lookup"><span data-stu-id="5e42e-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="5e42e-121">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5e42e-121">Click **Close**.</span></span>
    

