---
title: Просмотр данных магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: Сводка. Узнайте, как просматривать сведения о магистральных SIP в Skype для бизнеса Server.
ms.openlocfilehash: dd33f9e7719802081a35ce718e7fd534ac107269
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399903"
---
# <a name="skype-for-business-server-view-information-about-individual-sip-trunks"></a>Skype для бизнеса Server. Просмотр сведений об отдельных магистральных магистрали SIP 
 
**Сводка:** Узнайте, как просматривать сведения о магистрали SIP в Skype для бизнеса Server.
  
Магистрали SIP используются для подключения Skype для бизнеса Server голосовой связи через ip-телефонную сеть с открытой телефонной сетью(PSTN). В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль. Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны. Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.
  
В Skype для бизнеса Server, однако, несколько магистральных магистрали теперь могут быть назначены одному шлюзу PSTN. Это означает, что шлюзы и магистрали уже не одно и то же. В свою очередь, это означает, что администраторы должны использовать новый комлет [Get-CsTrunk](/powershell/module/skype/get-cstrunk) для просмотра сведений об отдельном магистрали SIP.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Просмотр сведений для всех магистральных SIP

- Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Просмотр сведений для определенного магистрали SIP

- Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Просмотр сведений для всех магистральных SIP, задаваемой пулу

- В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
