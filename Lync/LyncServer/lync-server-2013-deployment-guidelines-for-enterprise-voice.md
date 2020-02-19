---
title: 'Lync Server 2013: рекомендации по развертыванию для корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc2aee745a362e58003c62f483dda6c63ab244f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="201b4-102">Рекомендации по развертыванию корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="201b4-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="201b4-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="201b4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="201b4-104">В этом разделе описываются предварительные требования и другие рекомендации, которые необходимо учитывать при планировании развертывания Lync Server 2013 и рабочей нагрузки на корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="201b4-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="201b4-105">Предварительные требования для развертывания</span><span class="sxs-lookup"><span data-stu-id="201b4-105">Deployment Prerequisites</span></span>

<span data-ttu-id="201b4-106">Для оптимального использования при развертывании корпоративной голосовой связи убедитесь, что ваша ИТ инфраструктура, сеть и системы удовлетворяют следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="201b4-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="201b4-107">Lync Server 2013 Standard Edition или Enterprise Edition установлен и работает в вашей сети.</span><span class="sxs-lookup"><span data-stu-id="201b4-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="201b4-108">Все пограничные серверы разворачиваются и работают в сети периметра, включая пограничные серверы с пограничной службой доступа, пограничной службой аудио-и видеоконференций, пограничной службой веб-конференций и обратным прокси-сервером.</span><span class="sxs-lookup"><span data-stu-id="201b4-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="201b4-109">Один или несколько пользователей были созданы и включены для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="201b4-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="201b4-110">Установлен Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) или более поздний пакет обновления или Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="201b4-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="201b4-111">Один из них необходим для интеграции единой системы обмена сообщениями Exchange с Lync Server, а также для предоставления расширенных уведомлений и сведений журнала вызовов конечным точкам клиента.</span><span class="sxs-lookup"><span data-stu-id="201b4-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="201b4-112">Уникальный основной номер телефона был назначен, нормализован и скопирован в атрибут **msRTCSIP-Line** для каждого пользователя, который должен быть включен для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="201b4-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="201b4-113">Lync Server поддерживает номера E. 164 и непрямые входные номера.</span><span class="sxs-lookup"><span data-stu-id="201b4-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="201b4-114">Невыполненные номера могут быть представлены в формате <STRONG> &lt;E. 164&gt;; ext =&lt;Extension&gt; </STRONG> или в виде строки цифр с требованием о том, что личное расширение уникально в пределах предприятия.</span><span class="sxs-lookup"><span data-stu-id="201b4-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="201b4-115">Например, личный номер 1001 может быть представлен в виде <STRONG>+1425550100;ext=1001</STRONG> или в виде <STRONG>1001</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="201b4-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="201b4-116">В случае, когда номер представлен как <STRONG>1001</STRONG>, предполагается, что этот номер уникален в рамках всего предприятия.</span><span class="sxs-lookup"><span data-stu-id="201b4-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="201b4-117">Администраторы, развертывающие корпоративную голосовую связь, должны быть членами группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="201b4-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="201b4-118">По крайней мере Office Communicator 2007 успешно развернут.</span><span class="sxs-lookup"><span data-stu-id="201b4-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="201b4-119">Чтобы использовать новые возможности этого выпуска, будет развернут Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="201b4-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="201b4-120">Управляемая ключевая инфраструктура (MKI) развернута и настроена с помощью инфраструктуры Майкрософт или стороннего центра сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="201b4-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="201b4-121">Каждый компьютер, на котором устанавливается сервер-посредник, должен соответствовать следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="201b4-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="201b4-122">Рядовой сервер домена и подготовленные для доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="201b4-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="201b4-123">Инструкции по подготовке доменных служб Active Directory приведены в статье [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="201b4-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="201b4-124">Он должен работать под управлением одной из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="201b4-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="201b4-125">64-разрядной версии операционной системы Windows Server 2008 Standard;</span><span class="sxs-lookup"><span data-stu-id="201b4-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="201b4-126">64-разрядной версии операционной системы Windows Server 2008 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="201b4-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="201b4-p105">Если подключение к ТСОП или УАТС выполняется посредством подключения с временным мультиплексированием (TDM), то для развертывания доступен хотя бы один шлюз ТСОП. (если подключение выполняется посредством канала SIP, то шлюз ТСОП не требуется.)</span><span class="sxs-lookup"><span data-stu-id="201b4-p105">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment. (If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="201b4-129">Отключение электричества, сети или телефонной службы</span><span class="sxs-lookup"><span data-stu-id="201b4-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="201b4-130">В случае сбоя, нарушения или другого ухудшения электроэнергии, сети или телефонных служб в вашем расположении, голосовая связь, Обмен мгновенными сообщениями, сведения о присутствии и другие функции Lync Server и любое устройство, подключенное к Lync Server, могут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="201b4-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="201b4-131">Зависимость корпоративной голосовой связи от доступности сервера и работоспособности клиента голосовой связи или оборудования</span><span class="sxs-lookup"><span data-stu-id="201b4-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="201b4-132">Голосовая связь с Lync Server зависит от доступности серверного программного обеспечения и надлежащего функционирования голосовых клиентов или устройств, подключающихся к серверному программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="201b4-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="201b4-133">Дублирующие средства доступа к экстренным службам</span><span class="sxs-lookup"><span data-stu-id="201b4-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="201b4-134">Для тех расположений, в которых устанавливается голосовой клиент (например, ПК, на котором работает клиент Lync или устройство Lync Phone Edition), рекомендуется поддерживать функцию резервного копирования, чтобы пользователи вызывали экстренные службы (например, 911 или 999) в случае сбоя электросети. , снижение сетевого подключения, отключение телефонной службы или другие проблемы, которые могут препятствовать работе устройств Lync Server, Lync или Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="201b4-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="201b4-135">В качестве такого дублирующего варианта может использоваться телефонное подключение к обычной телефонной сети общего пользования или мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="201b4-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="201b4-136">Экстренные вызовы и многоканальные телефонные системы</span><span class="sxs-lookup"><span data-stu-id="201b4-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="201b4-137">Использование многострочной телефонной системы (МЛТС) может быть в состоянии U. S или федеральных законах или законах других стран и регионов, которые требуют от МЛТС предоставления доступа к телефонному номеру, добавочному номеру и/или физическому расположению для соответствующих экстренных служб при размещении абонента в аварийных 999 911 службах</span><span class="sxs-lookup"><span data-stu-id="201b4-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="201b4-138">В этом выпуске Lync Server можно настроить таким образом, чтобы обеспечить физическое расположение вызывающего абонента для поставщика экстренных служб, как описано в статье [планирование экстренных служб (E9-1-1) в Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="201b4-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="201b4-139">Соответствие законам МЛТС является единственной обязанностью покупателя Lync Server, Lync Client и Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="201b4-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

