---
title: Прокси-серверы для Teams или Skype для бизнеса Online
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: В этой статье содержатся сведения об использовании прокси-сервера с Microsoft Teams или Skype для бизнеса.
ms.openlocfilehash: 61a1878b3c7057de7dddbcd63c480f80c2f16e0f
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045438"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Прокси-серверы для Teams или Skype для бизнеса Online

В этой статье приводятся рекомендации по использованию прокси-сервера с Teams или Skype для бизнеса.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Использовать прокси-сервер не рекомендуется

Когда речь идет о Teams или Skype для бизнеса через прокси-серверы, корпорация Майкрософт рекомендует обходить прокси-серверы. Прокси-серверы не делают Teams или Skype для бизнеса более безопасным, так как трафик уже зашифрован.
  
Наличие прокси-сервера может вызвать проблемы. Проблемы, связанные с производительностью, могут быть введены в среду из-за задержки и потери пакетов. Такие проблемы могут привести к отрицательному опыту в таких сценариях Teams или Skype для бизнеса, как звук и видео, где потоки в режиме реального времени являются обязательными.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Если нужно использовать прокси-сервер

В некоторых организациях нет возможности обойти прокси-сервер для Teams или Skype для бизнеса трафика. В этом случае следует обратить внимание на указанные выше проблемы.
  
Майкрософт также рекомендует следующее:
  
- использовать внешнее разрешение DNS;
    
- использовать прямую маршрутизацию по UDP;
    
- разрешить трафик по UDP;
    
- Следуйте другим рекомендациям в наших рекомендациях по работе с сетями: [подготовка сети организации к Teams](prepare-network.md)
  
    
Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.
  
## <a name="related-topics"></a>Статьи по теме

[Принципы сетевых подключений в Microsoft 365 и Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Подготовка сети организации к использованию Teams](prepare-network.md)