---
title: 'Lync Server 2013: изменение структуры'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 601c313231a26341c3c4cf8a4897d11872dec9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="afdb1-102">Изменение структуры в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afdb1-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afdb1-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="afdb1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="afdb1-p101">После ответа на вопросы начального опроса вы можете изменить полное доменное имя и IP-адреса сайта. Для этого на странице **Global Topology** (Глобальная топология) дважды щелкните сайт, который хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="afdb1-p101">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="afdb1-106">Средство планирования отобразит топологию сайта для выбранного сайта.</span><span class="sxs-lookup"><span data-stu-id="afdb1-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="afdb1-107">At the bottom of the site page are four tabs:</span><span class="sxs-lookup"><span data-stu-id="afdb1-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="afdb1-108">![Топология сайта средства планирования] (images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Топология сайта средства планирования")</span><span class="sxs-lookup"><span data-stu-id="afdb1-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="afdb1-109">Топология сайта – отображаемая в данный момент страница с визуальным обзором топологии рекомендуемой.</span><span class="sxs-lookup"><span data-stu-id="afdb1-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="afdb1-110">Граничный сетевой график — на странице «Граничный сетевой график» конструктор делает большую часть работы в инструменте "планирование".</span><span class="sxs-lookup"><span data-stu-id="afdb1-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="afdb1-111">Схема отображает конфигурацию сети для рекомендованной топологии сервера Lync Server 2013 с редактируемыми записями для IP-адресов и полных доменных имен серверов, пула, а также аппаратных подсистем и подсистемы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="afdb1-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="afdb1-112">Отчет по пограничным серверам для администратора – всего эта страница содержит четыре отчета:</span><span class="sxs-lookup"><span data-stu-id="afdb1-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="afdb1-113">![Страница отчета "Администратор Edge"] (images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Страница отчета \"Администратор Edge\"")</span><span class="sxs-lookup"><span data-stu-id="afdb1-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="afdb1-p104">Сводный отчет – это общий отчет по параметрам для конфигурации сети периметра. Если вы измените значения на странице **Схема сети периметра** на значения TCP/IP и полного доменного имени топологии, которые будут использоваться в фактическом развертывании, эти адреса и имена будут представлены здесь. В противном случае отображается стандартный текст.</span><span class="sxs-lookup"><span data-stu-id="afdb1-p104">Summary Report – A general report of settings for the Edge network configuration. If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here. Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="afdb1-117">Отчет по сертификатам – этот отчет будет содержать имя субъекта и альтернативные имена субъекта для сертификатов, необходимых в данной топологии.</span><span class="sxs-lookup"><span data-stu-id="afdb1-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="afdb1-p105">Отчет по брандмауэру – этот отчет содержит информацию, необходимую для настройки брандмауэров по периметру сети в инфраструктуре. Сюда относятся IP-адреса (со значениями по умолчанию или измененными значениями), роль сервера, исходный IP-адрес и порт, конечный IP-адрес и порт, транспортный протокол, протокол приложений и соответствующие заметки.</span><span class="sxs-lookup"><span data-stu-id="afdb1-p105">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure. This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="afdb1-p106">Отчет DNS – этот отчет содержит существенную информацию по DNS-записям, которые вам требуется создать. В эту информацию входит тип записи, полное доменное имя, IP-адрес, а также комментарии, касающиеся обеспечения правильной работы.</span><span class="sxs-lookup"><span data-stu-id="afdb1-p106">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create. The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="afdb1-p107">Сводка сайта – сводка сайта содержит обзор тех вариантов, которые вы выбрали при ответе на вопросы начального опроса или при заполнении значений в области **Разработка сайтов**. Кроме того, приводится информация о мощности.</span><span class="sxs-lookup"><span data-stu-id="afdb1-p107">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**. Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afdb1-124">Информация на странице "Site Summary" (Сводка сайта) настраивается для каждой конкретной структуры и может не содержать всех тех разделов или сведений, которые перечислены здесь.</span><span class="sxs-lookup"><span data-stu-id="afdb1-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="afdb1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="afdb1-125">See Also</span></span>


[<span data-ttu-id="afdb1-126">Изменение схемы конфигурации сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afdb1-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

