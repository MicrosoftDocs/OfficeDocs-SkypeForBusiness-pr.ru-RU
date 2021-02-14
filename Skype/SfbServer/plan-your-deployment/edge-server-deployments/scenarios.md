---
title: Сценарии работы с edge-серверами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: Сводка. Просмотрите эти сценарии, чтобы помочь вам спланировать топологию edge Server в Skype для бизнеса Server.
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813799"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Сценарии работы с edge-серверами в Skype для бизнеса Server
 
**Сводка:** Просмотрите эти сценарии, чтобы помочь вам спланировать топологию edge Server в Skype для бизнеса Server.
  
We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement. После выбора хорошего кандидата можно ознакомиться с требованиями к среде, которые необходимо решить. Ниже приводится пример, применимый к любому из сценариев, поэтому мы сначала упомянум об этом.
  
Эти рисунки, которые показаны только для примера (и поэтому содержат примеры данных IPv4 и IPv6), представляют не фактический поток связи, а высокоуровневый вид возможного трафика. Сведения о портах также можно увидеть на схемах портов для каждого сценария ниже.
  
На схемах покажите .com для внешнего интерфейса и .net для внутреннего, который также является образцом материала; Конечно, ваши собственные записи могут сильно меняться, если вы объединяете свой окончательный план Edge.
  
Мы не включаем директора (который является необязательным компонентом) в схемы, но вы можете прочитать об этом отдельно (это упоминается в других темах планирования).
  
Как уже было отмечено выше, на схемах имеются примеры данных IPv6. Большая часть документации по планированию развертывания edge Server в Skype для бизнеса [Server](edge-server-deployments.md) относится к IPv4, но вы, конечно, поддерживаете, если вы хотите использовать IPv6. Обратите внимание, что в назначенной адресной области вам потребуется IPv6-адреса, а также они должны работать с внутренними и внешними адресами, как и с IP-адресами IPv4. Благодаря Windows можно использовать функцию двойного стека, которая является отдельным и отдельным сетевым стеком для IPv4 и IPv6. При необходимости вы сможете назначать адреса IPv4 и IPv6 одновременно.
  
There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.
  
> [!IMPORTANT]
> При использовании контроля допуска вызовов (CAC) необходимо использовать IPv4 во внутреннем интерфейсе, чтобы он работал. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT

В этом сценарии нет возможности для высокой доступности. Это означает, что вы будете тратить меньше на оборудование и упротите развертывание. Если высокая доступность является обязательной, ознакомьтесь с масштабированными консолидированными сценариями ниже.
  
![Сценарий edge для единой консолидированной границы с закрытым IP-адресом с использованием NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Схема порта

У нас также есть схема портов для одного консолидированного сервера.
  
![Сетевой периметр для сценария с одним консолидированным периметром](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Один консолидированный сервер Skype для бизнеса Server с общедоступными IP-адресами

В этом сценарии нет возможности для высокой доступности. Это означает, что вы будете тратить меньше на оборудование и упротите развертывание. Если высокая доступность является обязательной, ознакомьтесь с масштабированными консолидированными сценариями ниже.
  
![Сценарий edge для единой консолидированной границы с общедоступным IP-адресом](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Схема порта

У нас также есть схема портов для одного консолидированного сервера.
  
![Сетевой периметр для сценария с одним консолидированным периметром](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Масштабированный консолидированный пул Skype для бизнеса Server Edge, балансировка нагрузки на DNS, частные IP-адреса и NAT

В этом сценарии обеспечивается высокая доступность в развертывании Edge, что дает преимущества масштабируемости и поддержки от сбойов.
  
![Сценарий edge для масштабированной консолидированной границы, DNS LB с закрытым IP-адресом с использованием NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Схема порта

Также имеется схема масштабированных консолидированных пулов с балансировка нагрузки на DNS.
  
![Сетевой периметр для масштабированного консолидированного периметра по периметру с помощью DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Масштабированный консолидированный пул Skype для бизнеса Server Edge с балансировка нагрузки на DNS и общедоступными IP-адресами

В этом сценарии обеспечивается высокая доступность в развертывании Edge, что дает преимущества масштабируемости и поддержки от сбойов.
  
![Сценарий edge для масштабированной консолидированной границы, DNS LB с общедоступным IP-адресом](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Схема порта

Также имеется схема масштабированных консолидированных пулов с балансировка нагрузки на DNS.
  
![Сетевой периметр для масштабированного консолидированного периметра по периметру с помощью DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Масштабированный консолидированный пул Skype для бизнеса Server Edge с аппаратной балансировка нагрузки

В этом сценарии обеспечивается высокая доступность в развертывании Edge, что дает преимущества масштабируемости и поддержки от сбойов.
  
![Сценарий edge для масштабированной консолидированной границы с HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
