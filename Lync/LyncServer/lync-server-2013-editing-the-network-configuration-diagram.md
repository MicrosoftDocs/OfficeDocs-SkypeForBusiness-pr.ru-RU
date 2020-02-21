---
title: 'Lync Server 2013: редактирование схемы конфигурации сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225702f30aa19bf53c8b3f65c9731ea29b16a686
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="84f04-102">Изменение схемы конфигурации сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84f04-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84f04-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="84f04-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="84f04-104">Большая часть работы, которую выполняет конструктор в Lync Server 2013, средство планирования состоит из определения записей для IP-адресов и полных доменных имен (FQDN) для записей в сетевом графике.</span><span class="sxs-lookup"><span data-stu-id="84f04-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="84f04-105">Сведения, введенные на этой странице, переносятся в отчеты и другие сведения, содержащиеся в средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="84f04-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="84f04-106">![Сетевая схема средства планирования](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Сетевая схема средства планирования")</span><span class="sxs-lookup"><span data-stu-id="84f04-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="84f04-107">Средство планирования создает сетевую схему с текстом по умолчанию для IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="84f04-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="84f04-108">Чтобы изменить сетевую диаграмму и входные значения:</span><span class="sxs-lookup"><span data-stu-id="84f04-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="84f04-109">Выберите раздел сети, над которым необходимо начать работу.</span><span class="sxs-lookup"><span data-stu-id="84f04-109">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="84f04-110">Например, дважды щелкните текст **access1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="84f04-110">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="84f04-111">В открывшемся диалоговом окне введите реальное полное доменное имя сервера access1.contoso.com и фактический IP-адрес, заменив 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="84f04-111">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="84f04-112">Нажмите кнопку **ОК** , чтобы сохранить записи.</span><span class="sxs-lookup"><span data-stu-id="84f04-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="84f04-113">Продолжайте изменять IP-адреса и полные доменные имена, предоставляя виртуальные IP-адреса для аппаратных подсистем балансировки нагрузки или записи сервера для балансировки нагрузки службы доменных имен (DNS) для серверов в пулах.</span><span class="sxs-lookup"><span data-stu-id="84f04-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="84f04-114">Полезная функция средства планирования состоит в том, что она может потребовать последовательного назначения диапазона IP-адресов и имен узлов серверов, а не требуя, чтобы дизайнер мог редактировать каждый отдельный сервер в пуле.</span><span class="sxs-lookup"><span data-stu-id="84f04-114">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool.</span></span> <span data-ttu-id="84f04-115">Например:</span><span class="sxs-lookup"><span data-stu-id="84f04-115">For example:</span></span>

1.  <span data-ttu-id="84f04-116">Дважды щелкните Пулы серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="84f04-116">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="84f04-117">Когда откроется диалоговое окно, выберите **использовать IP-адреса и полное доменное имя в качестве начальных точек для всех эквивалентных серверов в этом кластере?**.</span><span class="sxs-lookup"><span data-stu-id="84f04-117">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="84f04-118">Например, начальным значением для первого сервера является fe0101.contoso.com и IP-адресом 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="84f04-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="84f04-119">Введите **fe0.contoso.com** в **качестве полного доменного имени сервера переднего плана**, введите **192.168.21.131** в качестве **IP-адреса сервера переднего плана**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84f04-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="84f04-120">Функция автоприращения обновляет все серверы в пуле на fe01 через fe06 и все IP-адреса от 192.168.21.131 до 136.</span><span class="sxs-lookup"><span data-stu-id="84f04-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="84f04-121">После завершения всех изменений сохраните топологию, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="84f04-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="84f04-122">Чтобы сохранить проект средства планирования, нажмите кнопку **файл**и выберите команду **Сохранить топологию** или **Сохранить топологию как**.</span><span class="sxs-lookup"><span data-stu-id="84f04-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="84f04-123">Если появится диалоговое окно **сохранить средство планирования как** , введите имя файла в поле **имя файла**и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="84f04-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="84f04-124">См. также</span><span class="sxs-lookup"><span data-stu-id="84f04-124">See Also</span></span>


[<span data-ttu-id="84f04-125">Редактирование макета в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84f04-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

