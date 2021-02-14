---
title: Добавление веб-службы директора
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.
ms.openlocfilehash: 481fe9d0a63af723346f7fac5f04e8a9b9bb7edd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807749"
---
# <a name="add-director-web-service"></a>Добавление веб-службы директора
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.
  
Невозможно переопределить полное доменное имя пула внутренних веб-служб, если развернут только один директор. При настройке балансировки нагрузки службы доменных имен (DNS) для пула директоров можно указать другой внутренний базовый URL-адрес (который должен быть отличается от FQDN пула и может быть, например, внутренним). \<your base URL\>
  
Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена. Например, внутренним доменом является contoso.net, однако именем внешнего домена является contoso.com. Внешний базовый URL-адрес следует определить с использованием имени домена contoso.com. Это важно для обратных прокси-серверов, используемых в пограничном развертывании. Доменное имя внешнего базового URL-адреса не должно отличаться от полного доменного имени обратного прокси-сервера. 
  

