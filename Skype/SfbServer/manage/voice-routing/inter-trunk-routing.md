---
title: Маршрутика между магистралью в Skype для бизнеса Server
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
description: 'Skype для бизнеса Server обеспечивает базовое управление сеансами с помощью поддержки маршрутиации интертрунков. '
ms.openlocfilehash: 2c2d2dfd1062414de0d11b9e77d7f9f1993a77a14266a8d121b43bfbc12335da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351499"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Маршрутика между магистралью в Skype для бизнеса Server

Skype для бизнеса Server обеспечивает базовое управление сеансами с помощью поддержки маршрутиации интертрунков. Эта возможность позволяет Skype для бизнеса Server функции управления вызовами для систем телефонии ниже по течению. Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС. Кроме того, Skype для бизнеса Server можно подключить две или несколько систем IP-PBX, чтобы между телефонами PBX можно было размещать и получить вызовы из различных систем IP-PBX. 


На следующем рисунке Skype для бизнеса Server обеспечение взаимосвязи между шлюзом PSTN и IP-PBX.

![Взаимосвязь между шлюзом PSTN и IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

На следующем рисунке Skype для бизнеса Server подключение двух систем IP-PBX.

![Skype для бизнеса Server двух систем IP-PGX](../../media/two-ip-pbx-systems.jpg)

