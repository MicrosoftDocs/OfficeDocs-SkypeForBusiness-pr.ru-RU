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
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — базовый https://pool01.contoso.net URL-адрес pool01.contoso.net.
ms.openlocfilehash: dad33773bc286e711c96eeb6157ff9ca53de789fc081b5abbfaf4e22e67fa119
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314535"
---
# <a name="add-front-end-web-services-2010"></a>Добавление веб-служб переднего плана 2010
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — базовый https://pool01.contoso.net URL-адрес pool01.contoso.net.
  
Нельзя переопределять внутренний пул веб-служб, полностью квалифицированный доменное имя (FQDN) для выпуск Standard Server. При настройке балансировки нагрузки системы доменных имен (DNS) для пула выпуск Enterprise переднего конца можно указать другой внутренний базовый URL-адрес (который должен быть другим, чем FQDN пула, и может быть, например, внутренним). \<your base URL\>
  
Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена. Например, внутренним доменом является contoso.net, однако именем внешнего домена является contoso.com. Внешний базовый URL-адрес следует определить с использованием имени домена contoso.com. Это важно для обратных прокси-серверов, используемых в пограничном развертывании. Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера. Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.
  

