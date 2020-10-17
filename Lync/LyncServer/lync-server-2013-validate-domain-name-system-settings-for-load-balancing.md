---
title: 'Lync Server 2013: Проверка параметров системы доменных имен для балансировки нагрузки'
description: 'Lync Server 2013: Проверка параметров системы доменных имен для балансировки нагрузки.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a218a79a541e9c9705a8403146fe7e134e8ed827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547235"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="0f026-103">Проверка параметров системы доменных имен для балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f026-103">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f026-104">_**Последнее изменение темы:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="0f026-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="0f026-p101">Для поддержки полного доменного имени, используемого балансировкой нагрузки на DNS, необходимо подготовить DNS, чтобы полное доменное имя пула (такое как pool01.contoso.com) сводилось к IP-адресам всех серверов в пуле (например, 192.168.1.1, 192.168.1.2 и т.д.). Следует включать IP-адреса только тех серверов которые развернуты в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="0f026-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="0f026-107">Кроме того, если вы используете балансировку нагрузки на DNS для пограничных пулов, необходимы следующие записи DNS:</span><span class="sxs-lookup"><span data-stu-id="0f026-107">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="0f026-108">Для службы пограничного сервера доступа Lync Server необходимо иметь одну запись для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="0f026-108">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="0f026-109">Каждая запись должна разрешать полное доменное имя пограничной службы доступа Lync Server (например, sip.contoso.com) к IP-адресу пограничной службы доступа Lync Server на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="0f026-109">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="0f026-110">Для пограничной службы веб-конференций Lync Server необходимо иметь одну запись для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="0f026-110">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="0f026-111">Каждая запись должна разрешать полное доменное имя пограничной службы веб-конференций Lync Server (например, webconf.contoso.com) в IP-адрес пограничной службы веб-конференций Lync Server на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="0f026-111">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="0f026-112">Для пограничной службы аудио-и видеоданных Lync Server необходимо наличие одной записи для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="0f026-112">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="0f026-113">Каждая запись должна разрешать полное доменное имя (например, av.contoso.com) сервера-пограничного сервера Lync Server (например,) в IP-адрес пограничной службы аудио-и видеосвязи Lync Server на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="0f026-113">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="0f026-114">Если вы хотите использовать балансировку нагрузки на DNS во внутреннем интерфейсе пограничного пула, необходимо добавить одну запись DNS, которая разрешает внутреннее полное доменное имя пограничного пула к IP-адресу каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="0f026-114">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="0f026-115">Чтобы убедиться, что DNS возвращает правильные значения для балансировки нагрузки DNS, следует использовать средство nslookup.</span><span class="sxs-lookup"><span data-stu-id="0f026-115">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="0f026-116">Чтобы получить все значения для записи DNS с помощью nslookup, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0f026-116">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="0f026-117">Эту команду необходимо выполнить для каждого полного доменного имени, используемого в конфигурации балансировки нагрузки DNS, чтобы убедиться, что все записи, настроенные для балансировки нагрузки DNS, возвращали все правильные записи.</span><span class="sxs-lookup"><span data-stu-id="0f026-117">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

