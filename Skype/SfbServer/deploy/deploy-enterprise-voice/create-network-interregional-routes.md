---
title: Создание сетевых маршрутов interregional в Скайп для Business Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Создание или изменение маршрутов interregional сети, которые используются контроля допуска звонков корпоративной голосовой связи в Скайп Business Server.
ms.openlocfilehash: b12f2f7d413be0031fd914157af4e9541095fd7f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892974"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Создание сетевых маршрутов interregional в Скайп для Business Server
 
Создание или изменение маршрутов interregional сети, которые используются контроля допуска звонков корпоративной голосовой связи в Скайп Business Server. 
  
Маршрут между регионами сети определяет маршрут между парой регионов сети. Маршрут между регионами сети требуется для каждой пары регионов сети в развертывании службы контроля допуска звонков. Это позволяет каждому региону сети в рамках развертывания осуществлять доступ к любому другому региону.
  
Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между регионами; маршруты же определяют путь, который должны пройти подключения от одного региона до другого.
  
В этом примере топологии необходимо определить маршруты между регионами сети для каждой пары регионов из трех: Северная Америка/EMEA, APAC/EMEA и APAC/Северная Америка. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Создание сетевой interregional маршрутов с помощью Скайп для консоли Business Server

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Выполните командлет **New-CsNetworkInterRegionRoute**, чтобы определить необходимые маршруты. Например, выполните:
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > Для маршрута между регионами "Северная Америка/APAC" требуются две связи между регионами сети, поскольку прямая сетевая связь между этими регионами отсутствует. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Создание сетевой interregional маршрутов с помощью Скайп для панели управления Business Server

1. Откройте Скайп для панели управления Business Server.
    
2. В левой области навигации щелкните элемент **Конфигурация сети**.
    
3. Щелкните кнопку навигации **Маршрут региона**.
    
4. Выберите **Создать**.
    
5. На странице **Новый маршрут региона** щелкните **Имя**, а затем введите имя для маршрута между регионами сети.
    
6. Щелкните **Регион сети №1**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №2.
    
7. Щелкните **Регион сети №2**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №2.
    
8. Щелкните **Добавить** рядом с полем **Связи между регионами сети**, а затем добавьте связь с регионом сети, которая будет использоваться в маршруте между регионами сети.
    
    > [!NOTE]
    > При создании маршрута между двумя регионами сети, между которыми отсутствует прямая связь, необходимо добавить все необходимые связи для создания полного маршрута. Например, для создания маршрута между регионами сети "Северная Америка" и "APAC" требуются две связи между сетевыми регионами, так как между ними отсутствует прямая связь. 
  
9. Нажмите **Исполнить**.
    
10. Чтобы завершить создание маршрутов между регионами сети, повторите шаги с 4 по 9 с указанием настроек для других маршрутов между сетевыми регионами.
    
## <a name="see-also"></a>См. также

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
