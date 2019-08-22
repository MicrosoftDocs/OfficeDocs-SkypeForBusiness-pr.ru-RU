---
title: Развертывание пограничного сервера в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Сводка: сведения о развертывании пограничного сервера или пограничного пула в среде Skype для бизнеса Server.'
ms.openlocfilehash: 03cb3f1bc4a938a698c28332b4781d08434bc52f
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "36492974"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="f7027-103">Развертывание пограничного сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f7027-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f7027-104">**Сводка:** Сведения о развертывании пограничного сервера или пограничного пула в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f7027-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="f7027-105">Зачем развертывать пограничный сервер или пограничный пул в среду Skype для бизнеса Server?</span><span class="sxs-lookup"><span data-stu-id="f7027-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="f7027-106">Это необходимо, если вам понадобятся внешние пользователи, которые не вошли в внутреннюю сеть Организации, чтобы обеспечить взаимодействие с внутренними пользователями.</span><span class="sxs-lookup"><span data-stu-id="f7027-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="f7027-107">Такие внешние пользователи могут быть аутентифицированными и анонимными удаленными пользователями, федеративными партнерами или другими мобильными клиентами.</span><span class="sxs-lookup"><span data-stu-id="f7027-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="f7027-108">Контрольный список развертывания для пограничного сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f7027-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="f7027-109">Как отмечалось выше, в приложении пограничного сервера в среде Skype для бизнеса Server осуществляется переход на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="f7027-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="f7027-110">Этот контрольный список содержит общие сведения о задачах, которые необходимо выполнить, и ссылки на подробные инструкции.</span><span class="sxs-lookup"><span data-stu-id="f7027-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="f7027-111">Надеемся, что вы начали [планировать развертывание пограничного сервера в разделе Skype для бизнеса Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="f7027-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="f7027-112">В противном случае многие из вещей, на которые мы будем ссылаться, подробно описаны здесь.</span><span class="sxs-lookup"><span data-stu-id="f7027-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="f7027-113">Раздел Развертывание содержит только процедуры, поэтому если вы хотите узнать, какие действия выполняются за этими инструкциями, планирование — это место для начала.</span><span class="sxs-lookup"><span data-stu-id="f7027-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="f7027-114">В этой документации также предполагается, что вы уже завершили простое развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f7027-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="f7027-115">Вы можете выполнить это развертывание параллельно с ребром, но вам потребуется сначала выполнить эти действия, и тогда вы сможете внести изменения в топологию за границу, описанную здесь.</span><span class="sxs-lookup"><span data-stu-id="f7027-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="f7027-116">Далее перечислены ссылки на описание высокоуровных действий, которые необходимо выполнить:</span><span class="sxs-lookup"><span data-stu-id="f7027-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="f7027-117">Требования к системе пограничного сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f7027-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="f7027-118">Требования к окружающей среде пограничного сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f7027-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="f7027-119">Создание топологии Edge для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f7027-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="f7027-120">Развертывание пограничных серверов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f7027-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="f7027-121">Проверка пограничного развертывания в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f7027-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

