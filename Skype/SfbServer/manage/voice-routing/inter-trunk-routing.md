---
title: Маршрутизация с межмагистральными узлами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации. '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816969"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Маршрутизация с межмагистральными узлами в Skype для бизнеса Server

Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации. Эта возможность позволяет Skype для бизнеса Server обеспечивать функции управления звонками для более нижестоящих систем телефонной связи. Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС. Аналогичным образом Skype для бизнеса Server может использовать несколько систем IP-УАТС для обмена звонками и их приема между телефонами УАТС из различных систем IP-УАТС. 


На приведенном ниже рисунке показана поддержка взаимодействия между шлюзом PSTN и IP-УАТС в Skype для бизнеса Server.

![Связь между шлюзом PSTN и IP-УАТС](../../media/pstn-gateway-ip-pbx.jpg)

На следующем рисунке показан сервер Skype для бизнеса, соединяющий две системы семейства IP-АТС.

![Skype для бизнеса Server, соединяющий две системы IP-ПГКС](../../media/two-ip-pbx-systems.jpg)

