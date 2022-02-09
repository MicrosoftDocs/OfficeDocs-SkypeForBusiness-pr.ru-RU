---
title: Создание ссылок сетевого региона в Skype для бизнеса Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Создание или изменение ссылок сетевого региона, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server.
ms.openlocfilehash: c2dd61cf8d2f8e8c77bdf3dde72035d9112348a4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417302"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Создание ссылок сетевого региона в Skype для бизнеса Server
 
Создание или изменение ссылок сетевого региона, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server. 
  
Регионы в сети связываются с помощью физического подключения глобальной сети. Ссылка в сетевом регионе создает связь между двумя регионами, настроенными для управления приемом вызовов (CAC), и устанавливает ограничения пропускной способности аудио- и видеопотока между этими регионами.
  
В примере топология имеет связь между регионами Северной Америки и APAC, а также связь между регионами EMEA и APAC. Каждая из этих областных ссылок ограничена пропускной способностью WAN, как описано в таблице Информация о пропускной способности полосы пропускания в регионе в примере: сбор требований для управления [приемом вызовов в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Создание ссылок сетевого региона с помощью Skype для бизнеса Server Management Shell

1. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.
    
2. Запустите командлет New-CsNetworkRegionLink, чтобы создать связи между областями и примените соответствующие профили политики пропускной способности. Например, выполните командлет:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Создание ссылок сетевого региона с помощью Skype для бизнеса Server панели управления

1. Откройте панель Skype для бизнеса Server управления.
    
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

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)