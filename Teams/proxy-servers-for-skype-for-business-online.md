---
title: Прокси-серверы для Teams или Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: M365-collaboration
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: В этой статье сведения об использовании прокси-сервера с группами или Скайп для бизнеса.
ms.openlocfilehash: e2d14c8307de2ee64a766394805498505719189a
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542809"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Прокси-серверы для Teams или Skype для бизнеса Online

В этой статье рекомендации относительно использования прокси-сервера с группами или Скайп для бизнеса.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Использовать прокси-сервер не рекомендуется

Когда речь идет о группы или Скайп для бизнес-трафика через прокси-серверы, корпорация Майкрософт рекомендует обход прокси-серверы. Прокси-серверы не сделать группы или Скайп для бизнеса более безопасной так как трафика уже зашифрованы.
  
И необходимости прокси-сервер может вызвать проблемы. Проблемы, связанные с производительностью может быть вызвана среду через задержки и потери пакетов. Проблемы, такие как это приведет к отрицательным взаимодействия в таких групп или Скайп для бизнес-сценарии как аудио и видео, где важны потоков в режиме реального времени.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Если нужно использовать прокси-сервер

В некоторых организациях не имеют возможности обхода прокси-сервер для группы или Скайп для бизнес-трафика. В этом случае следует обратить внимание на указанные выше проблемы.
  
Майкрософт также рекомендует следующее:
  
- использовать внешнее разрешение DNS;
    
- использовать прямую маршрутизацию по UDP;
    
- разрешить трафик по UDP;
    
- Выполнив другие рекомендации, приведенные в нашей сети рекомендаций:
    
  - [Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Оптимизация сети для Skype для бизнеса Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.
  
## <a name="related-topics"></a>Связанные разделы

[Оптимизация сети для Skype для бизнеса Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 