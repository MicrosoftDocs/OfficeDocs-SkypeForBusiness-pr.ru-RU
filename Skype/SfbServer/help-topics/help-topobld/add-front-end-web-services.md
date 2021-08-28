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
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — базовый https://pool01.contoso.net URL-адрес pool01.contoso.net.
ms.openlocfilehash: c2fd91d9f16d585e4ade2ac6a071d699e6917af7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615805"
---
# <a name="add-front-end-web-services"></a>Добавление веб-служб переднего плана
 
Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — базовый https://pool01.contoso.net URL-адрес pool01.contoso.net.
  
Вы не можете переопределить внутреннее полное доменное имя пула веб-служб для сервера Standard Edition. При настройке балансировки нагрузки системы доменных имен (DNS) для пула выпуск Enterprise переднего конца можно указать другой внутренний базовый URL-адрес, который должен быть отличается от FQDN пула (например, внутренний). \<your base URL\>
  
Вы можете указать внешний базовый URL-адрес, который отличается от внутреннего базового URL-адреса, чтобы обеспечить дифференциацию при именовании доменов. Например, ваш внутренний домен называется contoso.net, а внешний — contoso.com. Вам следует определить внешний базовый URL-адрес с использованием имени домена contoso.com. Это важно для обратных прокси-серверов при развертывании пограничного сервера. Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера. Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.
  

