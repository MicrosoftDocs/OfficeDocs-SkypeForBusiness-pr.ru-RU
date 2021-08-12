---
title: Включить управление приемом вызовов в Skype для бизнеса Server
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
description: Включить управление приемом вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 65c9ea2e4732ca4c2c069479826f353a9a2dabf82d6eee35c6feaf1c14391ddd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281202"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Включить управление приемом вызовов в Skype для бизнеса Server
 
Включить управление приемом вызовов в Skype для бизнеса Server Корпоративная голосовая связь. 
  
Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Включить управление приемом вызовов с помощью Skype для бизнеса Server Management Shell

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Включить управление приемом вызовов с помощью Skype для бизнеса Server панели управления

1. Откройте панель Skype для бизнеса Server управления.
    
2. В левой панели навигации щелкните **Network Configuration** (Параметры сети).
    
3. Нажмите кнопку навигации **Global** (Глобальные).
    
4. Выберите **Global** (Глобальные) в списке и затем в меню **Edit** (Изменить) выберите **Show Details** (Показать сведения).
    
5. На странице **Edit Global Settings** (Изменение глобальных параметров) установите флажок **Enable call admission control** (Включить службу контроля допуска звонков).
    
    > [!NOTE]
    > Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок. 
  
6. Щелкните **Commit** (Применить). 
    
## <a name="see-also"></a>См. также

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)