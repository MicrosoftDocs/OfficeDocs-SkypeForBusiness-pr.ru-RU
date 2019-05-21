---
title: Маршрутизация с межмагистральными узлами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Сведения о том, как в Skype для бизнеса Server Enterprise поддерживается межмагистральная маршрутизация.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276833"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Маршрутизация с межмагистральными узлами в Skype для бизнеса Server
 
Сведения о том, как в Skype для бизнеса Server Enterprise поддерживается межмагистральная маршрутизация.
  
Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации. Это позволяет серверу Skype для бизнеса Server обеспечивать функции управления звонками для вызываемых систем телефонной связи. Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС. Аналогичным образом Skype для бизнеса Server может использовать несколько систем IP-УАТС для обмена звонками и их приема между телефонами УАТС из различных систем IP-УАТС. 
  
На приведенном ниже рисунке показана поддержка взаимодействия между шлюзом PSTN и IP-УАТС в Skype для бизнеса Server.
  
![Схема подключения Lync Server к ТСОП-шлюзу/IP-УАТС](../../media/inter_trunk01.jpg)
  
На следующем рисунке показан сервер Skype для бизнеса, соединяющий две системы семейства IP-АТС.
  
![Схема соединений между системами IP-УАТС с помощью Lync Server](../../media/inter_trunk02.jpg)
  

