---
title: Прокси-серверы для группы или Скайп для бизнеса в Интернет
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
description: В этой статье сведения об использовании прокси-сервера с группами или Скайп для бизнеса.
ms.openlocfilehash: 1b25d0554ec8c5dca113be0842149dae11850b7e
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "29972214"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="c263c-103">Прокси-серверы для группы или Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="c263c-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="c263c-104">В этой статье рекомендации относительно использования прокси-сервера с группами или Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c263c-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="c263c-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="c263c-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="c263c-106">Когда речь идет о группы или Скайп для бизнес-трафика через прокси-серверы, корпорация Майкрософт рекомендует обход прокси-серверы.</span><span class="sxs-lookup"><span data-stu-id="c263c-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="c263c-107">Прокси-серверы не сделать группы или Скайп для бизнеса более безопасной так как трафика уже зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="c263c-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="c263c-108">И необходимости прокси-сервер может вызвать проблемы.</span><span class="sxs-lookup"><span data-stu-id="c263c-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="c263c-109">Проблемы, связанные с производительностью может быть вызвана среду через задержки и потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="c263c-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="c263c-110">Проблемы, такие как это приведет к отрицательным взаимодействия в таких групп или Скайп для бизнес-сценарии как аудио и видео, где важны потоков в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c263c-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="c263c-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="c263c-111">If you need to use a proxy server</span></span>

<span data-ttu-id="c263c-112">В некоторых организациях не имеют возможности обхода прокси-сервер для группы или Скайп для бизнес-трафика.</span><span class="sxs-lookup"><span data-stu-id="c263c-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="c263c-113">В этом случае следует обратить внимание на указанные выше проблемы.</span><span class="sxs-lookup"><span data-stu-id="c263c-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="c263c-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="c263c-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="c263c-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="c263c-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="c263c-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="c263c-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="c263c-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="c263c-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="c263c-118">Выполнив другие рекомендации, приведенные в нашей сети рекомендаций:</span><span class="sxs-lookup"><span data-stu-id="c263c-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="c263c-119">Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c263c-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="c263c-120">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c263c-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="c263c-121">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="c263c-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c263c-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c263c-122">Related topics</span></span>

[<span data-ttu-id="c263c-123">Оптимизация сети для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c263c-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 