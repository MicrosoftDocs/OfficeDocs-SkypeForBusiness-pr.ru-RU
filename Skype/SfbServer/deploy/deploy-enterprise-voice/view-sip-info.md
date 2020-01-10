---
title: Просмотр сведений об отдельных магистральных линиях SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Сводка: сведения о том, как просматривать сведения о магистральных линиях SIP в Skype для бизнеса Server.'
ms.openlocfilehash: 366e03c1a3ceef345a52bca6e038c9311fcc3003
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001129"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Просмотр сведений об отдельных магистральных линиях SIP в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как просматривать сведения о магистральных линиях SIP в Skype для бизнеса Server.
  
Магистральные линии SIP используются для подключения к голосовой сети Skype для бизнеса Server с помощью коммутируемой телефонной сети с открытым коммутируемым телефонным подключением. В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль. Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны. Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.
  
Однако в Skype для бизнеса Server для одного шлюза PSTN может быть назначено несколько каналов. Это означает, что шлюзы и магистральные линии больше не являются одними и теми же. В свою очередь, это означает, что администраторы должны использовать новый командлет [Get-кструнк](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) для просмотра сведений о отдельной внешней магистрали SIP.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Просмотр сведений о всех магистралях SIP

- Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Просмотр сведений об определенной магистрали SIP

- Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Просмотр информации обо всех линиях связи SIP, назначенных пулу

- В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
