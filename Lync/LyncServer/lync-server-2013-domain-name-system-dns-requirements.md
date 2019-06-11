---
title: 'Lync Server 2013: требования к системе доменных имен (DNS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771bf78f8477008345422cc61f63202c58fcdd14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="1c22c-102">Требования к системе доменных имен (DNS) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c22c-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c22c-103">_**Тема последнего изменения:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="1c22c-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="1c22c-104">Для развертывания сервера Lync Server необходимо создать записи DNS, которые обеспечивают обнаружение клиентов и серверов и, при необходимости, поддержку автоматического входа в систему, если ваша организация хочет ее поддерживать.</span><span class="sxs-lookup"><span data-stu-id="1c22c-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="1c22c-105">Lync Server использует DNS в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="1c22c-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="1c22c-106">Для выяснения внутренних серверов или пулов для обмена данными между серверами.</span><span class="sxs-lookup"><span data-stu-id="1c22c-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="1c22c-107">Для разрешения клиентам найти пул переднего плана или сервер Standard Edition, используемый для различных транзакций SIP.</span><span class="sxs-lookup"><span data-stu-id="1c22c-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="1c22c-108">Чтобы разрешить устройствам UC, которые не вошли в систему, найти пул переднего плана или сервер Standard Edition с веб-службой обновления устройств, получить обновления и отправить журналы.</span><span class="sxs-lookup"><span data-stu-id="1c22c-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="1c22c-109">Разрешить внешним серверам и клиентам подключаться к пограничным серверам или обратному прокси-серверу HTTP для обмена мгновенными сообщениями или конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="1c22c-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="1c22c-110">Чтобы разрешить внешним устройствам UC подключаться к веб-службе обновления устройства через пограничные серверы или обратный прокси-сервер HTTP и получать обновления.</span><span class="sxs-lookup"><span data-stu-id="1c22c-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="1c22c-111">Чтобы разрешить мобильным клиентам автоматически определять ресурсы веб-служб без необходимости вручную вводить URL-адреса в окне "Параметры устройства".</span><span class="sxs-lookup"><span data-stu-id="1c22c-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1c22c-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="1c22c-112">In This Section</span></span>

  - [<span data-ttu-id="1c22c-113">Определение требований DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c22c-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="1c22c-114">Требования к DNS для пулов интерфейсов на сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c22c-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="1c22c-115">Требования к DNS для серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c22c-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="1c22c-116">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c22c-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="1c22c-117">Требования DNS для автоматического входа клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c22c-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="1c22c-118">Требования к DNS для мобильных устройств с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c22c-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="1c22c-119">Балансировка нагрузки DNS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c22c-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

