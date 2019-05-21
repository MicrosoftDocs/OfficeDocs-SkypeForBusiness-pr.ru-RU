---
title: Развертывание элемента управления допуском звонков в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях.
ms.openlocfilehash: 7f7f8dee4e25061533564ce517f797281bef042e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280441"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Развертывание элемента управления допуском звонков в Skype для бизнеса Server
 
Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях. Дополнительные сведения можно найти [в разделе Планирование управления допуском звонков в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Развертывание контроля допуска звонков

1.  Соберите все необходимые данные для топологии корпоративной сети, как описано в [примере: сбор требований для управления допуском звонков в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Если вы еще не сделали этого, необходимо определить регионы сети и сайты, а затем связать подсети с сетевыми сайтами. Подробные сведения можно найти [в разделе Развертывание регионов сети, сайтов и подсетей в Skype для бизнеса](deploy-network.md).
    
3. Создание профилей политики пропускной способности в соответствии с подробными сведениями [Создание профилей политики пропускной способности в Skype для бизнеса Server](create-bandwidth-policy-profiles.md)
    
4. Создание ссылок на сетевой регион, подробно описанных в разделе [Создание ссылок на сетевой регион в Skype для бизнеса Server](create-network-region-links.md).
    
5. Создавайте маршруты между регионами, как описано в разделе [Создание межсетевых маршрутов в Skype для бизнеса Server](create-network-interregional-routes.md).
    
6. Создавайте политики межсетевого соединения, как описано в этой задаче: [Создание политик межсетевого соединения в Skype для бизнеса Server](create-network-intersite-policies.md).
    
7. Включите управление допуском звонков, как описано в подокне [включения управления допуском звонков в Skype для бизнеса Server](enable-call-admission-control.md).
    
8. Проверьте некоторые параметры, чтобы убедиться, что все настроено правильно. Дополнительные сведения можно найти в разделе [Развертывание элемента управления допуском звонков: последний контрольный список для Skype для бизнеса Server](final-checklist.md).
    

