---
title: 'Lync Server 2013: новые функции сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd9288fea9105be27428ac94d992de6e147f4900
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534186"
---
# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="cf804-102">Новые функции сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf804-102">New Persistent Chat Server features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf804-103">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="cf804-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="cf804-104">Lync Server 2013, сервер сохраняемого чата позволяет принимать участие в многосторонних беседах на основе тем, которые сохраняются со временем.</span><span class="sxs-lookup"><span data-stu-id="cf804-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="cf804-105">Сервер сохраняемого чата поможет вашей организации выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cf804-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="cf804-106">Улучшить связь между рабочими группами, которые географически рассредоточены и выполняют разные функции.</span><span class="sxs-lookup"><span data-stu-id="cf804-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="cf804-107">Расширить доступ к информации и партнерские отношения.</span><span class="sxs-lookup"><span data-stu-id="cf804-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="cf804-108">Улучшить связь в крупной организации.</span><span class="sxs-lookup"><span data-stu-id="cf804-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="cf804-109">Уменьшить информационную нагрузку.</span><span class="sxs-lookup"><span data-stu-id="cf804-109">Reduce information overload</span></span>

  - <span data-ttu-id="cf804-110">Улучшить информированность.</span><span class="sxs-lookup"><span data-stu-id="cf804-110">Improve information awareness</span></span>

  - <span data-ttu-id="cf804-111">Увеличить распределение важного знания и информации.</span><span class="sxs-lookup"><span data-stu-id="cf804-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="cf804-112">Lync Server 2013, сервер сохраняемого чата недоступен в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf804-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="cf804-113">В настоящее время он доступен только для локальных клиентов Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cf804-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="cf804-114">В Lync 2013 функция сохраняемого чата встроена в клиент Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cf804-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="cf804-115">В результате у пользователей есть доступ к обмену мгновенными сообщениями и присутствия, аудио-и видеоконференциям, конференц-связи и сохраняемому разговору в клиенте Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cf804-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="cf804-116">Дополнительные сведения о клиенте Lync 2013 содержатся в разделе <https://go.microsoft.com/fwlink/p/?linkid=270877> .</span><span class="sxs-lookup"><span data-stu-id="cf804-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="cf804-117">В этом разделе описываются различия между новой версией Lync Server 2013, сервером сохраняемого чата и предыдущей версией (Microsoft Lync Server 2010, группового чата), в том числе:</span><span class="sxs-lookup"><span data-stu-id="cf804-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="cf804-118">Предоставление административного интерфейса в панели управления Lync Server и удаление средства администрирования группового чата</span><span class="sxs-lookup"><span data-stu-id="cf804-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="cf804-119">Интеграция параметров конфигурации сервера сохраняемого чата с построителем топологий путем удаления средства настройки групповой беседы</span><span class="sxs-lookup"><span data-stu-id="cf804-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="cf804-120">Упрощение миграции и обновления с предыдущих версий сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cf804-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="cf804-121">Предоставление решений для обеспечения высокой доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="cf804-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="cf804-122">Дополнительные сведения о последней версии сервера сохраняемого чата можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="cf804-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="cf804-123">Справка по сохраняемому разговору <https://go.microsoft.com/fwlink/p/?linkid=270945> , в которой представлен подробный список функций сохраняемого чата, принципы их работы и их использования во время работы сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="cf804-124">[Сервер планирования для сохраняемого чата в Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию [развертывание сервера сохраняемого чата в Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) в документации по развертыванию: [миграция с Lync Server 2010, группового чата или Office Communications Server 2007 R2 в группу сервера сохраняемого чата в](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) документации по миграции и управление [сервером Lync Server 2013 2013, сохраняемый чат](managing-lync-server-2013-persistent-chat-server.md) в документации по операциям, все из которых предоставляет инструкции по настройке сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="cf804-125">Файл Documentation.msi сервера сохраняемого чата (файл установщика Windows) позволяет пользователям получать доступ к всеобъемлющей автономной документации по серверу сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="cf804-126">Основные изменения топологии для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cf804-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="cf804-127">Ниже приведены высокоуровневые изменения для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="cf804-128">Теперь сервер сохраняемого чата является ролью сервера.</span><span class="sxs-lookup"><span data-stu-id="cf804-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="cf804-129">В Microsoft Lync Server 2010 сервер групповой чат являлся сторонним доверенным приложением для Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cf804-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="cf804-130">Сохраняемый чат можно добавить в топологию Lync Server 2013 с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="cf804-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="cf804-131">В Lync Server 2013 функции сервера сохраняемого чата реализованы с помощью трех новых ролей сервера:</span><span class="sxs-lookup"><span data-stu-id="cf804-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="cf804-132">**PersistentChatService:** Это роль сервера переднего плана для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="cf804-133">В развертываниях Standard Edition роль сервера сохраняемого чата размещается на сервере Standard Edition, развернутом загрузчиком, как и любой другой ролью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf804-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="cf804-134">В развертываниях Enterprise Edition роль службы сохраняемого чата разворачивается на автономных компьютерах с помощью загрузчика, как и любой другой роли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf804-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="cf804-135">**PersistentChatStore:** Внутренний сервер, соответствующий базе данных контента сохраняемого чата, где хранится содержимое чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="cf804-136">**PersistentChatComplianceStore:** Роль внутреннего сервера, соответствующая базе данных соответствия сохраняемого чата, в которой хранятся все события соответствия.</span><span class="sxs-lookup"><span data-stu-id="cf804-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="cf804-137">Эти роли сервера сохраняемого чата являются необязательными и устанавливаются только клиентами, которые хотят обеспечить широкие возможности сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="cf804-138">Роль **PersistentChatComplianceStore** требуется только в том случае, если выбрана установка соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="cf804-139">Роль **PersistentChatService** запускает две службы:</span><span class="sxs-lookup"><span data-stu-id="cf804-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="cf804-140">Служба сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cf804-140">Persistent Chat service</span></span>

  - <span data-ttu-id="cf804-141">Служба соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cf804-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="cf804-142">Если эти службы работают на каждом сервере сохраняемого чата, обеспечивается высокая доступность этих служб в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="cf804-143">Кроме того, для поддержки отправки и загрузки файлов в помещениях сохраняемого чата сервер сохраняемого чата включает веб-службу.</span><span class="sxs-lookup"><span data-stu-id="cf804-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="cf804-144">Ранее эта служба была размещена на сервере сохраняемого чата, интерфейсном сервере и необходимых службах IIS для установки в качестве необходимого компонента.</span><span class="sxs-lookup"><span data-stu-id="cf804-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="cf804-145">В сервере сохраняемого чата Lync Server 2013 веб-служба отправки и загрузки файлов размещена на сервере переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf804-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="cf804-146">В качестве побочного действия службы IIS больше не являются обязательным условием для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="cf804-147">Веб-служба отправки и загрузки файлов определяется как **PersistentChat** в ДИСПЕТЧЕРЕ служб IIS.</span><span class="sxs-lookup"><span data-stu-id="cf804-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cf804-148">Роль <STRONG>PersistentChatService</STRONG> может выполняться на том же сервере, что и &nbsp; сервер переднего плана Lync Server 2013, только если этот сервер переднего плана является &nbsp; сервером переднего плана Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cf804-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="cf804-149">Роль <STRONG>PersistentChatService</STRONG> не может выполняться независимо от &nbsp; сервера переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf804-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="cf804-150">Его можно установить только в контексте развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf804-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="cf804-151">В сервере сохраняемого чата служба поиска удалена.</span><span class="sxs-lookup"><span data-stu-id="cf804-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="cf804-152">В Lync Server 2010, Group Chat служба поиска выполнялась на каждом сервере переднего плана сервера группового чата и выполняет маршрутизацию на один из серверов каналов.</span><span class="sxs-lookup"><span data-stu-id="cf804-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="cf804-153">Lync Server 2013 опирается на маршрутизацию с помощью объектов Contact, в которых каждый пул серверов сохраняемого чата представляется объектом Contact, который используется серверами переднего плана Lync Server для идентификации и маршрутизации запросов в соответствующий пул серверов сохраняемого чата, а также для одного из компьютеров, на которых работает сервер сохраняемого чата в пуле.</span><span class="sxs-lookup"><span data-stu-id="cf804-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="cf804-154">В Lync Server 2013 существуют изменения в службе соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cf804-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="cf804-155">В Lync Server 2010 служба соответствия работала автономно (без совместного размещения) и только на отдельном сервере.</span><span class="sxs-lookup"><span data-stu-id="cf804-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="cf804-156">Служба соответствия теперь работает на всех серверах переднего плана сервера сохраняемого чата, параллельно со службой сохраняемого чата и поэтому обеспечивает высокий уровень доступности в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="cf804-157">Можно настроить один адаптер соответствия для извлечения данных из базы данных соответствия в одну из других систем (XML-файл, архивы, размещенные в Exchange, и т. п.).</span><span class="sxs-lookup"><span data-stu-id="cf804-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="cf804-158">Сервер сохраняемого чата включает адаптер XML.</span><span class="sxs-lookup"><span data-stu-id="cf804-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="cf804-159">Очередь Message Queuing (также называемая MSMQ), которая совместно используется службой сохраняемого чата и службой соответствия на каждом сервере переднего плана сервера сохраняемого чата, теперь является частной, совместно используемой только двумя службами.</span><span class="sxs-lookup"><span data-stu-id="cf804-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="cf804-160">Все службы соответствия записывают данные в одну внутреннюю базу данных соответствия.</span><span class="sxs-lookup"><span data-stu-id="cf804-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="cf804-161">Также они все читают из этой базы данных с целью отправки данных в свой экземпляр адаптера.</span><span class="sxs-lookup"><span data-stu-id="cf804-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="cf804-162">Тыловой сервер соответствия представлен в виде новой роли тылового сервера.</span><span class="sxs-lookup"><span data-stu-id="cf804-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cf804-163">Как и в предыдущих версиях, все данные о соответствии требованиям обрабатываются только один раз.</span><span class="sxs-lookup"><span data-stu-id="cf804-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="cf804-164">Данные могут обрабатываться любыми экземплярами адаптеров, которые вызываются службой соответствия, запущенными на различных компьютерах сервера, работающего в Lync Server 2013, сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="cf804-165">На сервере сохраняемого чата любой из экземпляров адаптера может обработать данные.</span><span class="sxs-lookup"><span data-stu-id="cf804-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf804-166">Сведения об установке очереди сообщений можно найти в <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">статье Установка операционных систем и необходимого программного обеспечения на серверах для Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="cf804-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="cf804-167">В Lync Server 2013 существуют улучшения высокого уровня доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="cf804-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="cf804-168">Улучшения высокого уровня доступности: зеркальное отображение SQL Server используется для обеспечения высокой доступности базы данных контента сервера сохраняемого чата и базы данных соответствия сохраняемого чата в центре обработки данных (на месте).</span><span class="sxs-lookup"><span data-stu-id="cf804-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="cf804-169">Улучшения аварийного восстановления: сервер сохраняемого чата поддерживает архитектуру растянутого пула, позволяющую растянуть один пул серверов сохраняемого чата на два сайта (то есть один логический пул в топологии, при котором серверы в пуле физически располагаются на двух сайтах).</span><span class="sxs-lookup"><span data-stu-id="cf804-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="cf804-170">Доставка журналов SQL Server используется для аварийного восстановления на нескольких сайтах.</span><span class="sxs-lookup"><span data-stu-id="cf804-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="cf804-171">Дополнительные сведения о высокой доступности и аварийном восстановлении приведены в статье [Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="cf804-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="cf804-172">Основные изменения в администрировании и управлении для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="cf804-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="cf804-173">Lync Server 2013 упрощает администрирование и управление сервером сохраняемого чата, предоставляя следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="cf804-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="cf804-174">Унифицированное администрирование и управление.</span><span class="sxs-lookup"><span data-stu-id="cf804-174">Unified administration and management.</span></span> <span data-ttu-id="cf804-175">Lync Server 2013 упрощает управление и администрирование сервера сохраняемого чата с помощью средств, которые уже знакомы администраторам Lync.</span><span class="sxs-lookup"><span data-stu-id="cf804-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="cf804-176">Сервер сохраняемого чата включает в себя административный интерфейс пользователя, интегрированный с панелью управления Lync Server, который устраняет проблемы с производительностью предыдущих версий пользовательского интерфейса сервера группового чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="cf804-177">Кроме того, сервер сохраняемого чата включает набор командлетов Windows PowerShell для администрирования и управления категориями серверов сохраняемого чата, серверными комнатами сохраняемого чата (включая удаление комнат и очистку устаревшего контента) и надстроек.</span><span class="sxs-lookup"><span data-stu-id="cf804-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="cf804-178">Упрощенная модель администрирования.</span><span class="sxs-lookup"><span data-stu-id="cf804-178">Simplified administration model.</span></span> <span data-ttu-id="cf804-179">Lync Server 2013 изменился и упростил модель сервера сохраняемого чата, изменяя следующие ключевые требования к клиенту:</span><span class="sxs-lookup"><span data-stu-id="cf804-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="cf804-180">Устранение сложных вложенных иерархических систем областей действия и категорий.</span><span class="sxs-lookup"><span data-stu-id="cf804-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="cf804-181">Поддержка определения списков запрещенных и разрешенных списков (областей) для текущих клиентов Миндалигн, которые планируется перенести на сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="cf804-182">Чем отличаются роли пользователей от предыдущих версий сервера для группового чата?</span><span class="sxs-lookup"><span data-stu-id="cf804-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="cf804-183">Lync Server 2010, групповой чат имел роль администратора пользователей, роль администратора комнаты чата и роль администратора Lync Server, которые могут управлять надстройками. Сервер сохраняемого чата просто предоставляет роль администратора сохраняемого чата (аналогично другим ролям управления доступом на основе ролей в Lync Server (RBAC)).</span><span class="sxs-lookup"><span data-stu-id="cf804-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="cf804-184">Любой пользователь, являющийся членом этой роли RBAC, может управлять комнатами чата, надстройками и категориями (и, следовательно, получать доступ пользователей по этим категориям) и настраивать пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="cf804-185">Чем отличаются категории комнат чата от предыдущих версий сервера для группового чата?</span><span class="sxs-lookup"><span data-stu-id="cf804-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="cf804-186">Категории комнат чата больше не могут быть вложенными, и больше нельзя изменять корневую категорию.</span><span class="sxs-lookup"><span data-stu-id="cf804-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="cf804-187">AllowedMembers/DeniedMembers состоит в том, что область, используемая в предыдущих версиях группового чата (за исключением того, что она не поддерживала указание запрещенного списка).</span><span class="sxs-lookup"><span data-stu-id="cf804-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="cf804-188">Области больше нельзя переопределять, поскольку отсутствуют вложенные категории.</span><span class="sxs-lookup"><span data-stu-id="cf804-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="cf804-189">Администратор сохраняемого чата в Lync Server 2013 может создавать категории комнат чата и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="cf804-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="cf804-190">В процессе создания и управления категориями комнат чата администратор сохраняемого чата может настраивать субъекты (группы Active Directory/контейнеры и пользователей), которые имеют доступ к участникам или создателям чатов для конкретной категории.</span><span class="sxs-lookup"><span data-stu-id="cf804-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="cf804-191">Администратор сохраняемого чата также может добавлять DeniedMembers к категории, и они становятся явными исключениями в список разрешенных.</span><span class="sxs-lookup"><span data-stu-id="cf804-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="cf804-192">Участники DeniedMembers переопределяют участников AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="cf804-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="cf804-193">Чем отличаются свойства комнаты чата из предыдущих версий сервера для группового чата?</span><span class="sxs-lookup"><span data-stu-id="cf804-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="cf804-194">В Lync Server 2013 и на сервере сохраняемого чата существует новая концепция открытых комнат чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="cf804-195">Все разрешенные члены могут присоединяться к комнате чата без эксклюзивного членства.</span><span class="sxs-lookup"><span data-stu-id="cf804-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="cf804-196">Удалены следующие свойства комнаты чата, включенные в предыдущие версии сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="cf804-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="cf804-197">Тема: комната теперь имеет только описание.</span><span class="sxs-lookup"><span data-stu-id="cf804-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="cf804-198">Создание нового списка участников: на сервере сохраняемого чата все комнаты чата начинаются с пустого членства (и могут максимально разрешать членство, равное разрешенным членам).</span><span class="sxs-lookup"><span data-stu-id="cf804-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="cf804-p119">Отправка файлов: параметр в комнатах чата, указывавший, разрешена ли отправка и загрузка файлов. Теперь это устанавливается только на уровне категории и применяется ко всем комнатам в этой категории.</span><span class="sxs-lookup"><span data-stu-id="cf804-p119">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed. This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="cf804-201">Журнал чата: параметр в комнатах чата, указывавший, включено ли ведение журнала чата. Теперь это устанавливается только на уровне категории и применяется ко всем комнатам в этой категории.</span><span class="sxs-lookup"><span data-stu-id="cf804-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="cf804-p120">Приглашения: либо комната наследует параметр приглашений для категории, либо этот параметр отключается в комнате. В комнате нельзя включить приглашения, если в категории они были отключены.</span><span class="sxs-lookup"><span data-stu-id="cf804-p120">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room. A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="cf804-204">Чем отличаются политики от предыдущих версий сервера для группового чата?</span><span class="sxs-lookup"><span data-stu-id="cf804-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="cf804-205">На сервере сохраняемого чата новая политика Lync включена с сохраняемым чат на уровне пользователя/пула/сайта/глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="cf804-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="cf804-206">В клиенте Lync 2013 среда сохраняемого чата доступна только для пользователей, включенных политикой для сохраняемого чата (напрямую или с помощью параметра pool/site/Global/Global).</span><span class="sxs-lookup"><span data-stu-id="cf804-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="cf804-207">В предыдущих версиях сервера группового чата нет политик, интегрированных в политики Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf804-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="cf804-208">На уровне пользователя, на уровне категории или на уровне комнаты с помощью функции на уровне пользователя **Может отправлять файлы** можно было сделать пользователя администратором пользователей, администратором комнаты чата или разрешить пользователю отправлять файлы.</span><span class="sxs-lookup"><span data-stu-id="cf804-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="cf804-209">Компонент **отправки файлов** сервера сохраняемого чата относится только к категории.</span><span class="sxs-lookup"><span data-stu-id="cf804-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="cf804-210">Ведение журнала</span><span class="sxs-lookup"><span data-stu-id="cf804-210">Logging</span></span>

<span data-ttu-id="cf804-211">Ведение журнала для сервера сохраняемого чата и System Center Operations Manager встроено в журнал трассировки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf804-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf804-212">См. также</span><span class="sxs-lookup"><span data-stu-id="cf804-212">See Also</span></span>


[<span data-ttu-id="cf804-213">Планирование сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf804-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
