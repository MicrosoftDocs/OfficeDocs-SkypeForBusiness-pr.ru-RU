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
ms.openlocfilehash: 117b13802b79a66c7078f8dcd9ca92a14f390a17
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="07d77-102">Создание записей DNS для обратных прокси-серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07d77-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07d77-103">_**Последнее изменение темы:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="07d77-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="07d77-104">Создайте внешние записи A DNS, которые настраивают общедоступный внешний интерфейс для сервера ISA Server 2006 SP1, Forefront Threat Management Gateway 2010 Server или Internet Information Server Маршрутизация запросов, как описано в разделе [Настройка DNS для пограничной поддержки в Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span><span class="sxs-lookup"><span data-stu-id="07d77-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="07d77-105">Вам понадобятся записи DNS для полных доменных имен внешних веб-служб для каждого пула, директора (или пула директоров) и каждого простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="07d77-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="07d77-106">Минимальное число DNS-записей для разрешения клиентов на обратном прокси-сервере:</span><span class="sxs-lookup"><span data-stu-id="07d77-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="07d77-107">Записи узла (A), которые определяют опубликованные внешние веб-службы для директоров и пулов директоров (например, **webdirext.contoso.com**).</span><span class="sxs-lookup"><span data-stu-id="07d77-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="07d77-108">Записи узла (A), которые определяют опубликованные внешние веб-службы для внешних веб-служб, размещенных на всех интерфейсных пулах и ролях сервера Standard Edition (например, **webext.contoso.com**).</span><span class="sxs-lookup"><span data-stu-id="07d77-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="07d77-109">Записи узлов (A) для простых URL-адресов (например, **dialin.contoso.com** и **meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="07d77-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="07d77-110">Запись узла (A) для внешней записи Lync Discover, а также предоставляет указатель на автообнаружение для всех веб-приложений, включая Lync Web App, планировщик и мобильность (например, **lyncdiscover.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="07d77-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="07d77-111">Записи узла (A) для URL-адреса сервера Office Web Apps (например, **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="07d77-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="07d77-112">Дополнительные сведения [: сводка по DNS — обратный прокси-сервер в Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="07d77-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

