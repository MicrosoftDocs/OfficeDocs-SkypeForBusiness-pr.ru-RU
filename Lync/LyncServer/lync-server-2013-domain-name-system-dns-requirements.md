---
title: 'Lync Server 2013: требования к системе доменных имен (DNS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="55c04-102">Требования к системе доменных имен (DNS) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c04-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55c04-103">_**Тема последнего изменения:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="55c04-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="55c04-104">Для развертывания сервера Lync Server необходимо создать записи DNS, которые обеспечивают обнаружение клиентов и серверов и, при необходимости, поддержку автоматического входа в систему, если ваша организация хочет ее поддерживать.</span><span class="sxs-lookup"><span data-stu-id="55c04-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="55c04-105">Lync Server использует DNS в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="55c04-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="55c04-106">Для выяснения внутренних серверов или пулов для обмена данными между серверами.</span><span class="sxs-lookup"><span data-stu-id="55c04-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="55c04-107">Для разрешения клиентам найти пул переднего плана или сервер Standard Edition, используемый для различных транзакций SIP.</span><span class="sxs-lookup"><span data-stu-id="55c04-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="55c04-108">Чтобы разрешить устройствам UC, которые не вошли в систему, найти пул переднего плана или сервер Standard Edition с веб-службой обновления устройств, получить обновления и отправить журналы.</span><span class="sxs-lookup"><span data-stu-id="55c04-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="55c04-109">Разрешить внешним серверам и клиентам подключаться к пограничным серверам или обратному прокси-серверу HTTP для обмена мгновенными сообщениями или конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="55c04-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="55c04-110">Чтобы разрешить внешним устройствам UC подключаться к веб-службе обновления устройства через пограничные серверы или обратный прокси-сервер HTTP и получать обновления.</span><span class="sxs-lookup"><span data-stu-id="55c04-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="55c04-111">Чтобы разрешить мобильным клиентам автоматически определять ресурсы веб-служб без необходимости вручную вводить URL-адреса в окне "Параметры устройства".</span><span class="sxs-lookup"><span data-stu-id="55c04-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="55c04-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="55c04-112">In This Section</span></span>

  - [<span data-ttu-id="55c04-113">Определение требований DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c04-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="55c04-114">Требования к DNS для пулов интерфейсов на сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c04-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="55c04-115">Требования к DNS для серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c04-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="55c04-116">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c04-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="55c04-117">Требования DNS для автоматического входа клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c04-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="55c04-118">Требования к DNS для мобильных устройств с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c04-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="55c04-119">Балансировка нагрузки DNS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55c04-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

