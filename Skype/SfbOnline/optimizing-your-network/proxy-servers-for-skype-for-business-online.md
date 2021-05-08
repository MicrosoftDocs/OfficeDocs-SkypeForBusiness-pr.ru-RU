---
title: Прокси-серверы для Teams или Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: В этой статье содержится информация об использовании прокси-сервера с Skype для бизнеса.
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240418"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Прокси-серверы для Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

В этой статье приводится руководство по использованию прокси-сервера с Skype для бизнеса.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Использовать прокси-сервер не рекомендуется

Майкрософт рекомендует обходить прокси-серверы в трафике Skype для бизнеса. Прокси-прокси не делают Skype для бизнеса более безопасными, так как трафик уже зашифрован.
  
Наличие прокси-сервера может стать причиной проблем. Проблемы, связанные с производительностью, могут быть связаны с задержкой и потерей пакетов. Такие проблемы привязают к отрицательным результатам в таких сценариях Teams или Skype для бизнеса, как звук и видео, где важны потоки в режиме реального времени.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Если нужно использовать прокси-сервер

В некоторых организациях нет возможности обойти прокси-сервер в трафике Skype для бизнеса. В этом случае следует обратить внимание на указанные выше проблемы.
  
Майкрософт также рекомендует следующее:
  
- использовать внешнее разрешение DNS;
    
- использовать прямую маршрутизацию по UDP;
    
- разрешить трафик по UDP;
    
- Следуйте другим рекомендациям в наших рекомендациях по сети:
    
  - [Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online](media-quality-and-network-connectivity-performance.md)
    
  - [Оптимизация сети для Skype для бизнеса Online](optimizing-your-network.md)
    
Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.
  
## <a name="related-topics"></a>Статьи по теме

[Оптимизация сети для Skype для бизнеса Online](optimizing-your-network.md)
 
