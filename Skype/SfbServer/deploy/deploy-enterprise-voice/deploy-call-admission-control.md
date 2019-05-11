---
title: Развертывание контроля допуска звонков в Скайп for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях.
ms.openlocfilehash: 6ea527bc48f4a61bfe128eb935231200bb88b29f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892764"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="2077e-103">Развертывание контроля допуска звонков в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="2077e-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="2077e-104">Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях.</span><span class="sxs-lookup"><span data-stu-id="2077e-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="2077e-105">Для получения дополнительных сведений см [плана для контроля допуска звонков в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="2077e-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="2077e-106">Развертывание контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="2077e-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="2077e-107">Соберите все необходимые сведения для вашей топологии сети предприятия, как описано в статье [Пример: сбор требований для контроля допуска звонков в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2077e-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="2077e-108">Если вы еще не сделано, необходимо определить областей сети и веб-узлы и сопоставление подсетей с сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="2077e-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="2077e-109">Дополнительные сведения см [областей сети развернуть, сайты и подсети в Скайп для бизнеса](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="2077e-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="2077e-110">Создание профилей политики, как описано в [Создание профилей политики пропускной способности в Скайп для Business Server](create-bandwidth-policy-profiles.md) пропускной способности</span><span class="sxs-lookup"><span data-stu-id="2077e-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="2077e-111">Создание связей между областями, как описано в [Создание связей между областями в Скайп для Business Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="2077e-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="2077e-112">Создание маршрутов между областями сети, как описано в [Create interregional маршрутов между сетевыми в Скайп для Business Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="2077e-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="2077e-113">Создание политик межсайтового взаимодействия, как описано в [Создание политик межсайтового взаимодействия в Скайп для Business Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2077e-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="2077e-114">Включение службы контроля допуска звонков, как описано в [Включить контроль допуска звонков в Скайп для Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="2077e-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="2077e-115">Проверьте несколько окончательной настройки, убедитесь, что все настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="2077e-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="2077e-116">Дополнительные сведения см [развертывания контроля допуска звонков: последний контрольный список для Скайп для Business Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="2077e-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

