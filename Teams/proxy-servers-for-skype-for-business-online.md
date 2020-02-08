---
title: Прокси-серверы для Teams или Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: В этой статье приводятся сведения об использовании прокси-сервера в Teams или Skype для бизнеса.
ms.openlocfilehash: ca81c32064406af0e5bc3d614566a96ec5646a91
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863190"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="dab75-103">Прокси-серверы для Teams или Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="dab75-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="dab75-104">В этой статье приводятся рекомендации по использованию прокси-сервера в Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dab75-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="dab75-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="dab75-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="dab75-p101">При поступлении трафика в Teams или Skype для бизнеса через прокси-серверы Корпорация Майкрософт рекомендует обойти прокси-серверы. Прокси-серверы не делают Teams или Skype для бизнеса более надежными, так как трафик уже зашифрован.</span><span class="sxs-lookup"><span data-stu-id="dab75-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="dab75-p102">А у прокси-сервера могут возникнуть проблемы. Проблемы, связанные с производительностью, могут быть введены в среду с помощью задержки и потери пакетов. Такие проблемы могут привести к негативной работе в таких рабочих группах и сценариях Skype для бизнеса, как звуковые и видеофайлы, где очень важны потоки в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="dab75-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="dab75-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="dab75-111">If you need to use a proxy server</span></span>

<span data-ttu-id="dab75-p103">В некоторых организациях нет возможности обходить прокси-сервер для Teams и трафик Skype для бизнеса. Если это так, следует помнить о проблемах, упомянутых выше.</span><span class="sxs-lookup"><span data-stu-id="dab75-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="dab75-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="dab75-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="dab75-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="dab75-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="dab75-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="dab75-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="dab75-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="dab75-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="dab75-118">Ниже указаны другие рекомендации по работе в сети: [Подготовка сети организации для Teams](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="dab75-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="dab75-119">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="dab75-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dab75-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dab75-120">Related topics</span></span>

[<span data-ttu-id="dab75-121">Принципы подключения к сети в Office 365</span><span class="sxs-lookup"><span data-stu-id="dab75-121">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="dab75-122">Подготовка сети организации к использованию Teams</span><span class="sxs-lookup"><span data-stu-id="dab75-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)
