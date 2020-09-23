---
title: Добавление веб-служб переднего плана 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net pool01.contoso.NET, то используется базовый URL-адрес.
ms.openlocfilehash: d87bb3716a19f59f2614194d79dfedaf544964e1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217960"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="1d0e0-104">Добавление веб-служб переднего плана 2010</span><span class="sxs-lookup"><span data-stu-id="1d0e0-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="1d0e0-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="1d0e0-106">Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net pool01.contoso.NET, то используется базовый URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="1d0e0-107">Вы не можете переопределить полное доменное имя (FQDN) внутреннего пула веб-служб для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="1d0e0-108">При настройке балансировки нагрузки службы доменных имен (DNS) для пула переднего плана Enterprise Edition можно указать другой внутренний базовый URL-адрес (который должен отличаться от полного доменного имени пула и может быть, например, internal- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="1d0e0-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="1d0e0-109">Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="1d0e0-110">Например, внутренним доменом является contoso.net, однако именем внешнего домена является contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="1d0e0-111">Внешний базовый URL-адрес следует определить с использованием имени домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="1d0e0-112">Это важно для обратных прокси-серверов, используемых в пограничном развертывании.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="1d0e0-113">Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="1d0e0-114">Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

