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

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="c1d79-102">Создание DNS-записей для обратных прокси-серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1d79-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1d79-103">_**Тема последнего изменения:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="c1d79-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="c1d79-104">Создание внешних DNS-записей, указывающих на открытый внешний интерфейс сервера ISA Server 2006 SP1, сервер или Маршрутизация запросов приложений Forefront Threat Management Gateway 2010, как описано в разделе [Настройка DNS для поддержки EDGE в Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span><span class="sxs-lookup"><span data-stu-id="c1d79-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="c1d79-105">Вам понадобятся записи DNS для полных доменных имен веб-служб для каждого пула, режиссера (или режиссера) и каждого простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="c1d79-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="c1d79-106">Минимальный набор DNS-записей для разрешения клиента на обратный прокси, должны быть созданы следующие записи:</span><span class="sxs-lookup"><span data-stu-id="c1d79-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="c1d79-107">Записи узла (A), которые определяют опубликованные внешние веб-службы для режиссеров и пулов директоров (например, **webdirext.contoso.com**).</span><span class="sxs-lookup"><span data-stu-id="c1d79-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="c1d79-108">Записи узла (A), которые определяют опубликованные внешние веб-службы для внешних веб-служб, размещенных на любых интерфейсных пулах и ролях сервера Standard Edition (например, **webext.contoso.com**).</span><span class="sxs-lookup"><span data-stu-id="c1d79-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="c1d79-109">Записи узла (A) для простых URL-адресов (например, **Dialin.contoso.com** и **Meet.contoso.com**).</span><span class="sxs-lookup"><span data-stu-id="c1d79-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="c1d79-110">Запись узла (A) для внешней записи Lync Discover, а также предоставляет указатель на автообнаружение для всех веб-приложений, включая Lync Web App, планировщик и мобильность (например, **lyncdiscover.contoso.com**).</span><span class="sxs-lookup"><span data-stu-id="c1d79-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="c1d79-111">Записи узла (A) для URL-адреса сервера Office Web Apps (например, **officewebapp01.contoso.com**);</span><span class="sxs-lookup"><span data-stu-id="c1d79-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="c1d79-112">Подробности можно найти [в разделе Сводка DNS — обратный прокси-сервер в Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="c1d79-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

