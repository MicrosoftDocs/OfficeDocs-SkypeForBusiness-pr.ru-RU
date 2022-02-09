---
title: Добавление веб-служб переднего плана 2010
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес `https://pool01.contoso.net`веб-служб пула — базовый URL-адрес `pool01.contoso.net`.
ms.openlocfilehash: 5a4de05a5cf8c46c8c61a8b5bb54c4ebe9335f35
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399133"
---
# <a name="add-front-end-web-services-2010"></a>Добавление веб-служб переднего плана 2010
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес `https://pool01.contoso.net`веб-служб пула — базовый URL-адрес `pool01.contoso.net`.
  
Нельзя переопределять внутренний пул веб-служб, полностью квалифицированный доменное имя (FQDN) для выпуск Standard Server. При настройке балансировки нагрузки системы доменных имен (DNS) для пула выпуск Enterprise переднего конца можно указать другой внутренний базовый URL-адрес\<your base URL\> (который должен быть другим, чем FQDN пула, и может быть, например, внутренним).
  
Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена. Например, ваш внутренний домен , `contoso.net`но ваше внешнее доменное имя `contoso.com`. Внешний базовый URL-адрес следует определить с использованием имени домена contoso.com. Это важно для обратных прокси-серверов, используемых в пограничном развертывании. Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера. Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.
  

