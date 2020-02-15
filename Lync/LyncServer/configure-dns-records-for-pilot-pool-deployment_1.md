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
ms.openlocfilehash: fd9ae4eff928413838fc014a125b681aa15f0def
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41999004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="5f47b-102">Настройка DNS-записей для развертывания пилотного пула</span><span class="sxs-lookup"><span data-stu-id="5f47b-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f47b-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="5f47b-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="5f47b-104">Перед развертыванием пилотного пула Lync Server 2013 необходимо обновить записи узла DNS для пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="5f47b-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="5f47b-105">Чтобы успешно выполнить процедуру, необходимо выполнить вход на сервер или в домен по крайней мере с правами члена группы "Администраторы домена" или DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="5f47b-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="5f47b-106">**Настройка записей A узла DNS**</span><span class="sxs-lookup"><span data-stu-id="5f47b-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="5f47b-107">На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5f47b-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="5f47b-108">В дереве консоли для своего домена разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f47b-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="5f47b-109">Выберите команду **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="5f47b-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="5f47b-110">Щелкните поле **Имя** и введите имя узла пула (имя домена принимается соответствующим зоне, в которой определяется запись, и его не нужно вводить как часть записи A).</span><span class="sxs-lookup"><span data-stu-id="5f47b-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="5f47b-111">Щелкните **IP-адрес**, введите IP-адрес пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5f47b-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="5f47b-112">Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f47b-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="5f47b-113">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5f47b-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

