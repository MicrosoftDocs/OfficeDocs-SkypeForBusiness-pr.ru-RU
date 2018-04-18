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
ms.openlocfilehash: a4369208ab277e0eb5490a637421de605235a0cd
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="08d55-103">Прокси-серверы для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="08d55-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="08d55-104">[] В этой статье представлены рекомендации по использованию прокси-сервера в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="08d55-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="08d55-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="08d55-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="08d55-p101">Майкрософт рекомендует обходить прокси-серверы в трафике Skype для бизнеса. Прокси-серверы не служат дополнительной защитой в Skype для бизнеса, так как трафик уже зашифрован.</span><span class="sxs-lookup"><span data-stu-id="08d55-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="08d55-p102">Использование же прокси-сервера может вызвать, например, снижение производительности в среде из-за задержки и утери пакетов. В Skype для бизнеса важна непрерывность потоков в режиме реального времени, и такие проблемы ухудшат голосовую и видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="08d55-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="08d55-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="08d55-111">If you need to use a proxy server</span></span>

<span data-ttu-id="08d55-p103">В некоторых организациях нет возможности обойти прокси-сервер в трафике Skype для бизнеса. В этом случае следует обратить внимание на указанные выше проблемы.</span><span class="sxs-lookup"><span data-stu-id="08d55-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="08d55-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="08d55-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="08d55-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="08d55-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="08d55-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="08d55-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="08d55-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="08d55-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="08d55-118">следовать другим рекомендациям в руководствах по работе с сетями:</span><span class="sxs-lookup"><span data-stu-id="08d55-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="08d55-119">Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="08d55-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="08d55-120">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="08d55-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="08d55-121">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="08d55-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="08d55-122">Поставщики прокси-серверов со встроенной поддержкой или параметрами настройки Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="08d55-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="08d55-123">В этом разделе содержатся сведения о поставщиках прокси-серверов, предоставляющих продукты или службы, работающие с трафиком Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="08d55-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="08d55-124">Для организаций, использующих **решения прокси-серверов Bluecoat**, выпущено новое встроенное ПО, которое устраняет некоторые неполадки с:</span><span class="sxs-lookup"><span data-stu-id="08d55-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="08d55-125">перехватом SSL;</span><span class="sxs-lookup"><span data-stu-id="08d55-125">SSL interception</span></span>
    
  - <span data-ttu-id="08d55-126">проверками OCSP и SRL;</span><span class="sxs-lookup"><span data-stu-id="08d55-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="08d55-127">SIP по TLS;</span><span class="sxs-lookup"><span data-stu-id="08d55-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="08d55-128">поддержкой TURN.</span><span class="sxs-lookup"><span data-stu-id="08d55-128">support for TURN</span></span>
    
<span data-ttu-id="08d55-p104">Встроенную поддержку Bluecoat легко включить в Skype для бизнеса. Она позволяет идентифицировать нужный трафик и управлять им. Это обеспечит оптимальное взаимодействие для пользователей: проверку подлинности, обмен сигналами и поток трафика мультимедиа, и при этом не создаст проблем с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="08d55-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="08d55-131">Если Bluecoat прокси-сервер является частью топологию сети можно найти по следующей ссылке:https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="08d55-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="08d55-132">See also</span><span class="sxs-lookup"><span data-stu-id="08d55-132">Related topics</span></span>

[<span data-ttu-id="08d55-133">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="08d55-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 