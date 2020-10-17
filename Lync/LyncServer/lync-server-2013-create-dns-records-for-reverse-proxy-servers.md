---
title: 'Lync Server 2013: создание записей DNS для обратных прокси-серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51af1c3179d8101a7e2f9942e15553b5831bce95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532216"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Создание записей DNS для обратных прокси-серверов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-29_

Создайте внешние записи A DNS, которые настраивают общедоступный внешний интерфейс для сервера ISA Server 2006 SP1, Forefront Threat Management Gateway 2010 Server или Internet Information Server Маршрутизация запросов, как описано в разделе [Настройка DNS для пограничной поддержки в Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Вам понадобятся записи DNS для полных доменных имен внешних веб-служб для каждого пула, директора (или пула директоров) и каждого простого URL-адреса.

Минимальное число DNS-записей для разрешения клиентов на обратном прокси-сервере:

  - Записи узла (A), которые определяют опубликованные внешние веб-службы для директоров и пулов директоров (например, **webdirext.contoso.com**).

  - Записи узла (A), которые определяют опубликованные внешние веб-службы для внешних веб-служб, размещенных на всех интерфейсных пулах и ролях сервера Standard Edition (например, **webext.contoso.com**).

  - Записи узлов (A) для простых URL-адресов (например, **dialin.contoso.com** и **meet.contoso.com**)

  - Запись узла (A) для внешней записи Lync Discover, а также предоставляет указатель на автообнаружение для всех веб-приложений, включая Lync Web App, планировщик и мобильность (например, **lyncdiscover.contoso.com**)

  - Записи узла (A) для URL-адреса сервера Office Web Apps (например, **officewebapp01.contoso.com**)

Дополнительные сведения [: сводка по DNS — обратный прокси-сервер в Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

