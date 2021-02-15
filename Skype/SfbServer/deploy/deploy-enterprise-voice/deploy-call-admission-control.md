---
title: Развертывание контроля допуска звонков в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Контроль допуска вызовов (CAC) — это решение, которое определяет, можно ли установить сеанс в режиме реального времени на основе доступной пропускной способности для предотвращения неудовлетворительного качества звука и видео для пользователей в захламляемой сети.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836889"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="1446f-103">Развертывание контроля допуска звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1446f-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="1446f-104">Контроль допуска вызовов (CAC) — это решение, которое определяет, можно ли установить сеанс в режиме реального времени на основе доступной пропускной способности для предотвращения неудовлетворительного качества звука и видео для пользователей в захламляемой сети.</span><span class="sxs-lookup"><span data-stu-id="1446f-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="1446f-105">Дополнительные сведения см. в [сведениях о планировании контроля допуска звонков в Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="1446f-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="1446f-106">Развертывание контроля допуска вызовов</span><span class="sxs-lookup"><span data-stu-id="1446f-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="1446f-107">Соберите все необходимые сведения для корпоративной сетевой топологии, как описано в примере: сбор требований для контроля допуска звонков [в Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="1446f-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="1446f-108">Если это еще не сделано, необходимо определить области сети и сайты и связать подсети с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="1446f-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="1446f-109">Дополнительные сведения см. в сведениях о развертывании [областей сети, сайтов и подсетей в Skype для бизнеса.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="1446f-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="1446f-110">Создание профилей политик пропускной способности, как описано в описании создания профилей политик пропускной способности [в Skype для бизнеса Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1446f-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="1446f-111">Создание связей между областями сети, как описано в описании создания связей между областями [сети в Skype для бизнеса Server.](create-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="1446f-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="1446f-112">Создание маршрутов между регионами сети, как описано в описании создания межрегиональных сетевых маршрутов [в Skype для бизнеса Server.](create-network-interregional-routes.md)</span><span class="sxs-lookup"><span data-stu-id="1446f-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="1446f-113">Создайте межсайтовую сетевую политику, как описано в описании создания сетевых политик межсайтов [в Skype для бизнеса Server.](create-network-intersite-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1446f-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="1446f-114">Включить контроль допуска звонков, как описано в подробном описании этой [темы, в Skype для бизнеса Server.](enable-call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="1446f-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="1446f-115">Проверьте несколько окончательных параметров, чтобы убедиться, что все настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="1446f-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="1446f-116">Подробные сведения см. в развертывании контроля допуска [звонков: окончательный контрольный](final-checklist.md)список для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1446f-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

