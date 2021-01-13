---
title: Добавление политики расположения на сетевой сайт в Skype для бизнеса Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Назначьте политики расположения E9-1-1 сетевым сайтам в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804279"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Добавление политики расположения на сетевой сайт в Skype для бизнеса Server
 
Назначьте политики расположения E9-1-1 сетевым сайтам в Skype для бизнеса Server Корпоративная голосовая связь. 
  
В следующих примерах покажем, как добавить политику расположения **Redmond,** задаемую в области "Создание политик расположения" в Skype для бизнеса [Server,](create-location-policies.md) к существующему сетевому сайту и создать новый сетевой сайт, использующий политику расположения **Redmond.**
  
Подробные сведения о работе с сетевыми сайтами см. в документации по Lync Server Management Shell для следующих cmdlets:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Назначение политики местоположения существующему сетевому узлу

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Выполните следующие командлеты для изменения существующего сетевого узла.
    
    Назначьте политику расположения с тегами **Redmond** существующему сетевому сайту **с именем Redmond.**
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Назначение политики местоположения новому сетевому узлу

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Выполните следующий командлет для создания нового сетевого узла.
    
    Создайте новый сетевой узел в области сети и назначьте ему политику местоположения с меткой **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


