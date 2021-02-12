---
title: Маршрутка между магистралью в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Узнайте, как Skype для бизнеса Server Корпоративная голосовая связь маршрутику между магистралью.
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825605"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Маршрутка между магистралью в Skype для бизнеса Server
 
Узнайте, как Skype для бизнеса Server Корпоративная голосовая связь маршрутику между магистралью.
  
Skype для бизнеса Server обеспечивает базовое управление сеансами посредством поддержки маршрутации между маршрутами. Это позволяет Skype для бизнеса Server предоставлять функции управления звонками для нижестоовых телефонных систем. Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС. Аналогичным образом, Skype для бизнеса Server может подключить две или несколько систем IP-УАКС, чтобы можно было делать и делать вызовы между телефонами УАПС из разных систем IP-УАКС. 
  
На следующем рисунке показано, как Skype для бизнеса Server обеспечивает взаимодействие между шлюзом STN и IP-PBX.
  
![Схема Lync Server, соединяющего шлюз PSTN/IP-PBX](../../media/inter_trunk01.jpg)
  
На следующем рисунке показано, как Skype для бизнеса Server подключает две системы IP-PBX.
  
![Схема взаимодействия Lync Server с системами IP-PAX](../../media/inter_trunk02.jpg)
  

