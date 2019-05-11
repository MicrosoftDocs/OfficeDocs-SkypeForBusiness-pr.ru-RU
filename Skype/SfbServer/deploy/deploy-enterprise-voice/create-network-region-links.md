---
title: Создание связей между областями в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Создание или изменение связей между областями сети, используемые с корпоративной голосовой связи контроля допуска звонков в Скайп Business Server.
ms.openlocfilehash: c3b0f24ffdeea1724c89951ffc88516aea4dffb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892960"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Создание связей между областями в Скайп для Business Server
 
Создание или изменение связей между областями сети, используемые с корпоративной голосовой связи контроля допуска звонков в Скайп Business Server. 
  
Регионы в сети связываются с помощью физического подключения глобальной сети. Связь между областями сети создает канал между двумя областями, настроенными для контроля допуска звонков (CAC), и задает ограничения пропускной способности трафика аудио- и видеоданных между этими областями.
  
Пример топологии имеет связь между Северной Америке, а также Азиатско-Тихоокеанском регионе и ссылки между EMEA, а также Азиатско-Тихоокеанском регионе. Каждый из этих связей между областями ограниченной пропускной способностью глобальной сети, как описано в таблице сведения о пропускной способности связи между областями в [Пример: сбор требований для контроля допуска звонков в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Создание связей между областями с помощью Скайп для консоли Business Server

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Запустите командлет New-CsNetworkRegionLink, чтобы создать связи между областями и примените соответствующие профили политики пропускной способности. Например, выполните командлет:
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Создание связей между областями с помощью Скайп для панели управления Business Server

1. Откройте Скайп для панели управления Business Server.
    
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
