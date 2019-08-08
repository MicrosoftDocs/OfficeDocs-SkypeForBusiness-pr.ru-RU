---
title: Развертывание элемента управления допуском звонков в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях.
ms.openlocfilehash: 0b2df103c432cd6b304f93b3a36af6e87c4bc2e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233192"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="6245a-103">Развертывание элемента управления допуском звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6245a-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="6245a-104">Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях.</span><span class="sxs-lookup"><span data-stu-id="6245a-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="6245a-105">Дополнительные сведения можно найти [в разделе Планирование управления допуском звонков в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="6245a-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="6245a-106">Развертывание контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="6245a-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="6245a-107">Соберите все необходимые данные для топологии корпоративной сети, как описано в [примере: сбор требований для управления допуском звонков в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6245a-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="6245a-108">Если вы еще не сделали этого, необходимо определить регионы сети и сайты, а затем связать подсети с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="6245a-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="6245a-109">Подробные сведения можно найти [в разделе Развертывание регионов сети, сайтов и подсетей в Skype для бизнеса](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="6245a-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="6245a-110">Создание профилей политики пропускной способности в соответствии с подробными сведениями [Создание профилей политики пропускной способности в Skype для бизнеса Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6245a-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="6245a-111">Создание ссылок на сетевой регион, подробно описанных в разделе [Создание ссылок на сетевой регион в Skype для бизнеса Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="6245a-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="6245a-112">Создавайте маршруты между регионами, как описано в разделе [Создание межсетевых маршрутов в Skype для бизнеса Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="6245a-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="6245a-113">Создавайте политики межсетевого соединения, как описано в этой задаче: [Создание политик межсетевого соединения в Skype для бизнеса Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6245a-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="6245a-114">Включите управление допуском звонков, как описано в подокне [включения управления допуском звонков в Skype для бизнеса Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="6245a-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="6245a-115">Проверьте некоторые параметры, чтобы убедиться, что все настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="6245a-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="6245a-116">Дополнительные сведения можно найти в разделе [Развертывание элемента управления допуском звонков: последний контрольный список для Skype для бизнеса Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="6245a-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

