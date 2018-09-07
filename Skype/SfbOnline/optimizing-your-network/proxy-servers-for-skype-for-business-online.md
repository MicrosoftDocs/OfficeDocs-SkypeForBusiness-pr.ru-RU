---
title: Прокси-серверы для Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: В этой статье представлены рекомендации по использованию прокси-сервера в Skype для бизнеса.
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850016"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Прокси-серверы для Skype для бизнеса Online

[] В этой статье представлены рекомендации по использованию прокси-сервера в Skype для бизнеса.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Использовать прокси-сервер не рекомендуется

Майкрософт рекомендует обходить прокси-серверы в трафике Skype для бизнеса. Прокси-серверы не служат дополнительной защитой в Skype для бизнеса, так как трафик уже зашифрован.
  
Использование же прокси-сервера может вызвать, например, снижение производительности в среде из-за задержки и утери пакетов. В Skype для бизнеса важна непрерывность потоков в режиме реального времени, и такие проблемы ухудшат голосовую и видеосвязь.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Если нужно использовать прокси-сервер

В некоторых организациях нет возможности обойти прокси-сервер в трафике Skype для бизнеса. В этом случае следует обратить внимание на указанные выше проблемы.
  
Майкрософт также рекомендует следующее:
  
- использовать внешнее разрешение DNS;
    
- использовать прямую маршрутизацию по UDP;
    
- разрешить трафик по UDP;
    
- следовать другим рекомендациям в руководствах по работе с сетями:
    
  - [Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Оптимизация сети для Skype для бизнеса Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.
  
## <a name="related-topics"></a>См. также:

[Оптимизация сети для Skype для бизнеса Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 