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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: В этой статье содержится информация об использовании прокси-сервера с Microsoft Teams или Skype для бизнеса.
ms.openlocfilehash: 559a42c19aa47a9e72a5c0549e80f45de8d50fdf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582163"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Прокси-серверы для Teams или Skype для бизнеса Online

В этой статье приводится руководство по использованию прокси-сервера с Teams или Skype для бизнеса.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Использовать прокси-сервер не рекомендуется

Если речь идет о Teams или Skype для бизнеса трафике прокси-прокси, корпорация Майкрософт рекомендует обходить прокси-ми. Прокси-прокси не делают Teams или Skype для бизнеса более безопасными, так как трафик уже зашифрован.
  
Наличие прокси-сервера может стать причиной проблем. Проблемы, связанные с производительностью, могут быть связаны с задержкой и потерей пакетов. Такие проблемы привязают к отрицательным результатам в таких сценариях Teams или Skype для бизнеса, как аудио- и видеопотоки, где важны потоки в режиме реального времени.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Если нужно использовать прокси-сервер

В некоторых организациях нет возможности обойти прокси-сервер для Teams или Skype для бизнеса трафика. В этом случае следует обратить внимание на указанные выше проблемы.
  
Майкрософт также рекомендует следующее:
  
- использовать внешнее разрешение DNS;
    
- использовать прямую маршрутизацию по UDP;
    
- разрешить трафик по UDP;
    
- Следуйте другим рекомендациям в нашем руководстве по сети: Подготовка сети организации [к Teams](prepare-network.md)
  
    
Чтобы минимизировать возможные проблемы, следуйте этим рекомендациям.
  
## <a name="related-topics"></a>Статьи по теме

[Принципы сетевых подключений в Microsoft 365 и Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Подготовка сети организации к использованию Teams](prepare-network.md)