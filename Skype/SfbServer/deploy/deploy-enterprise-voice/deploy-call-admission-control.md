---
title: Развертывание контроля допуска звонков в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Контроль допуска вызовов (CAC) — это решение, которое определяет, можно ли установить сеанс в режиме реального времени на основе доступной пропускной способности для предотвращения неудовлетворительного качества звука и видео для пользователей в захламляемой сети.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836889"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Развертывание контроля допуска звонков в Skype для бизнеса Server
 
Контроль допуска вызовов (CAC) — это решение, которое определяет, можно ли установить сеанс в режиме реального времени на основе доступной пропускной способности для предотвращения неудовлетворительного качества звука и видео для пользователей в захламляемой сети. Дополнительные сведения см. в [сведениях о планировании контроля допуска звонков в Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
### <a name="to-deploy-call-admission-control"></a>Развертывание контроля допуска вызовов

1.  Соберите все необходимые сведения для корпоративной сетевой топологии, как описано в примере: сбор требований для контроля допуска звонков [в Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
    
2. Если это еще не сделано, необходимо определить области сети и сайты и связать подсети с сетевыми сайтами. Дополнительные сведения см. в сведениях о развертывании [областей сети, сайтов и подсетей в Skype для бизнеса.](deploy-network.md)
    
3. Создание профилей политик пропускной способности, как описано в описании создания профилей политик пропускной способности [в Skype для бизнеса Server](create-bandwidth-policy-profiles.md)
    
4. Создание связей между областями сети, как описано в описании создания связей между областями [сети в Skype для бизнеса Server.](create-network-region-links.md)
    
5. Создание маршрутов между регионами сети, как описано в описании создания межрегиональных сетевых маршрутов [в Skype для бизнеса Server.](create-network-interregional-routes.md)
    
6. Создайте межсайтовую сетевую политику, как описано в описании создания сетевых политик межсайтов [в Skype для бизнеса Server.](create-network-intersite-policies.md)
    
7. Включить контроль допуска звонков, как описано в подробном описании этой темы [в Skype для бизнеса Server.](enable-call-admission-control.md)
    
8. Проверьте несколько окончательных параметров, чтобы убедиться, что все настроено правильно. Подробные сведения см. в развертывании контроля допуска [звонков: окончательный контрольный](final-checklist.md)список для Skype для бизнеса Server.
    

