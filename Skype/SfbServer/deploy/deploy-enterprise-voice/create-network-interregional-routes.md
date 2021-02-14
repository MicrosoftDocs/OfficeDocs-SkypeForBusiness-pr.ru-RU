---
title: Создание межрегиональных сетевых маршрутов в Skype для бизнеса Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Создание или изменение межрегиональных сетевых маршрутов, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.
ms.openlocfilehash: 86b7cf9e41cb20d82f0c3c6edd6bcbd74331d553
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822499"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Создание межрегиональных сетевых маршрутов в Skype для бизнеса Server
 
Создание или изменение межрегиональных сетевых маршрутов, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server. 
  
Межрегиональный сетевой маршрут определяет маршрут между двумя областями сети. Для каждой пары регионов сети в развертывании контроля допуска вызовов требуется межрегиональный сетевой маршрут. Благодаря этому каждая область сети в рамках развертывания может получить доступ к каждой другой области.
  
Хотя связи между областями устанавливают ограничения пропускной способности для подключений между регионами, межрегиональный маршрут определяет, какой связанный путь будет проходить соединение между областями.
  
В примере топологии необходимо определить межрегиональные сетевые маршруты для каждой из трех пар регионов: Северная Америка/EMEA, EMEA/APAC и Северная Америка/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Создание межрегиональных сетевых маршрутов с помощью skype для бизнеса Server Management Shell

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Выполните командлет **New-CsNetworkInterRegionRoute**, чтобы определить необходимые маршруты. Например, выполните команду:
    
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
    > Межрегиональный сетевой маршрут "Северная Америка/ APAC" требует двух связей между областями сети, так как между ними нет прямой связи между областями сети. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Создание межрегиональных сетевых маршрутов с помощью панели управления Skype для бизнеса Server

1. Откройте панель управления Skype для бизнеса Server.
    
2. На левой панели навигации щелкните **Конфигурация сети**.
    
3. Щелкните кнопку навигации **Маршрут региона**.
    
4. Щелкните **Создать**.
    
5. На странице **"Новый маршрут области"** щелкните **"Имя",** а затем введите имя для межрегионального сетевого маршрута.
    
6. Щелкните **Регион сети №1**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №2.
    
7. Щелкните **Регион сети №2**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №1.
    
8. Нажмите **кнопку** "Добавить" рядом с полем "Связи между областями сети", а затем добавьте связь между регионами сети, которая будет использоваться в маршруте между регионами сети. 
    
    > [!NOTE]
    > При создании маршрута между двумя регионами сети, между которыми отсутствует прямая связь, необходимо добавить все необходимые связи для создания полного маршрута. Например, для межрегионального маршрута сети "Северная Америка" или APAC требуются две связи между областями сети, так как между ними нет прямой связи между областями сети. 
  
9. Щелкните **Исполнить**.
    
10. Чтобы завершить создание межрегиональных сетевых маршрутов для топологии, повторите шаги с 4 по 9 с настройками для других межрегиональных сетевых маршрутов.
    
## <a name="see-also"></a>См. также

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
