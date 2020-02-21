---
title: 'Lync Server 2013: Редактирование макета'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f6fa93dbb7ab1ad33b8972b8f09a025dec58c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="aaffb-102">Редактирование макета в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aaffb-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaffb-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="aaffb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="aaffb-104">После завершения начальных вопросов можно изменить полное доменное имя и IP-адреса сайта.</span><span class="sxs-lookup"><span data-stu-id="aaffb-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="aaffb-105">Для этого на странице **глобальная топология** дважды щелкните сайт, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="aaffb-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="aaffb-106">Средство планирования отображает топологию сайта для выбранного сайта.</span><span class="sxs-lookup"><span data-stu-id="aaffb-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="aaffb-107">В нижней части страницы сайта расположены четыре вкладки:</span><span class="sxs-lookup"><span data-stu-id="aaffb-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="aaffb-108">![Топология сайта средства планирования](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Топология сайта средства планирования")</span><span class="sxs-lookup"><span data-stu-id="aaffb-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="aaffb-109">Топология сайта — отображаемая в текущий момент страница с визуальным обзором топологии, как это рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="aaffb-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="aaffb-110">Схема пограничной сети — на странице схема пограничной сети размещается большая часть работы в средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="aaffb-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="aaffb-111">На схеме отображается конфигурация сети для рекомендуемой топологии Lync Server 2013 с изменяемыми записями IP-адресов и полных доменных имен для серверов, пулов, а также подсистем балансировки нагрузки на оборудование и систему доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="aaffb-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="aaffb-112">Отчет "администратор пограничного сервера" — отчет об административном пограничных отчетах содержит всего четыре отчета:</span><span class="sxs-lookup"><span data-stu-id="aaffb-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="aaffb-113">![Страница отчета "администратор пограничного сервера"](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Страница отчета "администратор пограничного сервера"")</span><span class="sxs-lookup"><span data-stu-id="aaffb-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="aaffb-114">Сводный отчет — общий отчет о параметрах конфигурации пограничной сети.</span><span class="sxs-lookup"><span data-stu-id="aaffb-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="aaffb-115">Если вы изменяете значения на странице " **схема пограничной сети** " на значение топология TCP/IP и полное доменное имя, которое будет использоваться в фактическом развертывании, эти адреса и имена будут представлены здесь.</span><span class="sxs-lookup"><span data-stu-id="aaffb-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="aaffb-116">В противном случае будет отображаться текст по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aaffb-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="aaffb-117">Отчет по сертификатам — в отчете о сертификате будут указаны имена субъектов и альтернативные имена субъектов для сертификатов, необходимых для топологии.</span><span class="sxs-lookup"><span data-stu-id="aaffb-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="aaffb-118">Отчет о брандмауэре — отчет о брандмауэре содержит сведения, необходимые для настройки брандмауэров периметра сети в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="aaffb-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="aaffb-119">Сюда входят IP-адреса (значения по умолчанию или измененные), роль сервера, исходный IP-адрес и порт, конечный IP-адрес и порт, протокол транспорта, протокол приложения и необходимые примечания.</span><span class="sxs-lookup"><span data-stu-id="aaffb-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="aaffb-120">Отчет DNS — в отчете DNS перечисляются релевантные сведения о записях DNS, которые необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="aaffb-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="aaffb-121">Включаются тип записи, полное доменное имя, IP-адрес и комментарии, необходимые для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="aaffb-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="aaffb-122">Сводка по сайту — сводка по сайту представляет собой обзор выбранных вариантов ответа на первоначальные вопросы об интервью или заполнения значений на **сайтах дизайна**.</span><span class="sxs-lookup"><span data-stu-id="aaffb-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="aaffb-123">Кроме того, представлены сведения о емкости.</span><span class="sxs-lookup"><span data-stu-id="aaffb-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aaffb-124">Сведения на странице Сводка по сайту настраиваются для каждой структуры и могут не содержать все разделы или сведения, подробные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="aaffb-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="aaffb-125">См. также</span><span class="sxs-lookup"><span data-stu-id="aaffb-125">See Also</span></span>


[<span data-ttu-id="aaffb-126">Изменение схемы конфигурации сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aaffb-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

