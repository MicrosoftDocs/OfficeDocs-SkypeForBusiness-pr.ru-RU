---
title: Развертывание контроля допуска звонков в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях. Для получения дополнительных сведений ознакомьтесь с разделом Plan для контроля допуска звонков в Скайп для Business Server 2015.
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="2d7d7-104">Развертывание контроля допуска звонков в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d7d7-104">Deploy call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2d7d7-105">Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="2d7d7-106">Для получения дополнительных сведений см [плана для контроля допуска звонков в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-106">For more information, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="2d7d7-107">Развертывание контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="2d7d7-107">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="2d7d7-108">Соберите все необходимые сведения для вашей топологии сети предприятия, как описано в статье [Пример: сбор требований для контроля допуска звонков в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="2d7d7-109">Если вы еще не сделано, необходимо определить областей сети и веб-узлы и сопоставление подсетей с сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-109">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="2d7d7-110">Дополнительные сведения см [областей сети развернуть, сайты и подсети в Скайп для бизнеса 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-110">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
3. <span data-ttu-id="2d7d7-111">Создание профилей политики, как описано в [Создание профилей политики пропускной способности в Скайп для Business Server 2015](create-bandwidth-policy-profiles.md) пропускной способности</span><span class="sxs-lookup"><span data-stu-id="2d7d7-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="2d7d7-112">Создание связей между областями, как описано в [Создание связей между областями в Скайп для Business Server 2015](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="2d7d7-113">Создание маршрутов между областями сети, как описано в [Create interregional маршрутов между сетевыми в Скайп для Business Server 2015](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="2d7d7-114">Создание политик межсайтового взаимодействия, как описано в [Создание политик межсайтового взаимодействия в Скайп для Business Server 2015](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="2d7d7-115">Включение контроля допуска звонков, как описано в [Включить контроль допуска звонков в Скайп для Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="2d7d7-116">Проверьте несколько окончательной настройки, убедитесь, что все настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-116">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="2d7d7-117">Дополнительные сведения см [развертывания контроля допуска звонков: последний контрольный список для Скайп для Business Server 2015](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-117">For details, see [Call admission control deployment: final checklist for Skype for Business Server 2015](final-checklist.md).</span></span>
    

