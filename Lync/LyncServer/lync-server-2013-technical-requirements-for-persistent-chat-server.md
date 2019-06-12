---
title: 'Lync Server 2013: технические требования для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b285e-102">Технические требования для постоянного сервера чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b285e-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b285e-103">_**Тема последнего изменения:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="b285e-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="b285e-104">На каждом компьютере, на котором размещается сохраняемый сервер чата, должен быть доступ к существующей топологии Lync Server 2013 со следующими компонентами:</span><span class="sxs-lookup"><span data-stu-id="b285e-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="b285e-105">**Lync Server 2013, сервер переднего плана.**  Сервер переднего плана — это основа для МАРШРУТИЗАЦИИ протокола SIP, которая делает связь между компьютерами, на которых запущены сохраняемый сервер чата, и функциональность сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b285e-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="b285e-106">Прежде чем приступить к развертыванию сервера сохраняемого чата, проверьте развертывание Lync Server 2013, Standard Edition или пула переднего плана сервера Lync Server и всех прочих внутренних компьютеров, работающих в Lync Server, в зависимости от вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b285e-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="b285e-107">В следующих разделах описаны особые требования для сервера сохраняемого чата и базы данных, хранящей сохраняемые данные чата.</span><span class="sxs-lookup"><span data-stu-id="b285e-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="b285e-108">Требования к серверу для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b285e-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="b285e-109">Подробные сведения о рекомендуемом оборудовании для развертывания Lync Server и последней версии сервера сохраняемого чата можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) в справочной системе по поддержке.</span><span class="sxs-lookup"><span data-stu-id="b285e-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b285e-110">Подробные сведения о поддержке сервера и средств операционной системы для Lync Server и сервера сохраняемого чата можно найти в документации поддержка [серверов и средств операционной системы в Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) .</span><span class="sxs-lookup"><span data-stu-id="b285e-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b285e-111">Сведения о дополнительном программном обеспечении, которое требуется для развертывания постоянного сервера чата, приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="b285e-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="b285e-112">Требования к серверному программному обеспечению для постоянного чата</span><span class="sxs-lookup"><span data-stu-id="b285e-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b285e-113">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="b285e-113">Software</span></span></th>
<th><span data-ttu-id="b285e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b285e-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b285e-115">Очередь сообщений</span><span class="sxs-lookup"><span data-stu-id="b285e-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="b285e-116">Используется при развертывании на сервере сохраняемого чата и в постоянной службе соответствия чатов.</span><span class="sxs-lookup"><span data-stu-id="b285e-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="b285e-117">Требования к базам данных сервера в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="b285e-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="b285e-118">Сервер сохраняемого чата использует базу данных сохраняемого чата для хранения истории чата, настройки и данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b285e-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="b285e-119">При необходимости для хранения данных о соответствии требованиям используется база данных соответствия требованиям сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b285e-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b285e-120">База данных сохраняемого чата (MGC) и база данных соответствия (мгккомп) могут находиться в одном и том же экземпляре SQL Server или на разных серверах SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b285e-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="b285e-121">Для подготовки платформы базы данных необходимо обеспечить соответствие каждого компьютера требованиям к оборудованию и затем установить обязательное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="b285e-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="b285e-122">Серверная платформа для серверов базы данных сохраняемого чата требует того же оборудования, что и серверная база данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b285e-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="b285e-123">Дополнительные сведения можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) .</span><span class="sxs-lookup"><span data-stu-id="b285e-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b285e-124">На сервере базы данных убедитесь, что установлено одно из следующих приложений:</span><span class="sxs-lookup"><span data-stu-id="b285e-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="b285e-125">Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="b285e-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="b285e-126">Подробнее о том, как установить Microsoft SQL Server 2012, можно найти в [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)разделе "Установка SQL Server 2012".</span><span class="sxs-lookup"><span data-stu-id="b285e-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="b285e-127">Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="b285e-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="b285e-128">Подробнее об установке Microsoft SQL Server 2008 R2 можно узнать в [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)разделе "Установка SQL Server (sql Server 2008 R2)".</span><span class="sxs-lookup"><span data-stu-id="b285e-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="b285e-129">Требования к сертификату сервера для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b285e-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="b285e-130">Подробные сведения о получении сертификатов, создании базы данных SQL Server и создании хранилищ файлов можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b285e-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

