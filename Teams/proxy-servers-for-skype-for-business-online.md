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
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117727"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="21c05-103">Прокси-серверы для Teams или Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="21c05-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="21c05-104">Эта статья содержит рекомендации по использованию прокси-сервера в Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="21c05-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="21c05-105">Использовать прокси-сервер не рекомендуется</span><span class="sxs-lookup"><span data-stu-id="21c05-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="21c05-106">Если речь идет о трафике Teams или Skype для бизнеса через прокси-прокси, Майкрософт рекомендует обходить прокси-прокси.</span><span class="sxs-lookup"><span data-stu-id="21c05-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="21c05-107">Прокси-решения не делают Teams и Skype для бизнеса более безопасными, так как трафик уже зашифрован.</span><span class="sxs-lookup"><span data-stu-id="21c05-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="21c05-108">Наличие прокси-сервера может вызвать проблемы.</span><span class="sxs-lookup"><span data-stu-id="21c05-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="21c05-109">Проблемы, связанные с производительностью, могут быть введены в среду за счет задержки и потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="21c05-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="21c05-110">Такие проблемы привязают к отрицательным результатам в таких сценариях Teams или Skype для бизнеса, как звук и видео, где потоки в режиме реального времени важны.</span><span class="sxs-lookup"><span data-stu-id="21c05-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="21c05-111">Если нужно использовать прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="21c05-111">If you need to use a proxy server</span></span>

<span data-ttu-id="21c05-112">В некоторых организациях нет возможности обойти прокси-сервер для трафика Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="21c05-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="21c05-113">В этом случае следует обратить внимание на указанные выше проблемы.</span><span class="sxs-lookup"><span data-stu-id="21c05-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="21c05-114">Майкрософт также рекомендует следующее:</span><span class="sxs-lookup"><span data-stu-id="21c05-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="21c05-115">использовать внешнее разрешение DNS;</span><span class="sxs-lookup"><span data-stu-id="21c05-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="21c05-116">использовать прямую маршрутизацию по UDP;</span><span class="sxs-lookup"><span data-stu-id="21c05-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="21c05-117">разрешить трафик по UDP;</span><span class="sxs-lookup"><span data-stu-id="21c05-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="21c05-118">Следуйте другим рекомендациям в наших руководствах по сети: подготовка сети [организации для Teams](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="21c05-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="21c05-119">Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="21c05-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="21c05-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="21c05-120">Related topics</span></span>

[<span data-ttu-id="21c05-121">Принципы сетевого подключения Microsoft 365 и Office 365</span><span class="sxs-lookup"><span data-stu-id="21c05-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="21c05-122">Подготовка сети организации к использованию Teams</span><span class="sxs-lookup"><span data-stu-id="21c05-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)