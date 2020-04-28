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
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: В этой статье приводятся сведения об использовании прокси-сервера в Microsoft Teams или Skype для бизнеса.
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905681"
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
    
- Ниже указаны другие рекомендации по работе в сети: [Подготовка сети организации для Teams](prepare-network.md)
  
    
Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.
  
## <a name="related-topics"></a>Статьи по теме

[Принципы подключения к сети в Office 365](https://aka.ms/pnc)

[Подготовка сети организации к использованию Teams](prepare-network.md)
