---
title: Создание ссылок на сетевой регион в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Создавайте и изменяйте ссылки на сетевые регионы, которые используются для управления допуском голосовых вызовов в Skype для бизнеса Server.
ms.openlocfilehash: 20fdbca9eb56fad9b69c6299177301e82fbf115a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767912"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Создание ссылок на сетевой регион в Skype для бизнеса Server
 
Создавайте и изменяйте ссылки на сетевые регионы, которые используются для управления допуском голосовых вызовов в Skype для бизнеса Server. 
  
Регионы в сети связываются с помощью физического подключения глобальной сети. Связь между областями сети создает канал между двумя областями, настроенными для контроля допуска звонков (CAC), и задает ограничения пропускной способности трафика аудио- и видеоданных между этими областями.
  
В примере топологии есть связь между областями "Северная Америка" и "APAC", а также ссылкой между регионами EMEA и APAC. Каждая из этих связей между регионами ограничена пропускной способностью по сети, как описано в таблице "сведения о пропускной способности ссылки на регион [" в примере: сбор требований для управления допуском звонков в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Создание ссылок на сетевой регион с помощью командной консоли Skype для бизнеса Server

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Запустите командлет New-CsNetworkRegionLink, чтобы создать связи между областями и примените соответствующие профили политики пропускной способности. Например, выполните командлет:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Создание ссылок на сетевой регион с помощью панели управления Skype для бизнеса Server

1. Откройте панель управления Skype для бизнеса Server.
    
2. В левой области навигации щелкните элемент **Конфигурация сети**.
    
3. Нажмите кнопку навигации **Связь между областями**.
    
4. Выберите **Создать**.
    
5. На странице **Создание связи между областями** щелкните поле **Имя** и введите имя для связи между областями сети.
    
6. Щелкните **Область сети 1**, затем в списке выберите область сети, которую требуется связать с областью сети 2.
    
7. Щелкните **Область сети 2**, а затем выберите в списке область, которую требуется связать с областью сети 1.
    
8. Кроме того, можно щелкнуть элемент **Политика пропускной способности**, а затем выбрать профиль политики пропускной способности, который требуется применить к связи между областями сети.
    
    > [!NOTE]
    > Применять политику пропускной способности следует только в том случае, если для связи между областями сети имеются ограничения полосы пропускания и требуется использовать CAC для управления трафиком среды по этому каналу. 
  
9. Нажмите **Исполнить**.
    
10. Чтобы завершить создание связи между областями сети для топологии, повторите шаги с 4 по 9 с настройками для других областей.
    
## <a name="see-also"></a>См. также

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
