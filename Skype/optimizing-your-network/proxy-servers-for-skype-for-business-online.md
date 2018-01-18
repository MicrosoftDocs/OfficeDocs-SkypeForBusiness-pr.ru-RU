---
title: "Прокси-серверы для Skype для бизнеса Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "В этой статье представлены рекомендации по использованию прокси-сервера в Skype для бизнеса."
ms.openlocfilehash: 325e48c7bfaeffca7c34915e176772f0824903f6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
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
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a>Поставщики прокси-серверов со встроенной поддержкой или параметрами настройки Skype для бизнеса

В этом разделе содержатся сведения о поставщиках прокси-серверов, предоставляющих продукты или службы, работающие с трафиком Skype для бизнеса.
  
Для организаций, использующих **решения прокси-серверов Bluecoat**, выпущено новое встроенное ПО, которое устраняет некоторые неполадки с:
    
  - перехватом SSL;
    
  - проверками OCSP и SRL;
    
  - SIP по TLS;
    
  - поддержкой TURN.
    
Встроенную поддержку Bluecoat легко включить в Skype для бизнеса. Она позволяет идентифицировать нужный трафик и управлять им. Это обеспечит оптимальное взаимодействие для пользователей: проверку подлинности, обмен сигналами и поток трафика мультимедиа, и при этом не создаст проблем с безопасностью.
    
Если Bluecoat прокси-сервер является частью топологию сети обратитесь к следующей ссылке: https://support.symantec.com/en_US/article.DOC9757.html

## <a name="related-topics"></a>См. также:

[Оптимизация сети для Skype для бизнеса Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)