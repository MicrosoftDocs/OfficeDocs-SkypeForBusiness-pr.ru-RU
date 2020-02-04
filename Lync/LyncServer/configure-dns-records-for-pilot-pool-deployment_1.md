---
title: Настройка DNS-записей для развертывания пилотного пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612857ba1a0ec599b0011ab5779cb7fc4b5a0615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="71a6f-102">Настройка DNS-записей для развертывания пилотного пула</span><span class="sxs-lookup"><span data-stu-id="71a6f-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71a6f-103">_**Тема последнего изменения:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="71a6f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="71a6f-104">Перед развертыванием пула проектов Lync Server 2013 Pilot необходимо обновить записи узла DNS для пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="71a6f-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="71a6f-105">Для успешного выполнения этой процедуры необходимо войти на сервер или домен, как минимум, с учетной записью члена группы администраторов домена или пользователя, который является членом группы Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="71a6f-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="71a6f-106">**Настройка записей узла DNS**</span><span class="sxs-lookup"><span data-stu-id="71a6f-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="71a6f-107">На сервере доменных имен (DNS) нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="71a6f-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="71a6f-108">В дереве консоли для вашего домена разверните раздел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71a6f-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="71a6f-109">Выберите команду **создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="71a6f-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="71a6f-110">Щелкните **Name (имя**), введите имя узла для пула (доменное имя будет указано в той зоне, в которой она определена, и ее не нужно вводить как часть записи A).</span><span class="sxs-lookup"><span data-stu-id="71a6f-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="71a6f-111">Щелкните **IP-адрес**, введите IP-адрес пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="71a6f-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="71a6f-112">Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71a6f-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="71a6f-113">Когда все будет готово, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="71a6f-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

