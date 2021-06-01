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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: В этой статье содержится информация об использовании прокси-сервера с Skype для бизнеса.
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240418"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="4ab3f-103">Прокси-серверы для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4ab3f-103">Proxy servers for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="4ab3f-104">В этой статье приводится руководство по использованию прокси-сервера с Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4ab3f-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="4ab3f-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="4ab3f-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="4ab3f-106">Майкрософт рекомендует обходить прокси-серверы в трафике Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4ab3f-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="4ab3f-107">Прокси-прокси не делают Skype для бизнеса более безопасными, так как трафик уже зашифрован.</span><span class="sxs-lookup"><span data-stu-id="4ab3f-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="4ab3f-108">Наличие прокси-сервера может стать причиной проблем.</span><span class="sxs-lookup"><span data-stu-id="4ab3f-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="4ab3f-109">Проблемы, связанные с производительностью, могут быть связаны с задержкой и потерей пакетов.</span><span class="sxs-lookup"><span data-stu-id="4ab3f-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="4ab3f-110">Такие проблемы привязают к отрицательным результатам в таких сценариях Teams или Skype для бизнеса, как звук и видео, где важны потоки в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="4ab3f-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="4ab3f-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="4ab3f-111">If you need to use a proxy server</span></span>

<span data-ttu-id="4ab3f-p103">В некоторых организациях нет возможности обойти прокси-сервер в трафике Skype для бизнеса. В этом случае следует обратить внимание на указанные выше проблемы.</span><span class="sxs-lookup"><span data-stu-id="4ab3f-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="4ab3f-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="4ab3f-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="4ab3f-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="4ab3f-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="4ab3f-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="4ab3f-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="4ab3f-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="4ab3f-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="4ab3f-118">Следуйте другим рекомендациям в наших рекомендациях по сети:</span><span class="sxs-lookup"><span data-stu-id="4ab3f-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="4ab3f-119">Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4ab3f-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="4ab3f-120">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4ab3f-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="4ab3f-121">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="4ab3f-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4ab3f-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4ab3f-122">Related topics</span></span>

[<span data-ttu-id="4ab3f-123">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4ab3f-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 
