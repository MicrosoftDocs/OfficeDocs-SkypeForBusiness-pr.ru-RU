---
title: Прокси-серверы для Teams или Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: M365-collaboration
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: В этой статье сведения об использовании прокси-сервера с группами или Скайп для бизнеса.
ms.openlocfilehash: 7ba522e2f49be0ae9846638839193d9c6c3a24b3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465286"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="7fab2-103">Прокси-серверы для Teams или Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7fab2-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="7fab2-104">В этой статье рекомендации относительно использования прокси-сервера с группами или Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7fab2-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="7fab2-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="7fab2-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="7fab2-106">Когда речь идет о группы или Скайп для бизнес-трафика через прокси-серверы, корпорация Майкрософт рекомендует обход прокси-серверы.</span><span class="sxs-lookup"><span data-stu-id="7fab2-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="7fab2-107">Прокси-серверы не сделать группы или Скайп для бизнеса более безопасной так как трафика уже зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="7fab2-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="7fab2-108">И необходимости прокси-сервер может вызвать проблемы.</span><span class="sxs-lookup"><span data-stu-id="7fab2-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="7fab2-109">Проблемы, связанные с производительностью может быть вызвана среду через задержки и потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="7fab2-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="7fab2-110">Проблемы, такие как это приведет к отрицательным взаимодействия в таких групп или Скайп для бизнес-сценарии как аудио и видео, где важны потоков в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="7fab2-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="7fab2-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="7fab2-111">If you need to use a proxy server</span></span>

<span data-ttu-id="7fab2-112">В некоторых организациях не имеют возможности обхода прокси-сервер для группы или Скайп для бизнес-трафика.</span><span class="sxs-lookup"><span data-stu-id="7fab2-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="7fab2-113">В этом случае следует обратить внимание на указанные выше проблемы.</span><span class="sxs-lookup"><span data-stu-id="7fab2-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="7fab2-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="7fab2-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="7fab2-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="7fab2-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="7fab2-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="7fab2-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="7fab2-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="7fab2-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="7fab2-118">Выполнив другие рекомендации, приведенные в нашей сети рекомендаций:</span><span class="sxs-lookup"><span data-stu-id="7fab2-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="7fab2-119">Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7fab2-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="7fab2-120">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7fab2-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="7fab2-121">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="7fab2-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7fab2-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7fab2-122">Related topics</span></span>

[<span data-ttu-id="7fab2-123">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7fab2-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 