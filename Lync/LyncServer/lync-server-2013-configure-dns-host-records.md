---
title: 'Lync Server 2013: Настройка записей узла DNS'
description: 'Lync Server 2013: Настройка записей узла DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fd403402d0d2f089d7fc92a62296a56df0cf2e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553435"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="30f85-103">Настройка записей узла DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30f85-103">Configure DNS Host records for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30f85-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="30f85-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="30f85-105">Чтобы успешно выполнить процедуру, необходимо выполнить вход на сервер или в домен по крайней мере с правами члена группы "Администраторы домена" или DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="30f85-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="30f85-106">Настройка записей A узла DNS</span><span class="sxs-lookup"><span data-stu-id="30f85-106">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="30f85-107">На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.</span><span class="sxs-lookup"><span data-stu-id="30f85-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="30f85-108">В дереве консоли для своего домена разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30f85-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="30f85-109">Выберите команду **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="30f85-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="30f85-110">Щелкните поле **Имя** и введите имя узла пула (имя домена принимается соответствующим зоне, в которой определяется запись, и его не нужно вводить как часть записи A).</span><span class="sxs-lookup"><span data-stu-id="30f85-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="30f85-111">Щелкните **IP-адрес**, введите виртуальный IP-адрес подсистемы балансировки нагрузки для пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="30f85-111">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="30f85-112">В развертываниях, в которых используется пул Директоров, записи узлов (A) для простых URL-адресов должны указывать на виртуальный IP-адрес балансировщика нагрузки Директоров.</span><span class="sxs-lookup"><span data-stu-id="30f85-112">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30f85-p101">Если вы развертываете только один сервер Enterprise Edition или Директор, который подключен к топологии без балансировщика нагрузки, или если вы развертываете сервер Standard Edition, введите IP-адрес сервера Enterprise Edition, Standard Edition или Директора. Балансировщик нагрузки требуется, если вы развертываете несколько серверов Enterprise Edition или Директоров в пуле. С серверами Standard Edition балансировщики нагрузки не используются.</span><span class="sxs-lookup"><span data-stu-id="30f85-p101">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director. A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool. Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="30f85-116">Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="30f85-116">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="30f85-117">Чтобы создать еще одну запись A, повторите действия 4 и 5.</span><span class="sxs-lookup"><span data-stu-id="30f85-117">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="30f85-118">Создав все нужные записи A, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="30f85-118">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

