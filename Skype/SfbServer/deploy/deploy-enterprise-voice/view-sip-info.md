---
title: Просмотр сведений об отдельных магистралях SIP в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Сводка: Узнайте, как для просмотра сведений о магистралях SIP в Скайп для Business Server 2015.'
ms.openlocfilehash: c307d4e9b18b7ff5fda8d8d0deaa4eb88ba5b6b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a>Просмотр сведений об отдельных магистралях SIP в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как для просмотра сведений о магистралях SIP в Скайп для Business Server 2015.
  
Магистралях SIP, используются для подключения Скайп Business Server голосовой связи через IP-телефона сеть с общей переключения телефонной сети общего пользования (PSTN). В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль. Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны. Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.
  
В Скайп Business Server Однако несколько магистралей можно теперь назначить один шлюз ТСОП; Это означает, что магистральных линий связи и шлюзами больше не одной и той же. В свою очередь, это означает, что администраторы должны использовать новый командлет [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) для просмотра сведений об отдельных канала SIP.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Просмотр сведений о всех магистралях SIP

- Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Просмотр сведений об определенной магистрали SIP

- Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Просмотр информации обо всех линиях связи SIP, назначенных пулу

- В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```


