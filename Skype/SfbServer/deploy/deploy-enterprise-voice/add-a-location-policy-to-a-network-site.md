---
title: Добавление политики расположения к сетевому сайту в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Назначение политик расположения E9-1-1 для сетевых узлов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: d167fb40e4a6318ce0621d365782cab3848cf284
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568265"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a>Добавление политики расположения к сетевому сайту в Skype для бизнеса Server 2015
 
Назначение политик расположения E9-1-1 для сетевых узлов в Скайп Business Server корпоративной голосовой связи. 
  
В следующих примерах показано, как добавить политику расположения **Redmond** , определенных в [Создание политик расположения в Скайп для Business Server 2015](create-location-policies.md) для существующего сетевого узла, а также для создания нового сетевого узла, который использует расположение **Redmond** политика.
  
Для получения дополнительных сведений о работе с сетевыми узлами обратитесь к документации Командная консоль Lync Server для следующих командлетов:
  
- **Новый CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **SET-CsNetworkSite**
    
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


