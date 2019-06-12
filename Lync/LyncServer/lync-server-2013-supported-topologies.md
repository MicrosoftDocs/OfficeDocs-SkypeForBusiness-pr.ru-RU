---
title: 'Lync Server 2013: поддерживаемые топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295d0cfc212fcf09b9752c43e918861f49ec7a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="40cf3-102">Поддерживаемые топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40cf3-102">Supported topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40cf3-103">_**Тема последнего изменения:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="40cf3-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="40cf3-104">Lync Server 2013 поддерживает развертывание локальных сайтов в Организации и интеграцию локальных развертываний с развертываниями Lync Online, которые называются гибридным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="40cf3-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="40cf3-105">В гибридном развертывании некоторые пользователи находятся в локальной среде, а некоторые — в сетевом режиме.</span><span class="sxs-lookup"><span data-stu-id="40cf3-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="40cf3-106">Для локальных развертываний Lync Server 2013 поддерживает развертывание одного или нескольких сайтов, которые можно масштабировать для достижения высокой доступности и требований к местоположению.</span><span class="sxs-lookup"><span data-stu-id="40cf3-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="40cf3-107">Вы можете структурировать эти сайты и их компоненты в соответствии с требованиями вашей организации к обеспечению доступа и устойчивости.</span><span class="sxs-lookup"><span data-stu-id="40cf3-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="40cf3-108">Развертывание в локальной среде Lync Server 2013 включает в себя следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="40cf3-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="40cf3-109">Развертывание должно включать хотя бы один центральный сайт (центр обработки данных).</span><span class="sxs-lookup"><span data-stu-id="40cf3-109">Your deployment must include at least one central site (also known as a data center).</span></span> <span data-ttu-id="40cf3-110">Каждый центральный сайт должен содержать по крайней мере одну группу переднего плана выпуска Enterprise Edition или один сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40cf3-110">Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server.</span></span> <span data-ttu-id="40cf3-111">Они состоят из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="40cf3-111">These consist of the following:</span></span>
    
      - <span data-ttu-id="40cf3-112">Пул переднего плана Enterprise Edition, состоящий из одного или нескольких серверов переднего плана (как правило, по крайней мере два сервера переднего плана для обеспечения масштабируемости) и отдельный сервер обратного доступа.</span><span class="sxs-lookup"><span data-stu-id="40cf3-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="40cf3-113">Пул переднего плана может содержать не более двенадцати серверных серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="40cf3-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="40cf3-114">Балансировка нагрузки требуется для нескольких серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="40cf3-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="40cf3-115">Для трафика SIP рекомендуется использовать балансировку нагрузки DNS, но также поддерживается балансировка нагрузки для оборудования.</span><span class="sxs-lookup"><span data-stu-id="40cf3-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="40cf3-116">Если вы используете балансировку нагрузки DNS для трафика SIP, вам по-прежнему понадобится балансировщик аппаратной балансировки нагрузки для HTTP-трафика.</span><span class="sxs-lookup"><span data-stu-id="40cf3-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="40cf3-117">Мы рекомендуем зеркальное отражение SQL Server для обеспечения высокой доступности баз данных.</span><span class="sxs-lookup"><span data-stu-id="40cf3-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="40cf3-118">Для серверной базы данных требуется отдельный экземпляр, но вы можете разгруппировать базу данных архивации, базу данных мониторинга, базу данных сохраняемого чата и базу данных соответствия требованиям к сохраненным чатам.</span><span class="sxs-lookup"><span data-stu-id="40cf3-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="40cf3-119">Lync Server 2013 поддерживает использование общего кластера для общих файлов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="40cf3-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="40cf3-120">Сведения о требованиях к хранению базы данных можно найти [в разделе Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="40cf3-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="40cf3-121">Сведения о требованиях к хранению файлов можно найти [в разделе Поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="40cf3-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="40cf3-122">При совместном сопоставлении баз данных Lync Server мы настоятельно рекомендуем оценить все факторы, которые могут повлиять на доступность и производительность.</span><span class="sxs-lookup"><span data-stu-id="40cf3-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="40cf3-123">Для проверки возможностей отработки отказа мы рекомендуем провести тестирование для всех сценариев отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="40cf3-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="40cf3-124">Сервер Standard Edition, включающий размещенную базу данных SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="40cf3-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="40cf3-125">Развертывание также может иметь один или несколько сайтов филиалов, связанных с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="40cf3-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="40cf3-126">В этом разделе описаны сайты и компоненты развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40cf3-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="40cf3-127">Подробные сведения о планировании сайтов, топологии и компонентах Lync Server 2013 можно найти в разделе [основы топологии, которые необходимо знать перед планированием для Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) и [ссылок на топологии в Lync Server 2013](lync-server-2013-reference-topologies.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="40cf3-128">Подробные сведения о интеграции компонентов предыдущих выпусков описаны [в разделе Поддерживаемые пути переноса и сосуществование сценариев в Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="40cf3-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40cf3-129">Растянутые пулы не поддерживаются для ролей "Передняя сторона", "граничный сервер", "устранение" и "режиссер".</span><span class="sxs-lookup"><span data-stu-id="40cf3-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="40cf3-130">Топологии и компоненты центрального сайта (локально)</span><span class="sxs-lookup"><span data-stu-id="40cf3-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="40cf3-131">Несмотря на то, что топология центрального сайта должна включать один пул переднего плана или один стандартный сервер выпуска, каждый центральный сайт может также содержать следующие:</span><span class="sxs-lookup"><span data-stu-id="40cf3-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="40cf3-132">Несколько пулов интерфейсов, которые могут находиться в одном и том же домене или разных доменах.</span><span class="sxs-lookup"><span data-stu-id="40cf3-132">Multiple Front End pools, which can be in the same domain or different domains.</span></span> <span data-ttu-id="40cf3-133">Однако все серверы переднего плана в пуле переднего плана и сервер, на котором они находятся, должны находиться в одном домене.</span><span class="sxs-lookup"><span data-stu-id="40cf3-133">However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="40cf3-134">Несколько серверов Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40cf3-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="40cf3-135">Сервер Office Web Apps, который используется с веб-приложениями Office в Lync Server 2013 для совместного использования и обработки презентаций Microsoft PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="40cf3-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="40cf3-136">Пул пограничного сервера или EDGE в демилитаризованной зоне, если вы хотите, чтобы развертывание поддерживало федеративных партнеров, общедоступное подключение к службе обмена МГНОВЕНными сообщениями, шлюз расширенных сообщений и протокола доступа (КСМПП), удаленный доступ пользователей, участие анонимных пользователей в собраниях. или единая система обмена сообщениями Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="40cf3-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="40cf3-137">Вы не можете различную роль сервера с помощью пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="40cf3-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="40cf3-138">Мы рекомендуем использовать балансировку нагрузки DNS, если это уместно, но также поддерживается балансировка нагрузки для оборудования.</span><span class="sxs-lookup"><span data-stu-id="40cf3-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="40cf3-139">Балансировка нагрузки на внутреннем и внешнем пограничным интерфейсах должна относиться к одному и тому же типу.</span><span class="sxs-lookup"><span data-stu-id="40cf3-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="40cf3-140">Невозможно осуществлять балансировку нагрузки на одном пограничном интерфейсе средствами DNS, а на другом — аппаратными средствами.</span><span class="sxs-lookup"><span data-stu-id="40cf3-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="40cf3-141">Подробные сведения о требованиях и поддержке балансировки нагрузки можно найти в разделе [Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) в документации по планированию и [развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="40cf3-142">Сервер или пул исправлений, если вы хотите поддерживать корпоративную голосовую связь или конференц-связь с телефонным подключением в пуле переднего плана на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="40cf3-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="40cf3-143">В зависимости от того, как вы разворачиваете поддержку корпоративной голосовой связи, вы можете разгруппировать сервер-посредник в пуле переднего плана (по умолчанию) или развернуть изолированный сервер или группу по отдельности.</span><span class="sxs-lookup"><span data-stu-id="40cf3-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="40cf3-144">Вы можете использовать DNS, оборудование или балансировку нагрузки приложений (при необходимости), чтобы распространить трафик с однорангового сайта пула, включая шлюз PSTN, IP-УАТС или элемент управления периметра магистральной магистрали SIP (SBC). Дополнительные сведения о планировании топологии сервера исправлений можно найти [в разделе рекомендации по развертыванию сервера обновлений в Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="40cf3-145">Сервер сохраняемого чата, если вы хотите, чтобы пользователи смогли принимать участие в многокомпонентных беседах, которые сохраняются с течением времени.</span><span class="sxs-lookup"><span data-stu-id="40cf3-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="40cf3-146">Для обеспечения большей производительности и повышенной надежности топология может включать несколько компьютеров, на которых запущен сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="40cf3-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="40cf3-147">Вы не можете разгруппировать сохраняемый сервер чата с другими ролями сервера в корпоративном пуле.</span><span class="sxs-lookup"><span data-stu-id="40cf3-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="40cf3-148">Тем не менее, вы можете разгруппировать сохраняемый сервер чата на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="40cf3-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="40cf3-149">Для сохраняемого чата требуется база данных и, если вы реализуете постоянную подведение на чат, базу данных соответствия требованиям сохраняемого чата, но базы данных могут быть выровнены вместе с базой данных архивации, контрольной базой данных или на обратном сервере Enterprise Edition. Пул внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="40cf3-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="40cf3-150">Подробные сведения о планировании топологии сервера сохраняемого чата можно найти [в разделе Планирование сохраняемого сервера чата в Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="40cf3-151">Наблюдение, если вы хотите поддерживать сбор данных для качества голосовой и видеосвязи (QoE) и записи сведений о звонке (CDR) для корпоративных голосовых и ных конференций в развертывании.</span><span class="sxs-lookup"><span data-stu-id="40cf3-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="40cf3-152">Кроме того, вы можете установить Microsoft System Center Operations Manager (прежнее название — Microsoft Operations Manager), в котором используются данные мониторинга CDR и QoE для создания практических оповещений в реальном времени, в которых показано состояние надежности и качества передачи звонков.</span><span class="sxs-lookup"><span data-stu-id="40cf3-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="40cf3-153">Наблюдение при развертывании размещается на серверах переднего плана или стандартном сервере выпуска.</span><span class="sxs-lookup"><span data-stu-id="40cf3-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="40cf3-154">Для наблюдения требуется база данных, но она может быть размещена с помощью базы данных архивации, сохраняемой базы данных чата, базы данных соответствия требованиям сохраняемого чата или на внутреннем сервере пула переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="40cf3-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="40cf3-155">Архивация, если вы хотите архивировать обмен мгновенными сообщениями и содержимое собраний (в целях обеспечения соответствия требованиям) в развертывании.</span><span class="sxs-lookup"><span data-stu-id="40cf3-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="40cf3-156">Архивирование при развертывании размещается на серверах переднего плана или стандартном сервере выпуска.</span><span class="sxs-lookup"><span data-stu-id="40cf3-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="40cf3-157">Для хранения архивов требуется либо развертывание базы данных архивации, либо интеграция с Exchange 2013 Storage.</span><span class="sxs-lookup"><span data-stu-id="40cf3-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="40cf3-158">Если вы используете и то, и другое ( *смешанный режим*), хранилище Exchange 2013 используется для хранения архивных данных для пользователей, расположенных на сервере Exchange 2013, а база данных архивации используется для архивации данных для всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="40cf3-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="40cf3-159">Если вам нужна база данных для архивации, она может быть размещена в базе данных мониторинга, базе данных сохраняемого чата, в сохраненном чате или на внутреннем сервере пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="40cf3-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="40cf3-160">Подробнее о том, как планировать подходящую топологию архивации, можно найти [в разделе Планирование архивации в Lync Server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="40cf3-161">Режиссер или Director pool, если вы хотите обеспечить устойчивость и перенаправление запросов пользователей Lync Server 2013 в домашнюю группу пользователя, который может быть либо пулом Enterprise Edition, либо стандартным сервером выпуска.</span><span class="sxs-lookup"><span data-stu-id="40cf3-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="40cf3-162">Рекомендуется развертывать режиссер или режиссер на каждом центральном сайте, поддерживающем доступ внешних пользователей, и на каждом центральном сайте, где развертываются один или несколько пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="40cf3-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="40cf3-163">Каждый режиссер может содержать не более десяти режиссеров.</span><span class="sxs-lookup"><span data-stu-id="40cf3-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="40cf3-164">Режиссер не может быть размещен с другой ролью сервера.</span><span class="sxs-lookup"><span data-stu-id="40cf3-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="40cf3-165">Сведения о планировании соответствующей топологии режиссера можно найти [в разделе сценарии для режиссера в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="40cf3-166">Обратный прокси-сервер, который не является компонентом Lync Server 2013, но является обязательным, если вы хотите поддерживать общий доступ к веб-контенту для федеративных пользователей или поддерживать трафик мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="40cf3-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="40cf3-167">Вы не можете допустить обратный прокси-сервер с любой ролью сервера Lync Server 2013, но вы можете реализовать поддержку обратной прокси-сервера для развертывания Lync Server 2013, настроив поддержку на существующем обратном прокси-сервере в вашей организации, который используется для других служб применения.</span><span class="sxs-lookup"><span data-stu-id="40cf3-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="40cf3-168">Подробнее об обратном прокси-серверах можно узнать в разделе [Настройка обратного прокси-сервера для Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40cf3-169">В Lync Server 2013 вы сможете конференции, отслеживать и архивировать их на серверах переднего плана и больше не являются отдельными серверными ролями.</span><span class="sxs-lookup"><span data-stu-id="40cf3-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="40cf3-170">Для всех высокоинтерфейсных пулов и серверов стандартных выпусков, развертываемых на центральном сайте, будет предоставлено развертывание для центрального сайта с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="40cf3-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="40cf3-171">Режиссер или режиссер</span><span class="sxs-lookup"><span data-stu-id="40cf3-171">Director or Director pool</span></span>

  - <span data-ttu-id="40cf3-172">Изолированный сервер или пул исправлений</span><span class="sxs-lookup"><span data-stu-id="40cf3-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="40cf3-173">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="40cf3-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="40cf3-174">Пул пограничного сервера или EDGE</span><span class="sxs-lookup"><span data-stu-id="40cf3-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="40cf3-175">Сервер или пул сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="40cf3-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="40cf3-176">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="40cf3-176">Monitoring</span></span>

  - <span data-ttu-id="40cf3-177">Архивирование</span><span class="sxs-lookup"><span data-stu-id="40cf3-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40cf3-178">Сервер UM Exchange можно реализовать вместе с развертыванием Lync Server 2013, если вы хотите поддерживать интеграцию единой системы обмена сообщениями Exchange 2013, но она не является компонентом сайта Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40cf3-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="40cf3-179">Несколько центральных сайтов также могут демонстрировать любые из следующих развертываний на одном центральном сайте:</span><span class="sxs-lookup"><span data-stu-id="40cf3-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="40cf3-180">Изолированный сервер или пул исправлений</span><span class="sxs-lookup"><span data-stu-id="40cf3-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="40cf3-181">Пул пограничного сервера или EDGE</span><span class="sxs-lookup"><span data-stu-id="40cf3-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="40cf3-182">Сервер или пул сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="40cf3-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="40cf3-183">Архивирование</span><span class="sxs-lookup"><span data-stu-id="40cf3-183">Archiving</span></span>

  - <span data-ttu-id="40cf3-184">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="40cf3-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40cf3-185">Сервер UM Exchange можно реализовать вместе с развертыванием Lync Server 2013 и совместно с несколькими центральными сайтами, но он не является компонентом сайта Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40cf3-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="40cf3-186">Подробные сведения о ролях и возможностях сервера Lync Server 2013 можно найти в разделе [роли сервера в Lync server 2013](lync-server-2013-server-roles.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="40cf3-187">Общие сведения о поддержке соразмещений на сервере Lync Server 2013 см. в разделе Поддерживаемые сведения о размещении [серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="40cf3-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="40cf3-188">Помимо ролей сервера и функциональных возможностей, рассмотренных ранее в этом разделе, в Lync Server 2013 есть дополнительные компоненты и параметры, которые могут включать в себя некоторые или все из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="40cf3-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="40cf3-189">Брандмауэры</span><span class="sxs-lookup"><span data-stu-id="40cf3-189">Firewalls</span></span>

  - <span data-ttu-id="40cf3-190">Шлюзы PSTN (при развертывании корпоративной голосовой связи)</span><span class="sxs-lookup"><span data-stu-id="40cf3-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="40cf3-191">Сервер Exchange UM</span><span class="sxs-lookup"><span data-stu-id="40cf3-191">Exchange UM Server</span></span>

  - <span data-ttu-id="40cf3-192">Балансировка нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="40cf3-192">DNS load balancing</span></span>

  - <span data-ttu-id="40cf3-193">Аппаратные подсистемы балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="40cf3-193">Hardware load balancers</span></span>

  - <span data-ttu-id="40cf3-194">Базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="40cf3-194">SQL Server databases</span></span>

  - <span data-ttu-id="40cf3-195">Общие файловые ресурсы</span><span class="sxs-lookup"><span data-stu-id="40cf3-195">File shares</span></span>

<span data-ttu-id="40cf3-196">Подробные сведения о всех функциях, компонентах и параметрах Lync Server 2013 можно найти в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="40cf3-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="40cf3-197">Топологии и компоненты сайтов филиалов (локально)</span><span class="sxs-lookup"><span data-stu-id="40cf3-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="40cf3-198">Сайт филиала связан с центральным сайтом, а все подключенные устройства филиалов на сайте филиала связаны с пулом переднего плана Enterprise Edition или с сервером Standard Edition на соответствующем центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="40cf3-198">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site.</span></span> <span data-ttu-id="40cf3-199">Сайты филиалов зависят от центрального сайта в большинстве функций, поэтому компоненты на сайте филиала содержат только следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="40cf3-199">Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="40cf3-200">Бесперебойно работающее устройство филиала, объединяющее коммутируемый шлюз телефонной сети (PSTN) с некоторыми функциями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40cf3-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="40cf3-201">Сервер-посредник может быть размещен с помощью экземпляра регистратора на работающем устройстве филиала, а также можно развернуть отдельный сервер-посредник или группу серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="40cf3-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="40cf3-202">Бесперебойно используемый сервер филиала, который является сервером под управлением Windows Server, на котором установлено программное обеспечение сервера регистратора Lync Server 2013 и сервер-посредника.</span><span class="sxs-lookup"><span data-stu-id="40cf3-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="40cf3-203">Отдельный шлюз PSTN (не входящий в бесперебойную подразделение) и изолированный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="40cf3-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="40cf3-204">Требования к оставшимся серверам филиалов совпадают с требованиями для любой роли сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40cf3-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

