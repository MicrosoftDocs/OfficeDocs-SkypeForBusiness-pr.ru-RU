---
title: Добавьте политику расположения на сетевой сайт в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Назначение политик расположения E9-1-1 сетевым сайтам в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 9d248d91703284d58b27e5fd593af95ddf4edaf3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765957"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Добавьте политику расположения на сетевой сайт в Skype для бизнеса Server
 
Назначение политик расположения E9-1-1 сетевым сайтам в Skype для бизнеса Server Корпоративная голосовая связь. 
  
В следующих примерах покажите, как добавить политику расположения [Redmond,](create-location-policies.md) определяемую в Политике создания расположения в Skype для бизнеса Server на существующем сетевом сайте, и как создать новый сетевой сайт, использующий политику расположения **Redmond.** 
  
Сведения о работе с сетевыми сайтами см. в документации по Lync Server Management Shell для следующих групп:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Назначение политики местоположения существующему сетевому узлу

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Выполните следующие командлеты для изменения существующего сетевого узла.
    
    Назначьте политику расположения с тегами **Redmond** существующему сетевому сайту с именем **Redmond**.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Назначение политики местоположения новому сетевому узлу

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Выполните следующий командлет для создания нового сетевого узла.
    
    Создайте новый сетевой узел в области сети и назначьте ему политику местоположения с меткой **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


