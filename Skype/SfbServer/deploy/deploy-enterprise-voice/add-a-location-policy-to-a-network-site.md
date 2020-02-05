---
title: Добавление политики расположения на сайт сети в Skype для бизнеса Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Назначьте политики местоположения E9-1-1 на сайты сети в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768282"
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
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Назначение политики местоположения новому сетевому узлу

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Выполните следующий командлет для создания нового сетевого узла.
    
    Создайте новый сетевой сайт в области сети и назначьте ему политику расположения с меткой **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


