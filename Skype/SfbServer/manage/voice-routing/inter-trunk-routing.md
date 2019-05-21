---
title: Маршрутизация с межмагистральными узлами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации. '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274970"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Маршрутизация с межмагистральными узлами в Skype для бизнеса Server

Skype для бизнеса Server обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации. Эта возможность позволяет Skype для бизнеса Server обеспечивать функции управления звонками для более нижестоящих систем телефонной связи. Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС. Аналогичным образом Skype для бизнеса Server может использовать несколько систем IP-УАТС для обмена звонками и их приема между телефонами УАТС из различных систем IP-УАТС. 


На приведенном ниже рисунке показана поддержка взаимодействия между шлюзом PSTN и IP-УАТС в Skype для бизнеса Server.

![Связь между шлюзом PSTN и IP-УАТС](../../media/pstn-gateway-ip-pbx.jpg)

На следующем рисунке показан сервер Skype для бизнеса, соединяющий две системы семейства IP-АТС.

![Skype для бизнеса Server, соединяющий две системы IP-ПГКС](../../media/two-ip-pbx-systems.jpg)

