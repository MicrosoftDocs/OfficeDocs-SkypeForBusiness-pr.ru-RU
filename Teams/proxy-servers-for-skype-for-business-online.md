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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: В этой статье приводятся сведения об использовании прокси-сервера в Teams или Skype для бизнеса.
ms.openlocfilehash: b06e7aa43dcbcf5aeab9011af72d94460f69cc63
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573210"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Прокси-серверы для Teams или Skype для бизнеса Online

В этой статье приводятся рекомендации по использованию прокси-сервера в Teams или Skype для бизнеса.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Использовать прокси-сервер не рекомендуется

При поступлении трафика в Teams или Skype для бизнеса через прокси-серверы Корпорация Майкрософт рекомендует обойти прокси-серверы. Прокси-серверы не делают Teams или Skype для бизнеса более надежными, так как трафик уже зашифрован.
  
А у прокси-сервера могут возникнуть проблемы. Проблемы, связанные с производительностью, могут быть введены в среду с помощью задержки и потери пакетов. Такие проблемы могут привести к негативной работе в таких рабочих группах и сценариях Skype для бизнеса, как звуковые и видеофайлы, где очень важны потоки в режиме реального времени.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Если нужно использовать прокси-сервер

В некоторых организациях нет возможности обходить прокси-сервер для Teams и трафик Skype для бизнеса. Если это так, следует помнить о проблемах, упомянутых выше.
  
Майкрософт также рекомендует следующее:
  
- использовать внешнее разрешение DNS;
    
- использовать прямую маршрутизацию по UDP;
    
- разрешить трафик по UDP;
    
- Ниже приведены другие рекомендации по работе в сети.
    
  - [Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Оптимизация сети для Skype для бизнеса Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.
  
## <a name="related-topics"></a>Статьи по теме

[Оптимизация сети для Skype для бизнеса Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 