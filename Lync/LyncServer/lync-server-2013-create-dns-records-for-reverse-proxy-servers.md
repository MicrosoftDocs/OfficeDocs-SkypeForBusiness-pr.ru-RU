---
title: 'Lync Server 2013: создание DNS-записей для обратных прокси-серверов'
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
ms.openlocfilehash: 0f85b222688dcefd45030f2c05f7b59ce45ec0ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Создание DNS-записей для обратных прокси-серверов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-29_

Создание внешних DNS-записей, указывающих на открытый внешний интерфейс сервера ISA Server 2006 SP1, сервер или Маршрутизация запросов приложений Forefront Threat Management Gateway 2010, как описано в разделе [Настройка DNS для поддержки EDGE в Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Вам понадобятся записи DNS для полных доменных имен веб-служб для каждого пула, режиссера (или режиссера) и каждого простого URL-адреса.

Минимальный набор DNS-записей для разрешения клиента на обратный прокси, должны быть созданы следующие записи:

  - Записи узла (A), которые определяют опубликованные внешние веб-службы для режиссеров и пулов директоров (например, **webdirext.contoso.com**).

  - Записи узла (A), которые определяют опубликованные внешние веб-службы для внешних веб-служб, размещенных на любых интерфейсных пулах и ролях сервера Standard Edition (например, **webext.contoso.com**).

  - Записи узла (A) для простых URL-адресов (например, **Dialin.contoso.com** и **Meet.contoso.com**).

  - Запись узла (A) для внешней записи Lync Discover, а также предоставляет указатель на автообнаружение для всех веб-приложений, включая Lync Web App, планировщик и мобильность (например, **lyncdiscover.contoso.com**).

  - Записи узла (A) для URL-адреса сервера Office Web Apps (например, **officewebapp01.contoso.com**);

Подробности можно найти [в разделе Сводка DNS — обратный прокси-сервер в Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

