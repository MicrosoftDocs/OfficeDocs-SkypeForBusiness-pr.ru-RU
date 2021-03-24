---
title: Просмотр сведений об отдельных магистральных серверах SIP в Skype для бизнеса Server
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: Сводка. Узнайте, как просматривать сведения о магистральных серверах SIP в Skype для бизнеса Server.
ms.openlocfilehash: 989f9fea44bfcce67eba71b9f0b495b924f9e3a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103235"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Просмотр сведений об отдельных магистральных серверах SIP в Skype для бизнеса Server
 
**Сводка:** Узнайте, как просматривать сведения о магистральных серверах SIP в Skype для бизнеса Server.
  
Магистрали SIP используются для подключения голосовой связи Skype для бизнеса Server через сеть IP-телефонов с открытой телефонной сетью (PSTN). В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль. Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны. Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.
  
Однако в Skype для бизнеса Server теперь несколько магистральных серверов могут быть назначены одному шлюзу PSTN; это означает, что шлюзы и магистрали больше не одно и то же. В свою очередь, это означает, что администраторы должны использовать новый комлет [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) для просмотра сведений об отдельном магистрали SIP.
  
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