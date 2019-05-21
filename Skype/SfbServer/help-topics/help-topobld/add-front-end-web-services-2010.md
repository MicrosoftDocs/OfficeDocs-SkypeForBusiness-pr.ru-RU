---
title: Добавление веб-служб переднего плана 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.
ms.openlocfilehash: ec167b333948384a66f6ff66c64c4f53fcbe1076
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275327"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="ca1f1-104">Добавление веб-служб переднего плана 2010</span><span class="sxs-lookup"><span data-stu-id="ca1f1-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="ca1f1-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="ca1f1-106">Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="ca1f1-107">Вы не можете переопределить полное доменное имя (FQDN) внутреннего пула веб-служб для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="ca1f1-108">При настройке балансировки нагрузки DNS для пула переднего плана Enterprise Edition вы можете указать другой внутренний URL-адрес, который должен отличаться от полного доменного имени пула и может быть, например, внутренним\<URL-адресом.\></span><span class="sxs-lookup"><span data-stu-id="ca1f1-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="ca1f1-109">Вы можете указать внешний базовый URL-адрес, который отличается от внутреннего базового URL-адреса, чтобы различать доменные имена.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="ca1f1-110">Например, внутренний домен — contoso.net, но имя внешнего домена — contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="ca1f1-111">Вы можете определить внешний базовый URL-адрес, используя имя домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="ca1f1-112">Это важно для обратного прокси-серверов для развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="ca1f1-113">Имя домена с внешним базовым URL-адресом должно совпадать с именем домена в качестве полного доменного имени обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="ca1f1-114">Для обмена мгновенными сообщениями и присутствия требуется доступ по протоколу HTTP к пулу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ca1f1-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

