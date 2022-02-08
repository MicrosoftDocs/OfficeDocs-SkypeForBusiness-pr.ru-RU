---
title: Развертывание управления приемом вызовов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Управление приемом вызовов (CAC) — это решение, которое определяет, можно ли установить сеанс в режиме реального времени на основе доступной пропускной способности, чтобы предотвратить плохое качество звука и видео для пользователей в захламляемой сети.
ms.openlocfilehash: 395d40caaf9db491bffad0723cab0142238bd32a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385307"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Развертывание управления приемом вызовов в Skype для бизнеса Server
 
Управление приемом вызовов (CAC) — это решение, которое определяет, можно ли установить сеанс в режиме реального времени на основе доступной пропускной способности, чтобы предотвратить плохое качество звука и видео для пользователей в захламляемой сети. Дополнительные сведения см. в [дополнительных сведениях в](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) области управления приемом вызовов в Skype для бизнеса Server.
  
### <a name="to-deploy-call-admission-control"></a>Развертывание управления приемом вызовов

1.  Соберите всю необходимую информацию для топологии корпоративной сети, как описано в примере: сбор требований для управления приемом [вызовов в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Если вы еще этого не сделали, необходимо определить сетевые регионы и сайты и связать подсети с сетевыми сайтами. Дополнительные сведения см. в [материале Deploy network regions, sites and subnets in Skype для бизнеса](deploy-network.md).
    
3. Создание профилей политики пропускной способности, как описано в профилей политики пропускной способности [в Skype для бизнеса Server](create-bandwidth-policy-profiles.md)
    
4. Создание ссылок сетевого региона, как описано в "Создание ссылок региона сети[" в Skype для бизнеса Server](create-network-region-links.md).
    
5. Создание сетевых межрегиональных маршрутов, как описано в "Создание сетевых межрегиональных маршрутов [в Skype для бизнеса Server.](create-network-interregional-routes.md)
    
6. Создайте межсетевую политику, как описано в [Create network intersite policies in Skype для бизнеса Server](create-network-intersite-policies.md).
    
7. Включить управление приемом вызовов, как подробно описано в [Включить управление приемом вызовов в Skype для бизнеса Server](enable-call-admission-control.md).
    
8. Проверьте несколько конечных параметров, чтобы убедиться, что все настроено правильно. Подробные сведения см. в материале Развертывание управления приемом вызовов[: окончательный контрольный список для Skype для бизнеса Server](final-checklist.md).
    

