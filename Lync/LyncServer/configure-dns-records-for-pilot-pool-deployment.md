---
title: Настройка DNS-записей для развертывания пилотного пула
description: Настройка DNS-записей для развертывания пилотного пула.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e41e163432ba910f6d083cc508e8ad8c9f2006d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548495"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="fe99f-103">Настройка DNS-записей для развертывания пилотного пула</span><span class="sxs-lookup"><span data-stu-id="fe99f-103">Configure DNS records for pilot pool deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe99f-104">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="fe99f-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="fe99f-105">Перед развертыванием пилотного пула Lync Server 2013 необходимо обновить записи узла DNS для пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="fe99f-105">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="fe99f-106">Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="fe99f-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="fe99f-107">**Настройка записей A узла DNS**</span><span class="sxs-lookup"><span data-stu-id="fe99f-107">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="fe99f-108">На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.</span><span class="sxs-lookup"><span data-stu-id="fe99f-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="fe99f-109">В дереве консоли для своего домена разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe99f-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="fe99f-110">Выберите команду **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="fe99f-110">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="fe99f-111">Нажмите кнопку **имя**, введите имя узла для пула Lync Server 2013 (имя домена предполагается в зоне, в которой определена запись, и его не нужно вводить как часть записи A).</span><span class="sxs-lookup"><span data-stu-id="fe99f-111">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="fe99f-112">Щелкните **IP-адрес**, введите IP-адрес пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="fe99f-112">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="fe99f-113">Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe99f-113">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="fe99f-114">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fe99f-114">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

