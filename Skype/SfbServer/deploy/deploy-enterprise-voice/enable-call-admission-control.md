---
title: Включение управления допуском звонков в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Включите управление допуском звонков в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: a1a2259c754af0275e473e6c0d175039450cecf7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240497"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Включение управления допуском звонков в Skype для бизнеса Server
 
Включите управление допуском звонков в корпоративной голосовой связи Skype для бизнеса Server. 
  
Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Включение управления допуском звонков с помощью командной консоли Skype для бизнеса Server

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Включение управления допуском звонков с помощью панели управления "Skype для бизнеса" на сервере

1. Откройте панель управления Skype для бизнеса Server.
    
2. В левой области навигации щелкните элемент **Конфигурация сети**.
    
3. Нажмите кнопку навигации **Глобальные**.
    
4. Выберите **Глобальные** в списке и затем в меню **Изменить** выберите **Показать сведения**.
    
5. На странице **Изменение глобальных параметров** установите флажок **Включить контроль допуска звонков**.
    
    > [!NOTE]
    > Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок. 
  
6. Нажмите **Исполнить**. 
    
## <a name="see-also"></a>См. также

[Get-Кснетворкконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
