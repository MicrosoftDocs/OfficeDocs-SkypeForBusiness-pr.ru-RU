---
title: Создание связей между областями сети в Skype для бизнеса Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Создание или изменение связей между областями сети, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822469"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Создание связей между областями сети в Skype для бизнеса Server
 
Создание или изменение связей между областями сети, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server. 
  
Регионы в сети связываются с помощью физического подключения глобальной сети. Связь между областями сети создает связь между двумя областями, настроенными для контроля допуска вызовов (CAC), и устанавливает ограничения пропускной способности аудио- и видео-трафика между этими областями.
  
В примере топологии имеется связь между Северной Америкой и регионами APAC, а также связь между регионами EMEA и APAC. Каждая из этих областей ограничена пропускной способностью WAN, как описано в таблице сведений о пропускной способности связи между областями в [примере:](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)сбор требований для контроля допуска звонков в Skype для бизнеса Server.
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Создание связей между областями сети с помощью оболочки управления Skype для бизнеса Server

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Запустите командлет New-CsNetworkRegionLink, чтобы создать связи между областями и примените соответствующие профили политики пропускной способности. Например, выполните командлет:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Создание связей между областями сети с помощью панели управления Skype для бизнеса Server

1. Откройте панель управления Skype для бизнеса Server.
    
2. В левой области навигации щелкните элемент **Конфигурация сети**.
    
3. Нажмите кнопку навигации **Region Link** (Связь между областями).
    
4. Нажмите кнопку **Создать**.
    
5. На странице **New Region Link** (Создание связи между областями) щелкните поле **Имя** и введите имя для связи между областями сети.
    
6. Щелкните **Network Region #1** (Область сети 1), затем в списке выберите область сети, которую требуется связать с областью сети 2.
    
7. Щелкните **Network Region #2** (Область сети 2), а затем выберите в списке область, которую требуется связать с областью сети 1.
    
8. Кроме того, можно щелкнуть элемент **Bandwidth policy** (Политика пропускной способности), а затем выбрать профиль политики пропускной способности, который требуется применить к связи между областями сети.
    
    > [!NOTE]
    > Применять политику пропускной способности следует только в том случае, если для связи между областями сети имеются ограничения полосы пропускания и требуется использовать CAC для управления трафиком среды по этому каналу. 
  
9. Нажмите кнопку **Зафиксировать**.
    
10. Чтобы завершить создание связи между областями сети для топологии, повторите шаги с 4 по 9 с настройками для других областей.
    
## <a name="see-also"></a>См. также

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
