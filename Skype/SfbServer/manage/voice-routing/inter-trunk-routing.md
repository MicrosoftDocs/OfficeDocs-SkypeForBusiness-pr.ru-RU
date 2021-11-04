---
title: 'Skype для бизнеса Server: маршрутия между магистралью'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Skype для бизнеса Server обеспечивает базовое управление сеансами с помощью поддержки маршрутиации интертрунков. '
ms.openlocfilehash: ea21bf8e3697dc4b06b562f709d88903666cf3c5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774749"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype для бизнеса Server: маршрутия между магистралью

Skype для бизнеса Server обеспечивает базовое управление сеансами с помощью поддержки маршрутиации интертрунков. Эта возможность позволяет Skype для бизнеса Server функции управления вызовами для систем телефонии ниже по течению. Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС. Кроме того, Skype для бизнеса Server можно подключить две или несколько систем IP-PBX, чтобы между телефонами PBX можно было размещать и получить вызовы из различных систем IP-PBX. 


На следующем рисунке Skype для бизнеса Server обеспечение взаимосвязи между шлюзом PSTN и IP-PBX.

![Связь между шлюзом PSTN и IP-PBX.](../../media/pstn-gateway-ip-pbx.jpg)

На следующем рисунке Skype для бизнеса Server подключение двух систем IP-PBX.

![Skype для бизнеса Server две системы IP-PGX.](../../media/two-ip-pbx-systems.jpg)

