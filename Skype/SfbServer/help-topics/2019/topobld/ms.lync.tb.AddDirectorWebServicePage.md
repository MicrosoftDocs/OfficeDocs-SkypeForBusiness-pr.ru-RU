---
title: Добавление веб-службы директора
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — `https://pool01.contoso.net` базовый `pool01.contoso.net` URL-адрес .
ms.openlocfilehash: d3341889606371b363d5e37b3d5a76af9e3d7911
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853473"
---
# <a name="add-director-web-service"></a>Добавление веб-службы директора
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — `https://pool01.contoso.net` базовый `pool01.contoso.net` URL-адрес .
  
Невозможно переопределить полное доменное имя пула внутренних веб-служб, если развернут только один директор. При настройке балансировки нагрузки системы доменных имен (DNS) для пула директоров можно указать другой внутренний базовый URL-адрес (который должен быть отличается от FQDN пула и может быть, например, внутренним). \<your base URL\>
  
Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена. Например, ваш внутренний домен `contoso.net` , но ваше внешнее доменное имя `contoso.com` . Вы бы определили внешний базовый URL-адрес с помощью `contoso.com domain name` . Это важно для обратных прокси-серверов, используемых в пограничном развертывании. Доменное имя внешнего базового URL-адреса не должно отличаться от полного доменного имени обратного прокси-сервера. 
  

