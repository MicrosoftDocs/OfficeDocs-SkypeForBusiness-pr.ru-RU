---
title: 'Lync Server 2013: настройка записей узлов DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="250a4-102">Настройка записей узлов DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="250a4-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="250a4-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="250a4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="250a4-104">Для успешного выполнения этой процедуры необходимо войти на сервер или домен, как минимум, с учетной записью члена группы администраторов домена или пользователя, который является членом группы Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="250a4-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="250a4-105">Настройка записей узла DNS</span><span class="sxs-lookup"><span data-stu-id="250a4-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="250a4-106">На сервере доменных имен (DNS) нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="250a4-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="250a4-107">В дереве консоли для вашего домена разверните раздел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="250a4-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="250a4-108">Выберите команду **создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="250a4-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="250a4-109">Щелкните **Name (имя**), введите имя узла для пула (доменное имя будет указано в той зоне, в которой она определена, и ее не нужно вводить как часть записи A).</span><span class="sxs-lookup"><span data-stu-id="250a4-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="250a4-110">Щелкните **IP-адрес**, введите виртуальный IP-протокол для подсистемы балансировки нагрузки для пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="250a4-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="250a4-111">В развертываниях, использующих пул каталогов, записи узла (A) для простых URL-адресов должны указывать на VIP подсистемы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="250a4-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="250a4-112">Если вы развертываете только один сервер выпуска Enterprise Edition или режиссер, подключенный к топологии без подсистемы балансировки нагрузки, а также при развертывании сервера Standard Edition, введите IP-адрес сервера Enterprise Edition, сервера Standard Edition или Director.</span><span class="sxs-lookup"><span data-stu-id="250a4-112">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director.</span></span> <span data-ttu-id="250a4-113">Подсистема балансировки нагрузки требуется при развертывании более одного сервера выпуска Enterprise Edition или режиссера в пуле.</span><span class="sxs-lookup"><span data-stu-id="250a4-113">A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool.</span></span> <span data-ttu-id="250a4-114">Подсистема балансировки нагрузки не используется для серверов Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="250a4-114">Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="250a4-115">Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="250a4-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="250a4-116">Чтобы создать дополнительную запись, повторите шаги 4 и 5.</span><span class="sxs-lookup"><span data-stu-id="250a4-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="250a4-117">Завершив создание всех необходимых записей, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="250a4-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

