---
title: Добавление веб-служб переднего плана
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — `https://pool01.contoso.net` базовый `pool01.contoso.net` URL-адрес .
ms.openlocfilehash: a02ab1d8c3013216c31d1e050e22eaf9cf614045
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752138"
---
# <a name="add-front-end-web-services"></a>Добавление веб-служб переднего плана
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — `https://pool01.contoso.net` базовый `pool01.contoso.net` URL-адрес .
  
Вы не можете переопределить внутреннее полное доменное имя пула веб-служб для сервера Standard Edition. При настройке балансировки нагрузки системы доменных имен (DNS) для пула выпуск Enterprise переднего конца можно указать другой внутренний базовый URL-адрес, который должен быть отличается от FQDN пула (например, внутренний). \<your base URL\>
  
Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена. Например, ваш внутренний домен `contoso.net` , но ваше внешнее доменное имя `contoso.com` . Вы бы определили внешний базовый URL-адрес с помощью `contoso.com` доменного имени. Это важно для обратных прокси-серверов, используемых в пограничном развертывании. Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера. Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.
  

