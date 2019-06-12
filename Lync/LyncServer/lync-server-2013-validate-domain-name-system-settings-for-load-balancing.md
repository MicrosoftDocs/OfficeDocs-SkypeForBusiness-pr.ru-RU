---
title: 'Lync Server 2013: Проверка параметров системы доменных имен для балансировки нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d56219dc36859eb37a766a94f827fb0c28a9909
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="17c88-102">Проверка параметров системы доменных имен для балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17c88-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17c88-103">_**Тема последнего изменения:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="17c88-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="17c88-104">Для поддержки полного доменного имени, используемого службой балансировки нагрузки DNS, необходимо подготовить DNS для разрешения полного доменного имени пула (например, pool01.contoso.com) в IP-адреса всех серверов в пуле (например, 192.168.1.1, 192.168.1.2 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="17c88-104">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="17c88-105">Вы должны включать только IP-адреса серверов, которые развернут в данный момент.</span><span class="sxs-lookup"><span data-stu-id="17c88-105">You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="17c88-106">Кроме того, при использовании балансировки нагрузки DNS для пулов Edge требуются следующие записи DNS:</span><span class="sxs-lookup"><span data-stu-id="17c88-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="17c88-107">Для службы пограничного доступа Lync Server вы должны иметь одну запись для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="17c88-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="17c88-108">Каждая запись должна разрешать полное доменное имя службы пограничного доступа Lync Server (например, sip.contoso.com) к IP-адресу службы пограничного доступа Lync Server на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="17c88-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="17c88-109">Для службы Edge для веб-конференций Lync Server необходимо иметь одну запись для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="17c88-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="17c88-110">Каждая запись должна разрешать полное доменное имя службы Microsoft Edge для веб-конференций Lync Server (например, webconf.contoso.com) в IP-адрес службы Edge веб-конференций Lync Server на одном из пограничных серверов пула.</span><span class="sxs-lookup"><span data-stu-id="17c88-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="17c88-111">Для службы звука и видео в Lync Server необходимо иметь одну запись для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="17c88-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="17c88-112">Каждая запись должна разрешать полное доменное имя (например, av.contoso.com) в качестве FQDN для службы "звук и видео" в Lync Server, а также в IP-адресе службы на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="17c88-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="17c88-113">Если вы хотите использовать балансировку нагрузки DNS на внутреннем интерфейсе пула EDGE, необходимо добавить одну запись DNS, которая будет разрешать внутреннее полное доменное имя пула Edge с IP-адресом каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="17c88-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="17c88-114">Чтобы убедиться в том, что DNS возвращает правильные значения для балансировки нагрузки DNS, следует использовать средство nslookup.</span><span class="sxs-lookup"><span data-stu-id="17c88-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="17c88-115">Чтобы вернуть все значения для записи DNS с помощью nslookup, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="17c88-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="17c88-116">Эта команда запускается для всех полных доменных имен, используемых в конфигурации балансировки нагрузки DNS, чтобы убедиться, что каждый набор записей для балансировки нагрузки DNS вернул все необходимые записи.</span><span class="sxs-lookup"><span data-stu-id="17c88-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

