---
title: Развертывание пограничного сервера в Skype для бизнеса Server 2015.
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Сводка: Узнайте, как развернуть пограничный сервер или пограничный пул в вашей Скайп среды Business Server 2015.'
ms.openlocfilehash: 38eb0344488512a47f4dc21223d881c15f618e22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-edge-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d5727-103">Развертывание пограничного сервера в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d5727-103">Deploy Edge Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d5727-104">**Сводка:** Узнайте, как развернуть пограничный сервер или пограничный пул в вашей Скайп среды Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d5727-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment.</span></span>
  
<span data-ttu-id="d5727-105">Почему целесообразно развертывать пограничный сервер или пограничный пул в вашей Скайп среды Business Server 2015?</span><span class="sxs-lookup"><span data-stu-id="d5727-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment?</span></span> <span data-ttu-id="d5727-106">Это необходимо, если требуется, чтобы внешние пользователи, которые не вошли во внутреннюю сеть организации, могли взаимодействовать с внутренними пользователями.</span><span class="sxs-lookup"><span data-stu-id="d5727-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="d5727-107">Такие внешние пользователи могут быть аутентифицированными и анонимными удаленными пользователями, федеративными партнерами или другими мобильными клиентами.</span><span class="sxs-lookup"><span data-stu-id="d5727-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server-2015"></a><span data-ttu-id="d5727-108">Контрольный список развертывания для пограничного сервера, для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d5727-108">Deployment checklist for the Edge, for Skype for Business Server 2015</span></span>

<span data-ttu-id="d5727-109">Как было указано выше,, много переходит в развертывании пограничного сервера для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d5727-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server 2015.</span></span> <span data-ttu-id="d5727-110">Этот контрольный список представлен обзор задач, которые необходимо выполнить и ссылки на более подробное описание действий.</span><span class="sxs-lookup"><span data-stu-id="d5727-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="d5727-111">Мы желаем начали в разделе [Планирование для развертывания пограничного сервера в Скайп для Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="d5727-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="d5727-112">В противном случае действия обращении к приведено подробное описание существует.</span><span class="sxs-lookup"><span data-stu-id="d5727-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="d5727-113">В разделе Развертывание содержит только процедуры, если вы хотите узнать обоснование эти этапы планирования — это место, чтобы начать.</span><span class="sxs-lookup"><span data-stu-id="d5727-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="d5727-114">В этой документации также предполагает, что вы также сделали базовой развертывания Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d5727-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server 2015.</span></span> <span data-ttu-id="d5727-115">Могут делать этого развертывания-одновременно пограничного сервера, но нужно сначала выполните эти действия и затем вы сможете вносить изменения топологии для пограничных серверов, описанных здесь.</span><span class="sxs-lookup"><span data-stu-id="d5727-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="d5727-116">Далее перечислены ссылки на описание высокоуровных действий, которые необходимо выполнить:</span><span class="sxs-lookup"><span data-stu-id="d5727-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="d5727-117">Пограничный сервер требования к системе в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d5727-117">Edge Server system requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="d5727-118">Пограничный сервер окружающей среды требования в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d5727-118">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="d5727-119">Создание топологии пограничных Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d5727-119">Create your Edge topology for Skype for Business Server 2015</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="d5727-120">Развертывание пограничных серверов в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d5727-120">Deploy Edge Servers in Skype for Business Server 2015</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="d5727-121">Проверка развертывания пограничного сервера в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d5727-121">Validate your Edge deployment in Skype for Business Server 2015</span></span>](validate-edge-deployment.md)
    

