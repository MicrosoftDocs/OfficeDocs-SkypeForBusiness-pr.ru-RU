---
title: 'Lync Server 2013: межмагистральная маршрутизация'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204402ba6620fa75b64bb9710ce979b44b63f412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a>Маршрутизация с межмагистральными организациями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-08_

Lync Server 2013 обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации. Благодаря этой новой возможности сервер Lync Server обеспечивает функции управления звонками для вызываемых систем телефонной связи. Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС. Аналогичным образом Lync Server может присоединиться к нескольким системам IP-УАТС, чтобы звонить и принимать их между телефонами УАТС из различных систем IP-УАТС.

На рисунке ниже показана интеграция сервера Lync Server 2013, обеспечивающая взаимодействие между шлюзом PSTN и IP-УАТС.

![Lync Server подключение PSTN Gateway/IP-УАТС] (images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server подключение PSTN Gateway/IP-УАТС")

На следующем рисунке показана платформа Lync Server 2013, соединяющая две системы IP-УАТС.

![Схема IP-схемы для совместного подключения к Lync Server — система PAX] (images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Схема IP-схемы для совместного подключения к Lync Server — система PAX")

</div>

<span> </span>

</div>

</div>

</div>

