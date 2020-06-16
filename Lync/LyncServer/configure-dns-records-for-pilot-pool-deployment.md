---
title: Настройка DNS-записей для развертывания пилотного пула
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
ms.openlocfilehash: 26f8c04773c31e60e5faa8fd9df2b1e08331f5c7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="f8fe1-102">Настройка DNS-записей для развертывания пилотного пула</span><span class="sxs-lookup"><span data-stu-id="f8fe1-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8fe1-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="f8fe1-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="f8fe1-104">Перед развертыванием пилотного пула Lync Server 2013 необходимо обновить записи узла DNS для пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="f8fe1-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="f8fe1-105">Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="f8fe1-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="f8fe1-106">**Настройка записей A узла DNS**</span><span class="sxs-lookup"><span data-stu-id="f8fe1-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="f8fe1-107">На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f8fe1-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f8fe1-108">В дереве консоли для своего домена разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8fe1-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="f8fe1-109">Выберите команду **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="f8fe1-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="f8fe1-110">Нажмите кнопку **имя**, введите имя узла для пула Lync Server 2013 (имя домена предполагается в зоне, в которой определена запись, и его не нужно вводить как часть записи A).</span><span class="sxs-lookup"><span data-stu-id="f8fe1-110">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="f8fe1-111">Щелкните **IP-адрес**, введите IP-адрес пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f8fe1-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="f8fe1-112">Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f8fe1-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="f8fe1-113">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f8fe1-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

