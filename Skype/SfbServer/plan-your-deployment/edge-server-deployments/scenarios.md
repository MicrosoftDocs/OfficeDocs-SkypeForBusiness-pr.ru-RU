---
title: Сценарии Edge Server в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: Сводка. Просмотрите эти сценарии, чтобы помочь вам спланировать топологию edge Server в Skype для бизнеса Server.
ms.openlocfilehash: 7d5c3b90f2b99b51eb74e0880c5a35f79025282a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763507"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Сценарии Edge Server в Skype для бизнеса Server
 
**Сводка:** Просмотрите эти сценарии, чтобы помочь вам спланировать топологию edge Server в Skype для бизнеса Server.
  
У нас есть несколько схем сценариев для визуализации и принятия решения о том, какую топологию Skype для бизнеса Server Edge Server вы хотите реализовать. После того как вы выбрали хорошего кандидата, вы можете прочитать о требованиях к окружающей среде, которые необходимо адресовать. Ниже приводится пример любого из сценариев, поэтому мы сначала об этом упоминаем.
  
Эти цифры, которые показаны только для целей (и как таковой содержат пример данных IPv4 и IPv6), представляют не фактический поток связи, а представление возможного трафика на высоком уровне. Сведения о порте также можно увидеть в диаграммах порта для каждого ниже сценария.
  
Диаграммы показывают .com для внешнего интерфейса и .net для внутреннего, который также является образцом материала; Конечно, ваши собственные записи могут быть совсем другими, когда вы собирали свой окончательный план Edge.
  
Мы не включаем Director (который является необязательным компонентом) ни в одной из схем, но вы можете прочитать об этом отдельно (это упоминается в других темах планирования).
  
Как уже отмечалось выше, в диаграммах есть пример данных IPv6. Большая часть документации в плане развертывания edge [Server](edge-server-deployments.md) в Skype для бизнеса Server будет относиться к IPv4, но вы, конечно, поддерживается, если вы хотите использовать IPv6. Обратите внимание, что вам потребуется IPv6-адреса в назначенной адресной области, и им необходимо работать с внутренним и внешним адресом, как и с ip-адресами IPv4. Благодаря Windows можно использовать функцию двойного стека, которая является отдельным сетевым стеком для IPv4 и IPv6. Это позволит при необходимости одновременно назначать адреса IPv4 и IPv6.
  
Существуют устройства NAT, которые позволяют использовать NAT64 (IPv6 для IPv4) и NAT66 (IPv6 для IPv6)), и это допустимо для Skype для бизнеса Server.
  
> [!IMPORTANT]
> Если вы используете управление приемом вызовов (CAC), для его работы необходимо использовать IPv4 во внутреннем интерфейсе. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Единый консолидированный Skype для бизнеса Server Edge Server с закрытыми IP-адресами и NAT

В этом сценарии нет возможности для высокой доступности. Это означает, что вы тратите меньше средств на оборудование и имеете более простое развертывание. Если обязательным является высокая доступность, ознакомьтесь с нижеспроимными сценариями с масштабированными консолидированными данными.
  
![Edge Scenario for Single Consolidated Edge with Private IP Using NAT.](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Схема порта

У нас также есть схема для портов для единых консолидированных edge Servers.
  
![Периметр сети для одного консолидированного края сценария edge.](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Единый консолидированный Skype для бизнеса Server Edge Server с общедоступными IP-адресами

В этом сценарии нет возможности для высокой доступности. Это означает, что вы тратите меньше средств на оборудование и имеете более простое развертывание. Если обязательным является высокая доступность, ознакомьтесь с нижеспроимными сценариями с масштабированными консолидированными данными.
  
![Сценарий edge для единого консолидированного края с общедоступным IP.](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Схема порта

У нас также есть схема для портов для единых консолидированных edge Servers.
  
![Периметр сети для одного консолидированного края сценария edge.](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Масштабированная консолидированная Skype для бизнеса Server Edge с балансировки нагрузки DNS и частными IP-адресами и NAT

При этом сценарии вы можете иметь высокую доступность в развертывании Edge, что дает вам преимущества масштабируемости и поддержки при сбойе.
  
![Сценарий edge для масштабированного консолидированного края, DNS LB с закрытым IP с помощью NAT.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Схема порта

У нас также есть схема для масштабированных консолидированных пулов Edge с балансировки нагрузки DNS.
  
![Периметр сети для сценария edge Scaled Consolidated Edge с помощью DNS LB.](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Масштабированный консолидированный Skype для бизнеса Server Edge с балансировки нагрузки DNS и общедоступными IP-адресами

При этом сценарии вы можете иметь высокую доступность в развертывании Edge, что дает вам преимущества масштабируемости и поддержки при сбойе.
  
![Сценарий edge для масштабированного консолидированного края, DNS LB с общедоступным IP.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Схема порта

У нас также есть схема для масштабированных консолидированных пулов Edge с балансировки нагрузки DNS.
  
![Периметр сети для сценария edge Scaled Consolidated Edge с помощью DNS LB.](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Масштабированный консолидированный Skype для бизнеса Server Edge с балансировки аппаратной нагрузки

При этом сценарии вы можете иметь высокую доступность в развертывании Edge, что дает вам преимущества масштабируемости и поддержки при сбойе.
  
![Сценарий edge для масштабированного консолидированного края с HLB.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
