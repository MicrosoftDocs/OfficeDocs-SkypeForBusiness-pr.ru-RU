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
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — базовый https://pool01.contoso.net URL-адрес pool01.contoso.net.
ms.openlocfilehash: b82cc8383efc32a92b46b798503a7780df82aad8c235c3d75561f895e13cdc02
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314495"
---
# <a name="add-front-end-web-services"></a>Добавление веб-служб переднего плана
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — базовый https://pool01.contoso.net URL-адрес pool01.contoso.net.
  
Вы не можете переопределить внутреннее полное доменное имя пула веб-служб для сервера Standard Edition. При настройке балансировки нагрузки системы доменных имен (DNS) для пула выпуск Enterprise переднего конца можно указать другой внутренний базовый URL-адрес, который должен быть отличается от FQDN пула (например, внутренний). \<your base URL\>
  
Вы можете указать внешний базовый URL-адрес, который отличается от внутреннего базового URL-адреса, чтобы обеспечить дифференциацию при именовании доменов. Например, ваш внутренний домен называется contoso.net, а внешний — contoso.com. Вам следует определить внешний базовый URL-адрес с использованием имени домена contoso.com. Это важно для обратных прокси-серверов при развертывании пограничного сервера. Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера. Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.
  

