---
title: Развертывание управления приемом вызовов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: b22074df1eac0727334371d92097333a589eb684
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753600"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Развертывание управления приемом вызовов в Skype для бизнеса Server
 
Управление приемом вызовов (CAC) — это решение, которое определяет, можно ли установить сеанс в режиме реального времени на основе доступной пропускной способности, чтобы предотвратить плохое качество звука и видео для пользователей в захламляемой сети. Дополнительные сведения см. в дополнительных сведениях в области управления приемом [вызовов в Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
### <a name="to-deploy-call-admission-control"></a>Развертывание управления приемом вызовов

1.  Соберите всю необходимую информацию для топологии корпоративной сети, как описано в [примере:](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)сбор требований для управления приемом вызовов в Skype для бизнеса Server .
    
2. Если вы еще этого не сделали, необходимо определить сетевые регионы и сайты и связать подсети с сетевыми сайтами. Дополнительные сведения см. в [материале Deploy network regions, sites and subnets in Skype для бизнеса.](deploy-network.md)
    
3. Создание профилей политики пропускной способности, как описано в профилей политики пропускной [способности](create-bandwidth-policy-profiles.md) в Skype для бизнеса Server
    
4. Создание ссылок сетевого региона, как описано в "Создание ссылок региона [сети" в Skype для бизнеса Server.](create-network-region-links.md)
    
5. Создание сетевых межрегиональных маршрутов, как подробно описано в [Create network interregional routes in Skype для бизнеса Server.](create-network-interregional-routes.md)
    
6. Создание сетевых межсетных политик, как описано в [Create network intersite policies in Skype для бизнеса Server.](create-network-intersite-policies.md)
    
7. Включить управление приемом вызовов, как подробно описано в Включить управление приемом [вызовов в Skype для бизнеса Server](enable-call-admission-control.md).
    
8. Проверьте несколько конечных параметров, чтобы убедиться, что все настроено правильно. Подробные сведения см. в развертывании управления приемом [вызовов: окончательный контрольный](final-checklist.md)список для Skype для бизнеса Server .
    

