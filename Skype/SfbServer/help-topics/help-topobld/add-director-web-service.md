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
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net pool01.contoso.NET, то используется базовый URL-адрес.
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219470"
---
# <a name="add-director-web-service"></a><span data-ttu-id="baaf9-104">Добавление веб-службы директора</span><span class="sxs-lookup"><span data-stu-id="baaf9-104">Add Director Web Service</span></span>
 
<span data-ttu-id="baaf9-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="baaf9-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="baaf9-106">Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net pool01.contoso.NET, то используется базовый URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="baaf9-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="baaf9-107">Невозможно переопределить полное доменное имя пула внутренних веб-служб, если развернут только один директор.</span><span class="sxs-lookup"><span data-stu-id="baaf9-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="baaf9-108">При настройке балансировки нагрузки службы доменных имен (DNS) для пула директоров можно указать другой внутренний базовый URL-адрес (который должен отличаться от полного доменного имени пула, например Internal- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="baaf9-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="baaf9-p104">Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена. Например, внутренним доменом является contoso.net, однако именем внешнего домена является contoso.com. Внешний базовый URL-адрес следует определить с использованием имени домена contoso.com. Это важно для обратных прокси-серверов, используемых в пограничном развертывании. Доменное имя внешнего базового URL-адреса не должно отличаться от полного доменного имени обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="baaf9-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

