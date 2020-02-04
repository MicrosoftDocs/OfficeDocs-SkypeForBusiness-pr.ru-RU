---
title: Добавление веб-службы директора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.
ms.openlocfilehash: 140012c548152f9473308b3be17f95adf53e918b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703184"
---
# <a name="add-director-web-service"></a>Добавление веб-службы директора
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.
  
Вы не можете переопределить полное доменное имя (FQDN) внутреннего пула веб-служб, если вы разворачиваете только один режиссер. При настройке балансировки нагрузки службы доменных имен (DNS) для пула режиссеров можно указать другой внутренний URL-адрес (который должен отличаться от полного доменного имени пула, например внутренний URL-\<адрес\>).
  
Вы можете указать внешний базовый URL-адрес, который отличается от внутреннего базового URL-адреса, чтобы различать доменные имена. Например, внутренний домен — contoso.net, но имя внешнего домена — contoso.com. Вы можете определить внешний базовый URL-адрес, используя имя домена contoso.com. Это важно для обратного прокси-серверов для развертывания пограничного сервера. Имя домена с внешним базовым URL-адресом должно совпадать с именем домена в качестве полного доменного имени обратного прокси-сервера. 
  

