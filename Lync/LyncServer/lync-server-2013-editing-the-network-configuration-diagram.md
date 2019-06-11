---
title: 'Lync Server 2013: редактирование схемы конфигурации сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="dfa5b-102">Изменение схемы конфигурации сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfa5b-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfa5b-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="dfa5b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="dfa5b-104">Большая часть работы, которую делает разработчик в Lync Server 2013, средство планирования состоит из определения записей для IP-адресов и полных доменных имен (FQDN) для записей в сетевом графике.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="dfa5b-105">Данные, введенные на этой странице, переносятся в отчеты и другие сведения, содержащиеся в инструменте "планирование".</span><span class="sxs-lookup"><span data-stu-id="dfa5b-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="dfa5b-106">![Сетевая схема инструмента "Планирование] " (images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Сетевая схема инструмента \"Планирование") "</span><span class="sxs-lookup"><span data-stu-id="dfa5b-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="dfa5b-107">Средство планирования создает сетевую схему с текстом по умолчанию для IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="dfa5b-108">Изменение схемы сети и входных значений:</span><span class="sxs-lookup"><span data-stu-id="dfa5b-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="dfa5b-p102">Выберите раздел сети, работу над которым хотите начать. Например, дважды щелкните текст **access1.contoso.com**. В открывшемся диалоговом окне введите фактическое полное доменное имя сервера access1.contoso.com и фактически IP-адрес, заменив значение 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-p102">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="dfa5b-112">Нажмите кнопку **OK** (ОК), чтобы сохранить записи.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="dfa5b-113">Продолжайте изменять IP-адреса и полные доменные имена, указывая виртуальные IP-адреса для устройств балансировки нагрузки или записи сервера для подсистемы балансировки нагрузки службы доменных имен (DNS) для серверов в пулах.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="dfa5b-p103">Удобной особенность средства планирования является то, что оно может поэтапно назначать диапазон IP-адресов и имен узла сервера, не требуя от проектировщика изменения каждого отдельного сервера в пуле. Например:</span><span class="sxs-lookup"><span data-stu-id="dfa5b-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="dfa5b-p104">Дважды щелкните входящие в состав пула серверы переднего плана. После открытия диалогового окна выберите элемент **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?** (Использовать IP-адреса и полное доменное имя в качестве исходных точек для всех эквивалентных серверов в этом кластере?).</span><span class="sxs-lookup"><span data-stu-id="dfa5b-p104">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="dfa5b-118">Например, начальное значение для первого сервера: fe0101.contoso.com и IP-адрес 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="dfa5b-119">Введите значение **fe0.contoso.com** в поле **Front End Server FQDN** (Полное доменное имя сервера переднего плана), введите значение **192.168.21.131** в поле **Front End Server IP address** (IP-адрес сервера переднего плана), а затем нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="dfa5b-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="dfa5b-120">Компонент автоматического приращения обновляет все серверы в пуле с fe01 по fe06 и все IP-адреса с 192.168.21.131 по 136.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="dfa5b-121">После внесения всех правок сохраните топологию, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="dfa5b-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="dfa5b-122">Чтобы сохранить структуру средства планирования, нажмите кнопку **файл**, а затем выберите команду **Сохранить топологию** или **Сохранить топологию как**.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="dfa5b-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="dfa5b-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dfa5b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="dfa5b-124">See Also</span></span>


[<span data-ttu-id="dfa5b-125">Изменение структуры в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfa5b-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

