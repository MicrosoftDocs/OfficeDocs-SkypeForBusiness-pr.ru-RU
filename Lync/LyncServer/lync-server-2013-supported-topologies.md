---
title: Lync Server 2013 поддерживаемые топологии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a74be867305f3e42d1e9e303baedbddd22f485
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="695a3-102">Поддерживаемые топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="695a3-102">Supported topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="695a3-103">_**Последнее изменение темы:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="695a3-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="695a3-104">Lync Server 2013 поддерживает развертывание локальных сайтов в Организации и интеграцию локальных развертываний с развертываниями Lync Online, которые называют гибридным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="695a3-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="695a3-105">В таком развертывании некоторые пользователи размещаются локально, а некоторые — в Интернете.</span><span class="sxs-lookup"><span data-stu-id="695a3-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="695a3-106">Для локальных развертываний Lync Server 2013 поддерживает развертывание одного или нескольких сайтов, которые можно масштабировать в соответствии с требованиями к высокой доступности и расположениям.</span><span class="sxs-lookup"><span data-stu-id="695a3-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="695a3-107">Вы можете структурировать эти сайты и их компоненты для выполнения требований по доступу и устойчивости вашей организации.</span><span class="sxs-lookup"><span data-stu-id="695a3-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="695a3-108">Локальное развертывание Lync Server 2013 состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="695a3-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="695a3-p103">Развертывание должно содержать хотя бы один центральный узел (который также называют центром обработки данных). Каждый центральный узел должен содержать по меньшей мере один интерфейсный пул Enterprise Edition или сервер Standard Edition. Они состоят из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="695a3-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="695a3-112">интерфейсного пула Enterprise Edition, который содержит один или несколько интерфейсных серверов (обычно для обеспечения масштабирования) и отдельный фоновый сервер.</span><span class="sxs-lookup"><span data-stu-id="695a3-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="695a3-113">Интерфейсный пул может содержать до двенадцати двенадцати серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="695a3-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="695a3-114">Для нескольких интерфейсных серверов требуется балансировка нагрузки.</span><span class="sxs-lookup"><span data-stu-id="695a3-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="695a3-115">Для трафика SIP рекомендуется использовать балансировку нагрузки DNS, но аппаратная балансировка нагрузки также поддерживается.</span><span class="sxs-lookup"><span data-stu-id="695a3-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="695a3-116">Если вы используете балансировку нагрузки DNS для трафика SIP, вам все равно требуется аппаратная подсистема балансировки нагрузки для HTTP-трафика.</span><span class="sxs-lookup"><span data-stu-id="695a3-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="695a3-117">Мы рекомендуем зеркальное отображение SQL Server для обеспечения высокой доступности баз данных.</span><span class="sxs-lookup"><span data-stu-id="695a3-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="695a3-118">Для фоновой базы данных требуется отдельный экземпляр, но вы можете совместно разместить базу данных архивации, базу данных мониторинга, базу данных Persistent Chat и базу данных соответствия Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="695a3-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="695a3-119">Lync Server 2013 поддерживает использование общего кластера для общих файловых ресурсов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="695a3-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="695a3-120">Дополнительные сведения о требованиях к хранению баз данных можно найти [в разделе Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="695a3-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="695a3-121">Дополнительные сведения о требованиях к хранению файлов приведены [в статье поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="695a3-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="695a3-122">При совместном размещении баз данных Lync Server мы настоятельно рекомендуем оценить все факторы, которые могут повлиять на доступность и производительность.</span><span class="sxs-lookup"><span data-stu-id="695a3-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="695a3-123">Чтобы проверить возможности аварийного переключения, рекомендуется протестировать все сценарии аварийного переключения.</span><span class="sxs-lookup"><span data-stu-id="695a3-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="695a3-124">Сервер Standard Edition, которая включает в себя базу данных SQL Server Express с совместным размещением.</span><span class="sxs-lookup"><span data-stu-id="695a3-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="695a3-125">В вашем развертывании также может быть один или несколько узлов филиалов, связанных с центральным узлом.</span><span class="sxs-lookup"><span data-stu-id="695a3-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="695a3-126">В этом разделе описываются сайты и компоненты развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="695a3-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="695a3-127">Подробные сведения о планировании сайтов, топологий и компонентов Lync Server 2013 можно найти в статье [основы топологии, которые необходимо знать перед планированием для Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) и [эталонных топологий в Lync Server 2013](lync-server-2013-reference-topologies.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="695a3-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="695a3-128">Подробные сведения о интеграции компонентов предыдущих выпусков приведены [в статье поддерживаемые пути миграции и сценарии сосуществования в Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="695a3-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="695a3-129">Растянутые пулы не поддерживаются для ролей сервера переднего плана, пограничного сервера, сервера-посредника и директора.</span><span class="sxs-lookup"><span data-stu-id="695a3-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="695a3-130">Топология и компоненты центрального узла (локально)</span><span class="sxs-lookup"><span data-stu-id="695a3-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="695a3-131">Хотя топология центрального узла должна включать один интерфейсный пул и один сервер Standard Edition, при этом каждый центральный узел также может содержать следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="695a3-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="695a3-p107">Несколько интерфейсных пулов, которые могут быть размещены в одном или в разных доменах. Однако, все интерфейсные серверы в интерфейсном пуле, а также фоновый сервер для этого пула должны быть расположены в одном домене.</span><span class="sxs-lookup"><span data-stu-id="695a3-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="695a3-134">Несколько серверов Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="695a3-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="695a3-135">Сервер Office Web Apps, используемый с веб-приложениями Office в Lync Server 2013 для совместного использования и отрисовки презентаций Microsoft PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="695a3-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="695a3-136">Пограничный сервер или пограничный пул в сети периметра, если вы хотите, чтобы развертывание поддерживало Федеративные партнеры, общедоступные службы обмена МГНОВЕНными сообщениями, шлюз XMPP, удаленный доступ пользователей, участие анонимных пользователей в собраниях, или единой системы обмена сообщениями Exchange (единой системы обмена сообщениями).</span><span class="sxs-lookup"><span data-stu-id="695a3-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="695a3-137">Вы не можете совместно размещать какую-либо другую роль сервера вместе с пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="695a3-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="695a3-138">Мы рекомендуем использовать балансировку нагрузки DNS, где это необходимо, по применение аппаратной балансировки нагрузки также поддерживает.</span><span class="sxs-lookup"><span data-stu-id="695a3-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="695a3-139">Внутренний и внешний пограничный интерфейс должны использовать один тип балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="695a3-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="695a3-140">Нельзя использовать балансировку нагрузки на DNS в одном пограничном интерфейсе и аппаратную балансировку нагрузки в другом пограничном интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="695a3-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="695a3-141">Дополнительные сведения о требованиях и поддержке балансировки нагрузки приведены в статье [Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) в документации по планированию и [развертыванию доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="695a3-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="695a3-142">Сервер-посредник или пул, если вы хотите поддержать корпоративную голосовую связь или конференц-связь с телефонным подключением в интерфейсном пуле на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="695a3-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="695a3-143">В зависимости от способа развертывания поддержки корпоративной голосовой связи сервер-посредник можно разместить в пуле переднего плана (по умолчанию) или развернуть изолированный сервер-посредник или пул.</span><span class="sxs-lookup"><span data-stu-id="695a3-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="695a3-144">Можно использовать DNS, аппаратное обеспечение или балансировку нагрузки приложений (при необходимости) для распространения трафика с узла шлюза пула серверов-посредников, в том числе шлюза PSTN, IP-УАТС или управления периметром сеанса связи SIP (SBC). Сведения о планировании соответствующей топологии сервера-посредника приведены в статье [рекомендации по развертыванию сервера-посредника в Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="695a3-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="695a3-145">Сервер сохраняемого чата, если вы хотите, чтобы пользователи могли участвовать в многосторонних беседах на основе темы, которые сохраняются со временем.</span><span class="sxs-lookup"><span data-stu-id="695a3-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="695a3-146">Для обеспечения большей емкости и повышенной надежности топология может включать несколько компьютеров, на которых работает сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="695a3-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="695a3-147">Вы не можете совместно разместить сервер сохраняемого чата с другими ролями сервера в корпоративном пуле.</span><span class="sxs-lookup"><span data-stu-id="695a3-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="695a3-148">Тем не менее, сервер сохраняемого чата можно разместить на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="695a3-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="695a3-149">Для Persistent Chat требуется база данных и, если вы реализуете соответствие для Persistent Chat, база данных соответствия Persistent Chat, но их можно совместно размещать с базой данных архивации, базой данных мониторинга или на фоновом сервере интерфейсного пула Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="695a3-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="695a3-150">Сведения о планировании соответствующей топологии сервера сохраняемого чата приведены в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="695a3-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="695a3-151">Мониторинг, если требуется поддерживать сбор данных для качество взаимодействия (QoE) аудио-видео и регистрации вызовов (CDR) для Enterprise Voice и аудио- видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="695a3-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="695a3-152">Кроме того, можно установить Microsoft System Center Operations Manager (ранее Microsoft Operations Manager), который использует данные мониторинга CDR и QoE для создания практических оповещений в режиме реального времени, показывающих состояние надежности вызовов и качества мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="695a3-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="695a3-153">При развертывании системы мониторинга она совместно размещается на интерфейсных серверах или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="695a3-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="695a3-154">Для мониторинга требуется база данных, но ее можно совместно размещать с базой данных архивации, базой данных Persistent Chat, базой данных соответствия Persistent Chat или на фоновом сервере интерфейсного пула Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="695a3-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="695a3-155">Архивация, если вы хотите архивировать мгновенные сообщения и содержимое собраний (для выполнения требований соответствия) в своем развертывании.</span><span class="sxs-lookup"><span data-stu-id="695a3-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="695a3-156">При развертывании системы архивации она совместно размещается на интерфейсных серверах или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="695a3-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="695a3-157">Для хранения архивных копий требуется либо развертывание базы данных архивации, либо интеграция с хранилищем Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="695a3-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="695a3-158">Если вы используете оба, который называется *смешанным режимом*, хранилище Exchange 2013 используется для хранения архивных данных для пользователей, размещенных в Exchange 2013, а база данных архивации используется для архивации данных для всех других пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="695a3-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="695a3-159">Если вам требуется база данных архивации, ее можно совместно разместить с базой данных мониторинга, базой данных Persistent Chat, базой данных соответствия Persistent Chat или на фоновом сервере интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="695a3-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="695a3-160">Сведения о планировании подходящей топологии архивации приведены в статье [Планирование архивации в Lync Server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="695a3-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="695a3-161">Директор или пул директоров, если вы хотите обеспечить устойчивость и перенаправление запросов пользователей Lync Server 2013 к домашнему пулу пользователя, который может быть либо интерфейсным пулом Enterprise Edition, либо сервером Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="695a3-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="695a3-162">Рекомендуется развернуть Директора или пул Директора на каждом центральном узле, поддерживающем доступ внешних пользователей, в котором развертывается один или несколько интерфейсных пулов.</span><span class="sxs-lookup"><span data-stu-id="695a3-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="695a3-163">Каждый пул Директоров может содержать не более десяти Директоров.</span><span class="sxs-lookup"><span data-stu-id="695a3-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="695a3-164">Директор не может совместно размещаться с какой-либо другой ролью сервера.</span><span class="sxs-lookup"><span data-stu-id="695a3-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="695a3-165">Для получения дополнительных сведений о планировании подходящей топологии директоров обратитесь к разделу [сценарии для директора в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="695a3-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="695a3-166">Обратный прокси-сервер, который не является компонентом Lync Server 2013, но является обязательным, если вы хотите поддерживать общий доступ к веб-контенту для федеративных пользователей или поддерживать трафик Mobility.</span><span class="sxs-lookup"><span data-stu-id="695a3-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="695a3-167">Вы не можете совместно использовать обратный прокси-сервер с любой ролью сервера Lync Server 2013, но вы можете реализовать поддержку обратного прокси-сервера для развертывания Lync Server 2013, настроив поддержку существующего обратного прокси-сервера в Организации, который используется для других заявлен.</span><span class="sxs-lookup"><span data-stu-id="695a3-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="695a3-168">Подробнее о обратных прокси-серверах можно узнать в статье [Настройка обратных прокси-серверов для Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="695a3-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="695a3-169">В Lync Server 2013, мониторинг и архивация аудио-и видеоконференций, мониторинг и архивация выполняются на серверах переднего плана и больше не являются отдельными ролями сервера.</span><span class="sxs-lookup"><span data-stu-id="695a3-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="695a3-170">Все интерфейсные пулы и серверы Standard Edition, развертываемые в центральном узле, совместно используют следующие компоненты, которые развертываются в центральном узле:</span><span class="sxs-lookup"><span data-stu-id="695a3-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="695a3-171">директор или пул директоров;</span><span class="sxs-lookup"><span data-stu-id="695a3-171">Director or Director pool</span></span>

  - <span data-ttu-id="695a3-172">автономный сервер-посредник или пул-посредник;</span><span class="sxs-lookup"><span data-stu-id="695a3-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="695a3-173">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="695a3-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="695a3-174">пограничный сервер или пограничный пул;</span><span class="sxs-lookup"><span data-stu-id="695a3-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="695a3-175">сервер или пул Persistent Chat;</span><span class="sxs-lookup"><span data-stu-id="695a3-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="695a3-176">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="695a3-176">Monitoring</span></span>

  - <span data-ttu-id="695a3-177">Архивация</span><span class="sxs-lookup"><span data-stu-id="695a3-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="695a3-178">Сервер единой системы обмена сообщениями Exchange можно реализовать в развертывании Lync Server 2013, если требуется поддержка интеграции единой системы обмена сообщениями Exchange 2013, но она не является компонентом сайта Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="695a3-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="695a3-179">Нескольких центральных узлов также могут совместно использовать следующие компоненты, развернутые в одном центральном узле:</span><span class="sxs-lookup"><span data-stu-id="695a3-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="695a3-180">автономный сервер-посредник или пул-посредник;</span><span class="sxs-lookup"><span data-stu-id="695a3-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="695a3-181">пограничный сервер или пограничный пул;</span><span class="sxs-lookup"><span data-stu-id="695a3-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="695a3-182">сервер или пул Persistent Chat;</span><span class="sxs-lookup"><span data-stu-id="695a3-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="695a3-183">Архивация</span><span class="sxs-lookup"><span data-stu-id="695a3-183">Archiving</span></span>

  - <span data-ttu-id="695a3-184">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="695a3-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="695a3-185">Сервер единой системы обмена сообщениями Exchange можно реализовать в развертывании Lync Server 2013 и совместно использовать несколькими центральными сайтами, но он не является компонентом сайта Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="695a3-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="695a3-186">Дополнительные сведения о ролях и функциональных возможностях сервера Lync Server 2013 можно найти в статье Planning Server [roles in Lync server 2013](lync-server-2013-server-roles.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="695a3-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="695a3-187">Сводка по поддержке совместного использования серверов в Lync Server 2013 приведена [в разделе Поддерживаемые выровненные серверы в Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="695a3-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="695a3-188">Помимо ролей сервера и функций, описанных ранее в этом разделе, Lync Server 2013 содержит дополнительные компоненты и параметры, которые могут включать в себя некоторые или все из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="695a3-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="695a3-189">Брандмауэров</span><span class="sxs-lookup"><span data-stu-id="695a3-189">Firewalls</span></span>

  - <span data-ttu-id="695a3-190">Шлюзы ТСОП (при развертывании Enterprise Voice);</span><span class="sxs-lookup"><span data-stu-id="695a3-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="695a3-191">Сервер единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="695a3-191">Exchange UM Server</span></span>

  - <span data-ttu-id="695a3-192">балансировка нагрузки DNS;</span><span class="sxs-lookup"><span data-stu-id="695a3-192">DNS load balancing</span></span>

  - <span data-ttu-id="695a3-193">аппаратные подсистемы балансировки нагрузки;</span><span class="sxs-lookup"><span data-stu-id="695a3-193">Hardware load balancers</span></span>

  - <span data-ttu-id="695a3-194">базы данных SQL Server;</span><span class="sxs-lookup"><span data-stu-id="695a3-194">SQL Server databases</span></span>

  - <span data-ttu-id="695a3-195">общие файловые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="695a3-195">File shares</span></span>

<span data-ttu-id="695a3-196">Подробные сведения обо всех компонентах, компонентах и параметрах Lync Server 2013 можно найти в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="695a3-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="695a3-197">Топология и компоненты узла филиала (локально)</span><span class="sxs-lookup"><span data-stu-id="695a3-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="695a3-p115">Узел филиала связан с центральным узлом, а каждое устройство для обеспечения связи в филиалах в узле филиала связано с интерфейсным пулом Enterprise Edition или сервером Standard Edition в соответствующем центральном узле. Большая часть функций узлов филиалов зависит от центрального узла, поэтому компоненты узла филиала могут включать в себя только следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="695a3-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="695a3-200">Устройство для обеспечения связи в филиалах, объединяющее шлюз телефонной сети общего пользования (PSTN) с некоторыми функциями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="695a3-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="695a3-201">Сервер-посредник может быть размещен с помощью экземпляра регистратора на устройстве для обеспечения связи в филиалах, а также можно развернуть изолированный сервер-посредник или пул серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="695a3-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="695a3-202">Сервер для обеспечения связи в филиалах — это сервер под управлением Windows Server, на котором установлено программное обеспечение сервера регистратора и сервера-посредника Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="695a3-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="695a3-203">Автономный шлюз ТСОП (не являющийся частью устройства обеспечения связи в филиалах) и автономный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="695a3-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="695a3-204">Требования к серверам для обеспечения связи в филиалах совпадают с требованиями для любой роли сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="695a3-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

