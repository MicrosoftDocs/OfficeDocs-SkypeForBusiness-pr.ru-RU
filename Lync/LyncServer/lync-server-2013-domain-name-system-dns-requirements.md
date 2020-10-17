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
ms.openlocfilehash: d7ddbab6e4d0b1a0654c91027cbf0676ad6445f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501136"
---
# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="69fd7-102">Требования к системе доменных имен (DNS) для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fd7-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69fd7-103">_**Последнее изменение темы:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="69fd7-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="69fd7-104">Для развертывания Lync Server необходимо создать записи службы доменных имен (DNS), которые обеспечивают обнаружение клиентов и серверов, а также (при необходимости) поддержку автоматического входа клиента, если ваша организация хочет ее поддерживать.</span><span class="sxs-lookup"><span data-stu-id="69fd7-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="69fd7-105">Lync Server использует DNS следующим образом:</span><span class="sxs-lookup"><span data-stu-id="69fd7-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="69fd7-106">Для обнаружения внутренних серверов или пулов для межсерверной связи.</span><span class="sxs-lookup"><span data-stu-id="69fd7-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="69fd7-107">, Чтобы разрешить клиентам обнаруживать пул переднего плана или сервер Standard Edition, используемый для различных транзакций SIP.</span><span class="sxs-lookup"><span data-stu-id="69fd7-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="69fd7-108">Чтобы разрешить устройствам Объединенных коммуникаций, не вошедшим в систему, обнаруживать интерфейсный пул или сервер Standard Edition с веб-службой обновления устройств, получать обновления и отправлять журналы.</span><span class="sxs-lookup"><span data-stu-id="69fd7-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="69fd7-109">, Чтобы разрешить внешним серверам и клиентам подключаться к пограничным серверам или обратному прокси-серверу HTTP для обмена мгновенными сообщениями или конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="69fd7-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="69fd7-110">Чтобы разрешить внешним устройствам UC подключаться к веб-службе обновления устройств через пограничные серверы или обратный прокси-сервер HTTP и получать обновления.</span><span class="sxs-lookup"><span data-stu-id="69fd7-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="69fd7-111">чтобы разрешить мобильным клиентам автоматически обнаруживать ресурсы веб-служб без того, чтобы пользователи вручную вводили URL-адреса в параметрах устройства.</span><span class="sxs-lookup"><span data-stu-id="69fd7-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69fd7-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="69fd7-112">In This Section</span></span>

  - [<span data-ttu-id="69fd7-113">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fd7-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="69fd7-114">Требования DNS для пулов переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fd7-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="69fd7-115">Требования DNS для серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fd7-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="69fd7-116">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fd7-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="69fd7-117">Требования DNS для автоматического входа клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fd7-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="69fd7-118">Требования DNS для мобильных устройств с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fd7-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="69fd7-119">Балансировка нагрузки на DNS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fd7-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

