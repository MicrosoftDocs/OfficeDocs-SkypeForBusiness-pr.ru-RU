---
title: 'Lync Server 2013: рекомендации по развертыванию для корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0f4f6198f8fb82720834d112bcf363554aaf84d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="4dae6-102">Рекомендации по развертыванию для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dae6-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dae6-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4dae6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4dae6-104">В этой статье описаны предварительные требования и другие рекомендации, которые следует принимать во время планирования развертывания Lync Server 2013 и корпоративной рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="4dae6-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="4dae6-105">Необходимые условия для развертывания</span><span class="sxs-lookup"><span data-stu-id="4dae6-105">Deployment Prerequisites</span></span>

<span data-ttu-id="4dae6-106">Для оптимальной работы при развертывании корпоративной голосовой связи убедитесь, что ваша ИТ инфраструктура, сеть и системы соответствуют следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="4dae6-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="4dae6-107">Lync Server 2013 Standard Edition или Enterprise Edition установлен и работает в сети.</span><span class="sxs-lookup"><span data-stu-id="4dae6-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="4dae6-108">Все пограничные серверы развертываются и работают в демилитаризованной зоне, в том числе на пограничные серверы со службой EDGE, служба EDGE, служба Edge для веб-конференций и обратный прокси.</span><span class="sxs-lookup"><span data-stu-id="4dae6-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="4dae6-109">У вас есть один или несколько пользователей, которые были созданы и включены для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4dae6-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="4dae6-110">Установлен Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) или последний пакет обновления либо Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4dae6-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="4dae6-111">Один из них требуется для интеграции единой системы обмена сообщениями Exchange с сервером Lync Server и предоставления подробных уведомлений и сведений журнала звонков конечным точкам клиента.</span><span class="sxs-lookup"><span data-stu-id="4dae6-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="4dae6-112">Уникальный основной телефонный номер был обозначен, нормализован и скопирован в атрибут **msRTCSIP Line** для каждого пользователя, который должен быть активирован для использования в корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4dae6-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4dae6-113">Lync Server поддерживает номера E. 164 и непрямые звонки (за один номер).</span><span class="sxs-lookup"><span data-stu-id="4dae6-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="4dae6-114">Невыполненные номера могут быть представлены в формате <STRONG> &lt;E. 164&gt;; рсш =&lt;Extension&gt; </STRONG> или в виде строки цифр с требованием, что личное расширение уникально для всего предприятия.</span><span class="sxs-lookup"><span data-stu-id="4dae6-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="4dae6-115">Например, частное число 1001 может быть представлено в виде <STRONG>+ 1425550100; ext = 1001</STRONG>или как <STRONG>1001</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4dae6-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="4dae6-116">Как и в <STRONG>1001</STRONG>, предполагается, что этот частный номер уникален для всего предприятия.</span><span class="sxs-lookup"><span data-stu-id="4dae6-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="4dae6-117">Администраторы, которые разворачивают корпоративную голосовую почту, должны быть членами группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="4dae6-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="4dae6-118">Office Communicator 2007 успешно развернут по крайней мере.</span><span class="sxs-lookup"><span data-stu-id="4dae6-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="4dae6-119">Для использования новых возможностей этого выпуска будет развернуто Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4dae6-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="4dae6-120">Инфраструктура управляемого ключа (МКИ) разворачивается и конфигурируется с помощью инфраструктуры Microsoft или стороннего центра сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="4dae6-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="4dae6-121">На каждом компьютере, на котором установлен сервер исправлений, должно быть:</span><span class="sxs-lookup"><span data-stu-id="4dae6-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="4dae6-122">Рядовой сервер домена и подготовка для доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4dae6-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="4dae6-123">Инструкции для подготовки доменных служб Active Directory содержатся в разделе [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4dae6-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4dae6-124">Выполнение одной из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="4dae6-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="4dae6-125">64-разрядная версия операционной системы Windows Server 2008 Standard.</span><span class="sxs-lookup"><span data-stu-id="4dae6-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="4dae6-126">64-разрядная версия операционной системы Windows Server 2008 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4dae6-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="4dae6-127">Если подключение к общественной коммутируемой телефонной сети (КТСОП) или УАТС (Private Branch Exchange) осуществляется с помощью подключения по времени (ТДМ), для развертывания доступны один или несколько шлюзов PSTN.</span><span class="sxs-lookup"><span data-stu-id="4dae6-127">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment.</span></span> <span data-ttu-id="4dae6-128">(Если соединение осуществляется с помощью магистральной магистрали SIP, шлюз PSTN не требуется.)</span><span class="sxs-lookup"><span data-stu-id="4dae6-128">(If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="4dae6-129">Перебои в сети, сетевые или телефонные услуги</span><span class="sxs-lookup"><span data-stu-id="4dae6-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="4dae6-130">Если у вас возникла ошибка, неисправность или другое падение электроэнергии, сети или телефонной службы в вашем расположении, голосовая почта, Обмен мгновенными сообщениями, присутствие и другие функции Lync Server и любые устройства, подключенные к Lync Server, могут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="4dae6-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="4dae6-131">Корпоративная голосовая связь зависит от доступности сервера, клиента голосовой связи и совместимости оборудования.</span><span class="sxs-lookup"><span data-stu-id="4dae6-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="4dae6-132">Голосовая связь с Lync Server зависит от доступности серверного программного обеспечения и надлежащей работы голосовых клиентов или аппаратных устройств, подключающихся к серверному программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="4dae6-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="4dae6-133">Альтернативные способы доступа к службам экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="4dae6-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="4dae6-134">Для тех случаев, когда вы устанавливаете голосовой клиент (например, ПК, на котором работает клиент Lync или устройство Lync Phone Edition), рекомендуем использовать функцию резервного копирования для пользователей, которые будут вызывать экстренные службы (например, 911 или 999) в случае сбоя электросети. , снижение сетевого подключения, отключение службы телефонной связи или другая неполадка, которая может препятствовать работе с устройствами Lync Server, Lync или Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="4dae6-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="4dae6-135">К таким альтернативным параметрам относятся Телефон, подключенный к стандартной линии телефонной сети с открытым коммутируемым подключением или сотовому телефону.</span><span class="sxs-lookup"><span data-stu-id="4dae6-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="4dae6-136">Экстренные вызовы и многострочные телефонные системы</span><span class="sxs-lookup"><span data-stu-id="4dae6-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="4dae6-137">Использование многострочной телефонной системы (МЛТС) может быть в состоянии U. S или федеральных законов или законов других стран и регионов, в которых требуется, чтобы МЛТС предоставил номер телефона, расширение и (или) физическое расположение вызывающего абонента при наличии вызывающий абонент помещается в экстренные службы (например, при наборе номера для экстренного доступа, например 911 или 999).</span><span class="sxs-lookup"><span data-stu-id="4dae6-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="4dae6-138">В этом выпуске Lync Server можно настроить таким образом, чтобы он предоставил службе экстренного обслуживания физическое расположение вызывающего абонента, как описано в разделе [Планирование служб экстренной помощи (E9-1-1) в Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="4dae6-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="4dae6-139">Соответствие требованиям, предъявляемым законами МЛТС законов, является единственной обязанностью покупателя Lync Server, клиента Lync и устройств Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="4dae6-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

