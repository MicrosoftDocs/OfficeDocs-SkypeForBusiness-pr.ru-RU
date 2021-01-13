---
title: Включить контроль допуска звонков в Skype для бизнеса Server
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Включить контроль допуска звонков в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 9ea8b03b48827abbb73e3d6e93ffb88ab93ad1ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831019"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Включить контроль допуска звонков в Skype для бизнеса Server
 
Включить контроль допуска звонков в Skype для бизнеса Server Корпоративная голосовая связь. 
  
Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>To enable call admission control by using Skype for Business Server Management Shell

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Чтобы включить контроль допуска звонков с помощью панели управления Skype для бизнеса Server

1. Откройте панель управления Skype для бизнеса Server.
    
2. В левой панели навигации щелкните **Network Configuration** (Параметры сети).
    
3. Нажмите кнопку навигации **Global** (Глобальные).
    
4. Выберите **Global** (Глобальные) в списке и затем в меню **Edit** (Изменить) выберите **Show Details** (Показать сведения).
    
5. На странице **Edit Global Settings** (Изменение глобальных параметров) установите флажок **Enable call admission control** (Включить службу контроля допуска звонков).
    
    > [!NOTE]
    > Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок. 
  
6. Щелкните **Commit** (Применить). 
    
## <a name="see-also"></a>См. также

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
