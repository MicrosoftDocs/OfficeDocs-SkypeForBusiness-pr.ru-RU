---
title: Обновление записей DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9df74033156e03cf7047b4d4bfbb2dbc83595b9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="89838-102">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="89838-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89838-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="89838-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="89838-104">Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="89838-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="89838-105">В этом разделе описывается, как обновить записи службы доменных имен (DNS) после перехода на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89838-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="89838-106">После того как все пользователи будут перемещены в Lync Server 2013, но до ликвидации устаревшего пула или директора Office Communications Server 2007 R2 необходимо обновить записи DNS SRV во внутренней DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="89838-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="89838-107">В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.</span><span class="sxs-lookup"><span data-stu-id="89838-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="89838-108">**Настройка DNS-записи SRV**</span><span class="sxs-lookup"><span data-stu-id="89838-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="89838-109">На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="89838-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="89838-110">В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**, разверните домен SIP, в котором установлен Lync Server 2013, и перейдите к параметру \*\* \_TCP\*\* .</span><span class="sxs-lookup"><span data-stu-id="89838-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="89838-111">В правой области щелкните \*\* \_\*\* правой кнопкой мыши сипинтерналтлс и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="89838-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="89838-112">В **узле, предоставляющем эту службу**, обновите полное доменное имя узла, указав пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89838-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="89838-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="89838-113">Click **OK**.</span></span>

<span data-ttu-id="89838-114">**Проверка возможности разрешения полного доменного имени интерфейсного пула или сервера Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="89838-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="89838-115">Войдите на клиентский компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="89838-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="89838-116">Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="89838-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="89838-117">В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="89838-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="89838-118">В командной строки введите **nslookup** \<FQDN переднего плана\> или \<полное доменное имя сервера\>Standard Edition, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="89838-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="89838-119">Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="89838-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

