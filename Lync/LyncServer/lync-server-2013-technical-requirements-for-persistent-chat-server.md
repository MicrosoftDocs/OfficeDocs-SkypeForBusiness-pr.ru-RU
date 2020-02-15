---
title: 'Lync Server 2013: технические требования для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba8e3e02efeddc1229d3616c0cdcaf4ca241bf24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6e726-102">Технические требования для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e726-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e726-103">_**Последнее изменение темы:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="6e726-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="6e726-104">Каждый компьютер, на котором размещается сервер сохраняемого чата, должен иметь доступ к существующей топологии Lync Server 2013 со следующими компонентами:</span><span class="sxs-lookup"><span data-stu-id="6e726-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="6e726-105">**Lync Server 2013, сервер переднего плана.**  Сервер переднего плана является основой для маршрутизации SIP, обеспечивающей связь между компьютерами с сервером сохраняемого чата и функциями сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="6e726-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="6e726-106">Прежде чем приступить к развертыванию сервера сохраняемого чата, проверьте развертывание Lync Server 2013, Standard Edition или интерфейсный пул Lync Server и все остальные внутренние компьютеры, на которых работает Lync Server, в соответствии с вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="6e726-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="6e726-107">В следующих разделах описываются конкретные требования для сервера сохраняемого чата и базы данных, в которых хранятся данные сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="6e726-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="6e726-108">Требования к серверу сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="6e726-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="6e726-109">Дополнительные сведения о рекомендуемом оборудовании для развертывания Lync Server и последней версии сервера сохраняемого чата приведены в статье [Server Hardware Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6e726-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6e726-110">Подробные сведения о поддержке сервера и средств операционной системы для Lync Server и сервера сохраняемого чата приведены в статье [Поддержка серверов и средств операционной системы в Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6e726-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6e726-111">Дополнительные сведения о дополнительном программном обеспечении, которое необходимо для развертывания сервера сохраняемого чата, приведено в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6e726-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="6e726-112">Необходимое программное обеспечение для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="6e726-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e726-113">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="6e726-113">Software</span></span></th>
<th><span data-ttu-id="6e726-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6e726-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e726-115">Очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="6e726-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="6e726-116">Используется сервером сохраняемого чата и службой соответствия сохраняемого чата, если она развернута.</span><span class="sxs-lookup"><span data-stu-id="6e726-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="6e726-117">Требования к базе данных сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="6e726-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="6e726-118">Сервер сохраняемого чата использует базу данных сохраняемого чата для хранения журнала чата, настройки и данных о подготовке пользователей.</span><span class="sxs-lookup"><span data-stu-id="6e726-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="6e726-119">При необходимости для хранения данных соответствия используется база данных соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="6e726-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e726-120">База данных сохраняемого чата (MGC) и база данных соответствия (mgccomp) могут находиться в том же экземпляре SQL Server или на разных серверах SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6e726-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="6e726-121">Чтобы подготовить платформу сервера базы данных, убедитесь, что каждый компьютер соответствует требованиям к оборудованию, а затем установите все необходимые программные компоненты.</span><span class="sxs-lookup"><span data-stu-id="6e726-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="6e726-122">Серверная платформа для серверов базы данных сохраняемого чата требует того же оборудования, что и серверный сервер базы данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e726-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="6e726-123">Дополнительные сведения: [аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6e726-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6e726-124">Убедитесь, что на сервере базы данных установлено одно из следующих программных приложений:</span><span class="sxs-lookup"><span data-stu-id="6e726-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="6e726-125">Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="6e726-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="6e726-126">Сведения о том, как установить Microsoft SQL Server 2012, можно найти в [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)разделе "Установка SQL Server 2012".</span><span class="sxs-lookup"><span data-stu-id="6e726-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="6e726-127">Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="6e726-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="6e726-128">Сведения о том, как установить Microsoft SQL Server 2008 R2, можно найти в [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)разделе "Установка SQL Server (sql Server 2008 R2)".</span><span class="sxs-lookup"><span data-stu-id="6e726-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="6e726-129">Требования к сертификатам сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="6e726-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="6e726-130">Для получения дополнительных сведений о получении сертификатов, создании базы данных SQL Server и создании хранилищ файлов ознакомьтесь со статьей [deploy Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6e726-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

