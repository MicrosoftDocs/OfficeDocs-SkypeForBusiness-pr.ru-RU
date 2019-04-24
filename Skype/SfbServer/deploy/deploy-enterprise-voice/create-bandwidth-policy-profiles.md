---
title: Создание профилей пропускной способности политики в Скайп для Business Server
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
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Создание или изменение политики пропускной способности, которые используются с корпоративной голосовой связи контроля допуска звонков в Скайп для Business Server.
ms.openlocfilehash: 26f0e81d4f148888b9c8f61b774dcd476bd102d5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223517"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Создание профилей пропускной способности политики в Скайп для Business Server 
 
Создание или изменение политики пропускной способности, которые используются с корпоративной голосовой связи контроля допуска звонков в Скайп для Business Server. 
  
Политики пропускной способности определяют ограничения пропускной способности сети для режимов передачи звука и видеоизображения в реальном времени. Политики пропускной способности, применяемые tobandwidth политики профилей, которые могут применяться к нескольким сетевых узлов для контроля допуска звонков.
  
Для указания, какие пропускной способности ограничивает вы должны в вашем развертывании CAC см [плана для контроля допуска звонков в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
Примеры политик, созданных в следующей процедуре, задают ограничения для общего трафика аудиоданных, отдельных аудиосеансов, общего трафика видеоданных и отдельных видеосеансов. Например, профиль политики пропускной способности 5Mb_Link задает следующие ограничения: 
  
- Аудиоданные: 2 000 кбит/с
    
- Аудиосеансы: 200 кбит/с
    
- Видеоданные: 1 400 кбит/с
    
- Видеосеансы: 700 кбит/с
    
> [!NOTE]
> Минимальное значение для аудиосеанса 40 кбит/с. Минимальное значение для видеосеанса 100 кбит/с. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Создание профилей политики пропускной способности с помощью Скайп для консоли Business Server

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Выполните командлет New-CsNetworkBandwidthPolicyProfile для каждого создаваемого профиля политики пропускной способности. Пример:
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Создание профилей политики пропускной способности с помощью Скайп для панели управления Business Server

1. Откройте Скайп для панели управления Business Server.
    
2. В левой области навигации щелкните **Конфигурация сети**.
    
3. Нажмите кнопку навигации **Профиль политики**.
    
4. Выберите **Создать**.
    
5. На странице **создания профиля политики** в поле щелкните **Имя**, затем введите имя профиля политики пропускной способности.
    
6. Щелкните **Ограничение для звукового сеанса**, затем введите максимальную скорость в кбит/с, общую для всех сеансов звуковой связи.
    
7. Щелкните **Ограничение для видео**, затем введите максимальную скорость в кбит/с для отдельного сеанса звуковой связи.
    
8. Щелкните **Ограничение для видео**, затем введите максимальную скорость в кбит/с, общую для всех сеансов видеосвязи.
    
9. Щелкните **Ограничение для видеосеанса**, затем введите максимальную скорость в кбит/с для отдельного сеанса видеосвязи.
    
10. Щелкните **Описание** и введите дополнительные сведения о профиле политики пропускной способности (не обязательно).
    
11. Нажмите **Исполнить**.
    
12. Чтобы завершить создание профилей политики пропускной способности для топологии, повторите шаги с 4 по 11 для остальных профилей политики пропускной способности.
    
## <a name="see-also"></a>См. также

[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
