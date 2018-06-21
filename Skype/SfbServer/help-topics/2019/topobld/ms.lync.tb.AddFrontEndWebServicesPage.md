---
title: Добавление веб-служб переднего плана
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.
ms.openlocfilehash: 4858f64d98b917876ec8d03b4dca9f9d0fee512d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "19972354"
---
# <a name="add-front-end-web-services"></a>Добавление веб-служб переднего плана
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.
  
Не может переопределить внутренние веб-служб пула полное доменное имя (FQDN) для сервера Standard Edition. При настройке доменных имен (DNS) балансировку нагрузки для пула переднего плана Enterprise Edition, можно указать разные внутренний базовый URL-адрес, который должно отличаться от полного доменного ИМЕНИ пула (например, внутренний -\<базовый URL-адреса\>).
  
Можно указать внешний базовый URL-адрес, отличающийся от вашей внутренней базовый URL-адрес, чтобы различать доменных имен. Например внутреннего домена — это contoso.net, но является имя внешнего домена contoso.com. Можно определить внешний базовый URL-адрес, используя имя домена contoso.com. Это важно для обратных прокси-серверов для развертывания пограничного сервера. Внешний базовый URL-адрес имя домена должно совпадать с доменное имя полное доменное имя обратного прокси-сервера. Обмен мгновенными сообщениями и присутствия требуется доступ по протоколу HTTP для пула переднего плана.
  

