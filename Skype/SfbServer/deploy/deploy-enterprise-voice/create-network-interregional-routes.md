---
title: Создание сетевых межрегиональных маршрутов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Создание или изменение сетевых межрегиональных маршрутов, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server.
ms.openlocfilehash: 4aa831c33049e2e77a298f96de80d9bad2d296e4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833875"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Создание сетевых межрегиональных маршрутов в Skype для бизнеса Server
 
Создание или изменение сетевых межрегиональных маршрутов, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server. 
  
Сетевой межрегиональный маршрут определяет маршрут между парой сетевых регионов. Для каждой пары сетевых регионов в развертывании управления приемом вызовов требуется сетевой межрегиональный маршрут. Благодаря этому каждая область сети в рамках развертывания может получить доступ к каждой другой области.
  
В то время как ссылки региона устанавливают ограничения пропускной способности для подключений между регионами, межрегиональный маршрут определяет, какой связанный путь будет проходить подключение из одного региона в другой.
  
В примере топологии необходимо определить сетевые межрегиональные маршруты для каждой из трех пар регионов: Северная Америка/EMEA, EMEA/APAC и Северная Америка/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Создание сетевых межрегиональных маршрутов с помощью Skype для бизнеса Server Management Shell

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Выполните командлет **New-CsNetworkInterRegionRoute**, чтобы определить необходимые маршруты. Например, выполните:
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > Межрегиональный сетевой маршрут Северная Америка и APAC требует двух сетевых областей, так как между ними нет прямой связи между регионами сети. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Создание сетевых межрегиональных маршрутов с помощью Skype для бизнеса Server панели управления

1. Откройте панель Skype для бизнеса Server управления.
    
2. На левой панели навигации щелкните **Конфигурация сети**.
    
3. Щелкните кнопку навигации **Маршрут региона**.
    
4. Щелкните **Создать**.
    
5. На странице **Маршрут нового региона** щелкните **Имя,** а затем введите имя для сетевого межрегионального маршрута.
    
6. Щелкните **Регион сети №1**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №2.
    
7. Щелкните **Регион сети №2**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №1.
    
8. Щелкните **Добавить** рядом с **полем Сетевые регионы ссылки,** а затем добавить ссылку сетевого региона, которая будет использоваться в сетевом межрегиональный маршрут.
    
    > [!NOTE]
    > При создании маршрута между двумя регионами сети, между которыми отсутствует прямая связь, необходимо добавить все необходимые связи для создания полного маршрута. Например, межрегиональный сетевой маршрут Северной Америки и APAC требует двух сетевых областей, поскольку между ними нет прямой связи между регионами сети. 
  
9. Щелкните **Исполнить**.
    
10. Чтобы завершить создание сетевых межрегиональных маршрутов для топологии, повторите шаги 4-9 с настройками для других сетевых межрегиональных маршрутов.
    
## <a name="see-also"></a>См. также

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)