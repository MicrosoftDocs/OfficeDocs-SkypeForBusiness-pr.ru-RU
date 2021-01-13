---
title: Добавление веб-служб переднего плана
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.
ms.openlocfilehash: 171cc8c912e1a1204d07be2c52c0e96bc1369991
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823989"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="c41ad-104">Добавление веб-служб переднего плана</span><span class="sxs-lookup"><span data-stu-id="c41ad-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="c41ad-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="c41ad-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="c41ad-106">Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="c41ad-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="c41ad-107">Вы не можете переопределить внутреннее полное доменное имя пула веб-служб для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c41ad-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="c41ad-108">При настройке балансировки нагрузки службы доменных имен (DNS) для пула переднего уровня Enterprise Edition можно указать другой внутренний базовый URL-адрес, который должен быть отличается от FQDN пула (например, \<your base URL\> internal-).</span><span class="sxs-lookup"><span data-stu-id="c41ad-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="c41ad-p104">Вы можете указать внешний базовый URL-адрес, который отличается от внутреннего базового URL-адреса, чтобы обеспечить дифференциацию при именовании доменов. Например, ваш внутренний домен называется contoso.net, а внешний — contoso.com. Вам следует определить внешний базовый URL-адрес с использованием имени домена contoso.com. Это важно для обратных прокси-серверов при развертывании пограничного сервера. Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера. Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.</span><span class="sxs-lookup"><span data-stu-id="c41ad-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy. Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

