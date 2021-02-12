---
title: Настройка обхода сервера-посредника в Skype для бизнеса Server для всегдаго обхода сервера-посредника
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Включить обход сервера-посредника для обхода сервера-посредника в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804219"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Настройка обхода сервера-посредника в Skype для бизнеса Server для всегдаго обхода сервера-посредника
 
Включить обход сервера-посредника для обхода сервера-посредника в Skype для бизнеса Server Корпоративная голосовая связь. 
  
 Если для настройки глобальных параметров обхода мультимедиа используются действия, которые данной темы используются, предположим, что у вас хорошая связь между конечными точками Skype для бизнеса и любым одноранговой точкой, для которой вы настроили обход мультимедиа в магистрали.
  
If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass. Это обеспечивает более точный контроль над процессом обхода сервера-посредника. Для этого используйте действия, которые необходимо предпринять в настройке глобальных параметров обхода сервера-посредника в Skype для бизнеса [Server,](use-site-and-region-information.md) чтобы использовать сведения о сайте и регионе, а затем связать подсеть с сетевым [сайтом.](deploy-network.md#BKMK_AssociateSubnets)
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Чтобы включить глобальный постоянный обход сервера-посредника, выполните следующие действия.

1. Откройте панель управления Skype для бизнеса Server.
    
2. В левой панели навигации щелкните **Конфигурация сети**.
    
3. Дважды щелкните конфигурацию **Глобальная** в списке.
    
4. На странице **Изменение глобального параметра** установите флажок **Включить обхода сервера-посредника**.
    
5. Щелкните **Всегда обходить**.
    
6. Нажмите кнопку **Сохранить**.
    
## <a name="see-also"></a>См. также

[Планирование обхода мультимедиа в Skype для бизнеса](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Развертывание обхода сервера-посредника в Skype для бизнеса Server](deploy-media-bypass.md)

