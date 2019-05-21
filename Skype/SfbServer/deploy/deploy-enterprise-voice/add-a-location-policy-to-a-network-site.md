---
title: Добавление политики расположения на сайт сети в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Назначьте политики местоположения E9-1-1 на сайты сети в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 3653811298e7ce5659d4d416798010b3ac427732
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306876"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Добавление политики расположения на сайт сети в Skype для бизнеса Server
 
Назначьте политики местоположения E9-1-1 на сайты сети в Skype для бизнеса Server Enterprise. 
  
В следующих примерах показано, как добавить политику расположения в **Редмонде** , определенную в разделе [Создание политик местоположений в Skype для бизнеса Server](create-location-policies.md) , на существующий сайт сети и как создать новый сайт сети, использующий политику расположения в **Редмонде** .
  
Дополнительные сведения о работе с сетевыми сайтами можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Назначение политики местоположения существующему сетевому узлу

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Выполните следующие командлеты для изменения существующего сетевого узла.
    
    Назначьте политику расположения с меткой **Redmond** существующему сетевому сайту с именем **Redmond**.
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Назначение политики местоположения новому сетевому узлу

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Выполните следующий командлет для создания нового сетевого узла.
    
    Создайте новый сетевой сайт в области сети и назначьте ему политику расположения с меткой **Redmond**.
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


