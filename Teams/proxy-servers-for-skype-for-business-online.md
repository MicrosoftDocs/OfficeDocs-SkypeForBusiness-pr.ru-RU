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
- seo-marvel-apr2020
description: В этой статье приводится информация об использовании прокси-сервера с Microsoft Teams или Skype для бизнеса.
ms.openlocfilehash: 3d8e2e067cce4214f51ee54ec08bafa1f4100770
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665961"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="027ac-103">Прокси-серверы для Teams или Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="027ac-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="027ac-104">Эта статья содержит рекомендации по использованию прокси-сервера в Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="027ac-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="027ac-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="027ac-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="027ac-p101">Если речь идет о трафике Teams или Skype для бизнеса через прокси-прокси, Майкрософт рекомендует обходить прокси-прокси. Прокси-решения не делают Teams и Skype для бизнеса более безопасными, так как трафик уже зашифрован.</span><span class="sxs-lookup"><span data-stu-id="027ac-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="027ac-p102">Наличие прокси-сервера может вызвать проблемы. Проблемы, связанные с производительностью, могут быть введены в среду за счет задержки и потери пакетов. Такие проблемы привязают к отрицательным результатам в таких сценариях Teams или Skype для бизнеса, как звук и видео, где трансляции в режиме реального времени важны.</span><span class="sxs-lookup"><span data-stu-id="027ac-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="027ac-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="027ac-111">If you need to use a proxy server</span></span>

<span data-ttu-id="027ac-p103">В некоторых организациях нет возможности обойти прокси-сервер для трафика Teams или Skype для бизнеса. В этом случае следует помнить о проблемах, упомянутых выше.</span><span class="sxs-lookup"><span data-stu-id="027ac-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="027ac-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="027ac-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="027ac-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="027ac-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="027ac-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="027ac-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="027ac-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="027ac-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="027ac-118">Следуйте другим рекомендациям в руководстве по сети: подготовка сети [организации для Teams](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="027ac-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="027ac-119">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="027ac-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="027ac-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="027ac-120">Related topics</span></span>

[<span data-ttu-id="027ac-121">Принципы сетевого подключения Microsoft 365 и Office 365</span><span class="sxs-lookup"><span data-stu-id="027ac-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="027ac-122">Подготовка сети организации к использованию Teams</span><span class="sxs-lookup"><span data-stu-id="027ac-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)
