---
title: Добавление веб-службы директора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net pool01.contoso.NET, то используется базовый URL-адрес.
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219470"
---
# <a name="add-director-web-service"></a>Добавление веб-службы директора
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net pool01.contoso.NET, то используется базовый URL-адрес.
  
Невозможно переопределить полное доменное имя пула внутренних веб-служб, если развернут только один директор. При настройке балансировки нагрузки службы доменных имен (DNS) для пула директоров можно указать другой внутренний базовый URL-адрес (который должен отличаться от полного доменного имени пула, например Internal- \<your base URL\> ).
  
Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена. Например, внутренним доменом является contoso.net, однако именем внешнего домена является contoso.com. Внешний базовый URL-адрес следует определить с использованием имени домена contoso.com. Это важно для обратных прокси-серверов, используемых в пограничном развертывании. Доменное имя внешнего базового URL-адреса не должно отличаться от полного доменного имени обратного прокси-сервера. 
  

