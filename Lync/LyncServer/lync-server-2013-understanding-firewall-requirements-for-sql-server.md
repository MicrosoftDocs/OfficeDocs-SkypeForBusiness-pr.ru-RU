---
title: 'Lync Server 2013: обзор требований к брандмауэру для SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="34c90-102">Обзор требований к брандмауэру для SQL Server с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34c90-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34c90-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="34c90-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="34c90-104">Для развертывания в стандартном выпуске исключения брандмауэра создаются автоматически во время установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34c90-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="34c90-105">Тем не менее, для развертывания выпуска Enterprise Edition необходимо вручную настроить исключения брандмауэра на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34c90-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="34c90-106">Протокол TCP/IP позволяет использовать конкретный порт для определенного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="34c90-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="34c90-107">Это означает, что для сервера SQL Server вы можете назначить экземпляру базы данных по умолчанию порт 1433 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34c90-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="34c90-108">Для всех других экземпляров вам потребуется использовать диспетчер конфигурации SQL Server для назначения уникальных и неиспользуемых портов.</span><span class="sxs-lookup"><span data-stu-id="34c90-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="34c90-109">В этой статье рассматриваются следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="34c90-109">This topic covers:</span></span>

  - <span data-ttu-id="34c90-110">Требования к исключению брандмауэра при использовании экземпляра по умолчанию</span><span class="sxs-lookup"><span data-stu-id="34c90-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="34c90-111">Требования к исключению межсетевого экрана для службы браузера SQL Server</span><span class="sxs-lookup"><span data-stu-id="34c90-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="34c90-112">Требования к статическим портам для прослушивания при использовании именованных экземпляров</span><span class="sxs-lookup"><span data-stu-id="34c90-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="34c90-113">Требования к исключению брандмауэра при использовании экземпляра по умолчанию</span><span class="sxs-lookup"><span data-stu-id="34c90-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="34c90-114">Если вы используете экземпляр SQL Server по умолчанию для любой базы данных при развертывании Lync Server 2013, для обеспечения взаимодействия из пула переднего плана с экземпляром SQL Server по умолчанию используются следующие требования правил брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="34c90-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34c90-115">Протокол</span><span class="sxs-lookup"><span data-stu-id="34c90-115">Protocol</span></span></th>
<th><span data-ttu-id="34c90-116">Порт</span><span class="sxs-lookup"><span data-stu-id="34c90-116">Port</span></span></th>
<th><span data-ttu-id="34c90-117">Направление</span><span class="sxs-lookup"><span data-stu-id="34c90-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34c90-118">TCP</span><span class="sxs-lookup"><span data-stu-id="34c90-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="34c90-119">1433</span><span class="sxs-lookup"><span data-stu-id="34c90-119">1433</span></span></p></td>
<td><p><span data-ttu-id="34c90-120">Входящий на сервер SQL Server</span><span class="sxs-lookup"><span data-stu-id="34c90-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="34c90-121">Требования к исключению межсетевого экрана для службы браузера SQL Server</span><span class="sxs-lookup"><span data-stu-id="34c90-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="34c90-122">Служба "Обозреватель SQL Server" обнаружит экземпляры базы данных и настроит порт, для которого настроен экземпляр (с именем или по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="34c90-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34c90-123">Протокол</span><span class="sxs-lookup"><span data-stu-id="34c90-123">Protocol</span></span></th>
<th><span data-ttu-id="34c90-124">Порт</span><span class="sxs-lookup"><span data-stu-id="34c90-124">Port</span></span></th>
<th><span data-ttu-id="34c90-125">Направление</span><span class="sxs-lookup"><span data-stu-id="34c90-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34c90-126">UDP</span><span class="sxs-lookup"><span data-stu-id="34c90-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="34c90-127">1434</span><span class="sxs-lookup"><span data-stu-id="34c90-127">1434</span></span></p></td>
<td><p><span data-ttu-id="34c90-128">443</span><span class="sxs-lookup"><span data-stu-id="34c90-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="34c90-129">Требования к статическим портам для прослушивания при использовании именованных экземпляров</span><span class="sxs-lookup"><span data-stu-id="34c90-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="34c90-130">При использовании именованных экземпляров в конфигурации SQL Server для баз данных, поддерживающих Lync Server 2013, вы конфигурируете статические порты с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34c90-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="34c90-131">После того как статические порты будут назначены каждому именованному экземпляру, вы создаете исключения для каждого статического порта в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="34c90-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34c90-132">Протокол</span><span class="sxs-lookup"><span data-stu-id="34c90-132">Protocol</span></span></th>
<th><span data-ttu-id="34c90-133">Порт</span><span class="sxs-lookup"><span data-stu-id="34c90-133">Port</span></span></th>
<th><span data-ttu-id="34c90-134">Направление</span><span class="sxs-lookup"><span data-stu-id="34c90-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34c90-135">TCP</span><span class="sxs-lookup"><span data-stu-id="34c90-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="34c90-136">Статическое определение</span><span class="sxs-lookup"><span data-stu-id="34c90-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="34c90-137">443</span><span class="sxs-lookup"><span data-stu-id="34c90-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="34c90-138">Документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="34c90-138">SQL Server Documentation</span></span>

<span data-ttu-id="34c90-139">Документация по Microsoft SQL Server 2012 содержит подробные инструкции по настройке доступа к межсетевому экрану для баз данных.</span><span class="sxs-lookup"><span data-stu-id="34c90-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="34c90-140">Подробные сведения о Microsoft SQL Server 2012 можно найти в [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)разделе "Настройка брандмауэра Windows для обеспечения доступа к SQL Server".</span><span class="sxs-lookup"><span data-stu-id="34c90-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

