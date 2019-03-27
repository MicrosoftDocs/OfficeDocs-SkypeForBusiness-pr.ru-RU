---
title: Добавление веб-служб переднего плана 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.
ms.openlocfilehash: 75a905767ff4dbf2b9366193727bde370d05f87c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882799"
---
# <a name="add-front-end-web-services-2010"></a>Добавление веб-служб переднего плана 2010
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.
  
Не может переопределить внутренние веб-служб пула полное доменное имя (FQDN) для сервера Standard Edition. При настройке доменных имен (DNS) балансировку нагрузки для пула переднего плана Enterprise Edition, можно указать другой внутренний базовый URL-адрес (который должно отличаться от полного доменного ИМЕНИ пула и может быть, например, внутренний -\<базовый URL-адреса\>).
  
Можно указать внешний базовый URL-адрес, отличающийся от вашей внутренней базовый URL-адрес, чтобы различать доменных имен. Например внутреннего домена — это contoso.net, но является имя внешнего домена contoso.com. Может определить внешний базовый URL-адрес, используя имя домена contoso.com. Это важно для обратных прокси-серверов для развертывания пограничного сервера. Внешний базовый URL-адрес имя домена должно совпадать с доменное имя полное доменное имя обратного прокси-сервера. Обмен мгновенными сообщениями и присутствия требуется доступ по протоколу HTTP для пула переднего плана.
  

