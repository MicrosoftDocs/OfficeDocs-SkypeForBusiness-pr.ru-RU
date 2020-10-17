---
title: 'Lync Server 2013: Маршрутизация между магистрали'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de302ec9bfbf81ea1d5c43ec568f2a0c0f6c19bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498496"
---
# <a name="inter-trunk-routing-in-lync-server-2013"></a>Маршрутизация между магистрали в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-08_

Lync Server 2013 обеспечивает базовое управление сеансами посредством поддержки маршрутизации по каналам связи. Эта новая возможность позволяет Lync Server обеспечивать функции управления звонками для вызываемых телефонных систем. Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС. Аналогично, Lync Server может соединить две или более системы IP-УАТС, чтобы звонки можно было размещать и принимать между телефонами УАТС из различных систем IP-УАТС.

На следующем рисунке показана платформа Lync Server 2013, обеспечивающая взаимодействие между шлюзом PSTN и IP-УАТС.

![Lync Server с подключением шлюза PSTN/IP-УАТС](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server с подключением шлюза PSTN/IP-УАТС")

На следующем рисунке показана платформа Lync Server 2013, соединяющая две системы IP-УАТС.

![Схема IP-PAX для системы связи Lync Server-PAX](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Схема IP-PAX для системы связи Lync Server-PAX")

</div>

<span> </span>

</div>

</div>

</div>

