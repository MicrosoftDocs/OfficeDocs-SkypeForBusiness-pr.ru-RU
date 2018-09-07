---
title: Прокси-серверы для Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: В этой статье представлены рекомендации по использованию прокси-сервера в Skype для бизнеса.
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850016"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="98df9-103">Прокси-серверы для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="98df9-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="98df9-104">[] В этой статье представлены рекомендации по использованию прокси-сервера в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="98df9-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="98df9-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="98df9-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="98df9-p101">Майкрософт рекомендует обходить прокси-серверы в трафике Skype для бизнеса. Прокси-серверы не служат дополнительной защитой в Skype для бизнеса, так как трафик уже зашифрован.</span><span class="sxs-lookup"><span data-stu-id="98df9-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="98df9-p102">Использование же прокси-сервера может вызвать, например, снижение производительности в среде из-за задержки и утери пакетов. В Skype для бизнеса важна непрерывность потоков в режиме реального времени, и такие проблемы ухудшат голосовую и видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="98df9-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="98df9-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="98df9-111">If you need to use a proxy server</span></span>

<span data-ttu-id="98df9-p103">В некоторых организациях нет возможности обойти прокси-сервер в трафике Skype для бизнеса. В этом случае следует обратить внимание на указанные выше проблемы.</span><span class="sxs-lookup"><span data-stu-id="98df9-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="98df9-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="98df9-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="98df9-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="98df9-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="98df9-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="98df9-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="98df9-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="98df9-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="98df9-118">следовать другим рекомендациям в руководствах по работе с сетями:</span><span class="sxs-lookup"><span data-stu-id="98df9-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="98df9-119">Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="98df9-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="98df9-120">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="98df9-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="98df9-121">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="98df9-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="98df9-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="98df9-122">Related topics</span></span>

[<span data-ttu-id="98df9-123">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="98df9-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 