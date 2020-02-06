---
title: Добавление веб-службы директора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.
ms.openlocfilehash: 0cdec8e371d7803bdcac781209b0fd9e55cb82be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821181"
---
# <a name="add-director-web-service"></a><span data-ttu-id="5713a-104">Добавление веб-службы директора</span><span class="sxs-lookup"><span data-stu-id="5713a-104">Add Director Web Service</span></span>
 
<span data-ttu-id="5713a-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="5713a-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="5713a-106">Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="5713a-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="5713a-107">Вы не можете переопределить полное доменное имя (FQDN) внутреннего пула веб-служб, если вы разворачиваете только один режиссер.</span><span class="sxs-lookup"><span data-stu-id="5713a-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="5713a-108">При настройке балансировки нагрузки службы доменных имен (DNS) для пула режиссеров можно указать другой внутренний URL-адрес (который должен отличаться от полного доменного имени пула, например внутренний URL-\<адрес\>).</span><span class="sxs-lookup"><span data-stu-id="5713a-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="5713a-109">Вы можете указать внешний базовый URL-адрес, который отличается от внутреннего базового URL-адреса, чтобы различать доменные имена.</span><span class="sxs-lookup"><span data-stu-id="5713a-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="5713a-110">Например, внутренний домен — contoso.net, но имя внешнего домена — contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5713a-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="5713a-111">Вы можете определить внешний базовый URL-адрес, используя имя домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5713a-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="5713a-112">Это важно для обратного прокси-серверов для развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5713a-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="5713a-113">Имя домена с внешним базовым URL-адресом должно совпадать с именем домена в качестве полного доменного имени обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="5713a-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

