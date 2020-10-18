---
title: Обновление записей DNS SRV
description: Обновление записей DNS SRV.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24161074e8f3bcf7e296a957588eeb59d5f2ad1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579595"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="5b047-103">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="5b047-103">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b047-104">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="5b047-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="5b047-105">Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="5b047-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="5b047-106">В этом разделе описывается, как обновить записи службы доменных имен (DNS) после перехода на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b047-106">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="5b047-107">После того как все пользователи будут перемещены в Lync Server 2013, но до того, как старый пул или директор Lync Server 2010 не будут списаны, необходимо обновить записи DNS SRV во внутренней DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="5b047-107">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="5b047-108">В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.</span><span class="sxs-lookup"><span data-stu-id="5b047-108">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="5b047-109">**Настройка DNS-записи SRV**</span><span class="sxs-lookup"><span data-stu-id="5b047-109">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="5b047-110">На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5b047-110">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="5b047-111">В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**, РАЗВЕРНИТЕ домен SIP, в котором установлен Lync Server 2013, и перейдите к параметру \*\* \_ TCP\*\* .</span><span class="sxs-lookup"><span data-stu-id="5b047-111">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="5b047-112">В правой области щелкните правой кнопкой мыши \*\* \_ сипинтерналтлс\*\* и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5b047-112">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="5b047-113">В **узле, предоставляющем эту службу**, обновите полное доменное имя узла, указав пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b047-113">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="5b047-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5b047-114">Click **OK**.</span></span>

<span data-ttu-id="5b047-115">**Проверка возможности разрешения полного доменного имени интерфейсного пула или сервера Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="5b047-115">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="5b047-116">Войдите на клиентский компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="5b047-116">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="5b047-117">Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5b047-117">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="5b047-118">В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5b047-118">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5b047-119">В командной строки введите **nslookup** \<FQDN of the Front End pool\> или и нажмите \<FQDN of the Standard Edition server\> клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="5b047-119">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="5b047-120">Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="5b047-120">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

