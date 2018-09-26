---
title: Запрет сеансов для служб
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно запретить установку новых сеансов для устаревших служб, работающих на определенном компьютере или запретить установку новых сеансов для определенной службы прежних версий, можно использовать устаревшим установкам панель управления.
ms.openlocfilehash: af4605f65d7cabe187696eda20bd9082ab73ad02
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027216"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="c03af-103">Запрет сеансов для служб</span><span class="sxs-lookup"><span data-stu-id="c03af-103">Prevent sessions for services</span></span>

<span data-ttu-id="c03af-104">Можно запретить установку новых сеансов для устаревших служб, работающих на определенном компьютере или запретить установку новых сеансов для определенной службы прежних версий, можно использовать устаревшим установкам панель управления.</span><span class="sxs-lookup"><span data-stu-id="c03af-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="c03af-105">Чтобы запретить установку новых сеансов для служб на компьютере</span><span class="sxs-lookup"><span data-stu-id="c03af-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="c03af-106">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c03af-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="c03af-107">Откройте Скайп для панели управления бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c03af-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="c03af-108">В левой панели навигации щелкните **Топология**, а затем **Состояние**. </span><span class="sxs-lookup"><span data-stu-id="c03af-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="c03af-109">На странице " **состояние** " Сортировка или поиска по списку как требуется на компьютере, на котором запущены службы, для которых вы хотите запретить новые сеансы, а затем нажмите кнопку Найти.</span><span class="sxs-lookup"><span data-stu-id="c03af-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="c03af-110">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="c03af-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="c03af-111">Щелкните **Запретить установку новых сеансов для всех служб**.</span><span class="sxs-lookup"><span data-stu-id="c03af-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="c03af-112">Чтобы запретить установку новых сеансов для определенной службы</span><span class="sxs-lookup"><span data-stu-id="c03af-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="c03af-113">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c03af-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="c03af-114">Откройте Скайп для панели управления бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c03af-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="c03af-115">В левой панели навигации щелкните **Топология**, а затем **Состояние**. </span><span class="sxs-lookup"><span data-stu-id="c03af-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="c03af-116">На странице **состояния** , сортировки или поиска по списку, чтобы найти компьютер, на котором работает служба необходимо запустить или остановить и нажмите кнопку.</span><span class="sxs-lookup"><span data-stu-id="c03af-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="c03af-117">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c03af-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="c03af-118">Отсортируйте список служб, если это необходимо и выберите службу, для которого вы хотите запретить новые сеансы.</span><span class="sxs-lookup"><span data-stu-id="c03af-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="c03af-119">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="c03af-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="c03af-120">Щелкните **запретить новые сеансы для службы**.</span><span class="sxs-lookup"><span data-stu-id="c03af-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="c03af-121">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c03af-121">Click **Close**.</span></span>
    

