---
title: 'Skype для бизнеса Server: маршрутия между магистралью'
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
ms.openlocfilehash: 917f6bb1eb114202f06e1f1d2be0c7c126f42d8cf1614c2a05dcce0dde6bb9a6
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850174"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype для бизнеса Server: маршрутия между магистралью

Skype для бизнеса Server обеспечивает базовое управление сеансами с помощью поддержки маршрутиации интертрунков. Эта возможность позволяет Skype для бизнеса Server функции управления вызовами для систем телефонии ниже по течению. Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС. Кроме того, Skype для бизнеса Server можно подключить две или несколько систем IP-PBX, чтобы между телефонами PBX можно было размещать и получить вызовы из различных систем IP-PBX. 


На следующем рисунке Skype для бизнеса Server обеспечение взаимосвязи между шлюзом PSTN и IP-PBX.

![Взаимосвязь между шлюзом PSTN и IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

На следующем рисунке Skype для бизнеса Server подключение двух систем IP-PBX.

![Skype для бизнеса Server двух систем IP-PGX](../../media/two-ip-pbx-systems.jpg)

