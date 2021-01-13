---
title: Развертывание сервера Edge Server в Skype для бизнеса Server
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: Сводка. Узнайте, как развернуть в среде Skype для бизнеса Server edge server или пул.
ms.openlocfilehash: edd2ff501320c4252b8032d1528ede7b83b8fcd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804389"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="090ce-103">Развертывание сервера Edge Server в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090ce-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="090ce-104">**Сводка:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span><span class="sxs-lookup"><span data-stu-id="090ce-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="090ce-105">Зачем развертывать в среде Skype для бизнеса Server edge Server или пул?</span><span class="sxs-lookup"><span data-stu-id="090ce-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="090ce-106">Это необходимо, если внешние пользователи, которые не вошли во внутреннюю сеть организации, должны иметь возможность взаимодействовать с внутренними пользователями.</span><span class="sxs-lookup"><span data-stu-id="090ce-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="090ce-107">Эти внешние пользователи могут быть аутентификацией и анонимными удаленными пользователями, федератерными партнерами или другими мобильными клиентами.</span><span class="sxs-lookup"><span data-stu-id="090ce-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="090ce-108">Контрольный список развертывания для edge для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090ce-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="090ce-109">Как уже было отмечено выше, в развертывании edge Server для Skype для бизнеса Server многое происходит.</span><span class="sxs-lookup"><span data-stu-id="090ce-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="090ce-110">Этот контрольный список предоставляет обзор задач, которые необходимо выполнить, и ссылки на более подробные инструкции.</span><span class="sxs-lookup"><span data-stu-id="090ce-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="090ce-111">Мы надеемся, что вы начали работу в разделе "Планирование развертывания edge [Server в Skype для бизнеса Server".](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)</span><span class="sxs-lookup"><span data-stu-id="090ce-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="090ce-112">В этом случае многие из ссылок на них подробно описаны.</span><span class="sxs-lookup"><span data-stu-id="090ce-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="090ce-113">Раздел развертывания содержит только процедуры, поэтому, если вы хотите узнать причину этих действий, необходимо начать планирование.</span><span class="sxs-lookup"><span data-stu-id="090ce-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="090ce-114">В этой документации также предполагается, что базовое развертывание Skype для бизнеса Server уже завершено.</span><span class="sxs-lookup"><span data-stu-id="090ce-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="090ce-115">Возможно, вы будете выполнять это развертывание рядом с edge, но сначала вам потребуется выполнять эти действия, а затем вы сможете внести изменения в топологию для edge, которые описаны здесь.</span><span class="sxs-lookup"><span data-stu-id="090ce-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="090ce-116">Ниже следуют высокоуровневые шаги, которые необходимо выполнять, и места, где вы найдете эти действия:</span><span class="sxs-lookup"><span data-stu-id="090ce-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="090ce-117">Требования к системе для сервера Edge Server в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090ce-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="090ce-118">Требования к среде для edge Server в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090ce-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="090ce-119">Создание топологии edge для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090ce-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="090ce-120">Развертывание серверов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090ce-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="090ce-121">Проверка развертывания edge в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090ce-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

