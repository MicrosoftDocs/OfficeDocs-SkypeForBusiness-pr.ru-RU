---
title: Маршрутка между магистралью в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype для бизнеса Server обеспечивает базовое управление сеансами посредством поддержки маршрутной маршрутации между межуголковой инфраструктурой. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814129"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Маршрутка между магистралью в Skype для бизнеса Server

Skype для бизнеса Server обеспечивает базовое управление сеансами посредством поддержки маршрутной маршрутации между межуголковой инфраструктурой. Эта возможность позволяет Skype для бизнеса Server предоставлять функции управления звонками для нижестоовых телефонных систем. Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС. Аналогичным образом, Skype для бизнеса Server может подключить две или несколько систем IP-УАКС, чтобы можно было размещать и получить вызовы между телефонами УАПС из разных систем IP-УАКС. 


На следующем рисунке показано, как Skype для бизнеса Server обеспечивает взаимодействие между шлюзом STN и IP-PBX.

![Взаимодействие между шлюзом PSTN и IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

На следующем рисунке показано, как Skype для бизнеса Server подключает две системы IP-PBX.

![Skype для бизнеса Server, подключающий две системы IP-PGX](../../media/two-ip-pbx-systems.jpg)

