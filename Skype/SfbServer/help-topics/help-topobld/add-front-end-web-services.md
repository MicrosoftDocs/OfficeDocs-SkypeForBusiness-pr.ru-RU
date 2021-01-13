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
# <a name="add-front-end-web-services"></a>Добавление веб-служб переднего плана
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.
  
Вы не можете переопределить внутреннее полное доменное имя пула веб-служб для сервера Standard Edition. При настройке балансировки нагрузки службы доменных имен (DNS) для пула переднего уровня Enterprise Edition можно указать другой внутренний базовый URL-адрес, который должен быть отличается от FQDN пула (например, \<your base URL\> internal-).
  
Вы можете указать внешний базовый URL-адрес, который отличается от внутреннего базового URL-адреса, чтобы обеспечить дифференциацию при именовании доменов. Например, ваш внутренний домен называется contoso.net, а внешний — contoso.com. Вам следует определить внешний базовый URL-адрес с использованием имени домена contoso.com. Это важно для обратных прокси-серверов при развертывании пограничного сервера. Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера. Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.
  

