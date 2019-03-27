---
title: Развертывание контроля допуска звонков в Скайп for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях.
ms.openlocfilehash: 52fcedaab781e9ed76222afb32b56840a3b07c1c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892866"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Развертывание контроля допуска звонков в Скайп for Business Server
 
Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях. Для получения дополнительных сведений см [плана для контроля допуска звонков в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Развертывание контроля допуска звонков

1.  Соберите все необходимые сведения для вашей топологии сети предприятия, как описано в статье [Пример: сбор требований для контроля допуска звонков в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Если вы еще не сделано, необходимо определить областей сети и веб-узлы и сопоставление подсетей с сетевыми узлами. Дополнительные сведения см [областей сети развернуть, сайты и подсети в Скайп для бизнеса](deploy-network.md).
    
3. Создание профилей политики, как описано в [Создание профилей политики пропускной способности в Скайп для Business Server](create-bandwidth-policy-profiles.md) пропускной способности
    
4. Создание связей между областями, как описано в [Создание связей между областями в Скайп для Business Server](create-network-region-links.md).
    
5. Создание маршрутов между областями сети, как описано в [Create interregional маршрутов между сетевыми в Скайп для Business Server](create-network-interregional-routes.md).
    
6. Создание политик межсайтового взаимодействия, как описано в [Создание политик межсайтового взаимодействия в Скайп для Business Server](create-network-intersite-policies.md).
    
7. Включение службы контроля допуска звонков, как описано в [Включить контроль допуска звонков в Скайп для Business Server](enable-call-admission-control.md).
    
8. Проверьте несколько окончательной настройки, убедитесь, что все настроено правильно. Дополнительные сведения см [развертывания контроля допуска звонков: последний контрольный список для Скайп для Business Server](final-checklist.md).
    

