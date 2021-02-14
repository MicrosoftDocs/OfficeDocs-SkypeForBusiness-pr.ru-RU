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
description: В этой статье приводится информация об использовании прокси-сервера в Skype для бизнеса.
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863758"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Прокси-серверы для Skype для бизнеса Online

В этой статье указаны инструкции по использованию прокси-сервера в Skype для бизнеса.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Использовать прокси-сервер не рекомендуется

Если речь идет о трафике Skype для бизнеса через прокси-прокси, Майкрософт рекомендует обходить прокси-прокси. Прокси-решения не делают Skype для бизнеса более безопасным, так как трафик уже зашифрован.
  
Наличие прокси-сервера может вызвать проблемы. Проблемы, связанные с производительностью, могут быть введены в среду за счет задержки и потери пакетов. Такие проблемы привязают к отрицательным результатам в таких сценариях Teams или Skype для бизнеса, как звук и видео, где трансляции в режиме реального времени важны.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Если нужно использовать прокси-сервер

В некоторых организациях нет возможности обойти прокси-сервер в трафике Skype для бизнеса. В этом случае следует обратить внимание на указанные выше проблемы.
  
Майкрософт также рекомендует следующее:
  
- использовать внешнее разрешение DNS;
    
- использовать прямую маршрутизацию по UDP;
    
- разрешить трафик по UDP;
    
- Следуя другим рекомендациям в руководстве по сети:
    
  - [Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online](media-quality-and-network-connectivity-performance.md)
    
  - [Оптимизация сети для Skype для бизнеса Online](optimizing-your-network.md)
    
Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.
  
## <a name="related-topics"></a>Статьи по теме

[Оптимизация сети для Skype для бизнеса Online](optimizing-your-network.md)
 