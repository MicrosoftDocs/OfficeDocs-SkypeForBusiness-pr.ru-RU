---
title: Добавление веб-служб переднего плана 2010
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824029"
---
# <a name="add-front-end-web-services-2010"></a>Добавление веб-служб переднего плана 2010
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.
  
Переопределять полное доменное имя внутреннего пула веб-служб для сервера Standard Edition невозможно. При настройке балансировки нагрузки службы доменных имен (DNS) для пула переднего уровня Enterprise Edition можно указать другой внутренний базовый URL-адрес (который должен быть отличается от FQDN пула и может быть, например, внутренним). \<your base URL\>
  
Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена. Например, внутренним доменом является contoso.net, однако именем внешнего домена является contoso.com. Внешний базовый URL-адрес следует определить с использованием имени домена contoso.com. Это важно для обратных прокси-серверов, используемых в пограничном развертывании. Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера. Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.
  

