---
title: 'Lync Server 2013: Общие сведения о требованиях к брандмауэру для SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f32d84e4cd08c40f95a47af7c988599678c972
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="4cdd1-102">Общие сведения о требованиях к брандмауэру для SQL Server с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cdd1-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cdd1-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4cdd1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4cdd1-104">Для развертывания Standard Edition исключения брандмауэра создаются автоматически во время установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="4cdd1-105">Тем не менее, для развертываний Enterprise Edition необходимо вручную настроить исключения брандмауэра на внутреннем сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="4cdd1-106">Протокол TCP/IP допускает использование определенного порта только для одного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="4cdd1-107">Это означает, что для сервера SQL Server вы можете назначить экземпляру базы данных по умолчанию стандартный TCP-порт 1433.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="4cdd1-108">Для других экземпляров необходимо назначить уникальные свободные порты с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="4cdd1-109">В этом разделе рассматриваются следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="4cdd1-109">This topic covers:</span></span>

  - <span data-ttu-id="4cdd1-110">требования к исключению брандмауэра для экземпляра по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="4cdd1-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="4cdd1-111">требования к исключению брандмауэра для службы обозревателя SQL Server;</span><span class="sxs-lookup"><span data-stu-id="4cdd1-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="4cdd1-112">требования к статическим прослушивающим портам при использовании именованных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="4cdd1-113">Требования к исключению брандмауэра при использовании экземпляра по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4cdd1-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="4cdd1-114">Если при развертывании Lync Server 2013 используется экземпляр SQL Server по умолчанию для любой базы данных, то для обеспечения связи между интерфейсным пулом и экземпляром SQL Server по умолчанию используются следующие требования к правилу брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cdd1-115">Протокол</span><span class="sxs-lookup"><span data-stu-id="4cdd1-115">Protocol</span></span></th>
<th><span data-ttu-id="4cdd1-116">Порт</span><span class="sxs-lookup"><span data-stu-id="4cdd1-116">Port</span></span></th>
<th><span data-ttu-id="4cdd1-117">Direction</span><span class="sxs-lookup"><span data-stu-id="4cdd1-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cdd1-118">TCP</span><span class="sxs-lookup"><span data-stu-id="4cdd1-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="4cdd1-119">1433</span><span class="sxs-lookup"><span data-stu-id="4cdd1-119">1433</span></span></p></td>
<td><p><span data-ttu-id="4cdd1-120">Входящий трафик SQL Server</span><span class="sxs-lookup"><span data-stu-id="4cdd1-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="4cdd1-121">Требования к исключению брандмауэра для службы обозревателя SQL Server</span><span class="sxs-lookup"><span data-stu-id="4cdd1-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="4cdd1-122">Служба обозревателя SQL Server обнаруживает экземпляры базы данных (именованные или экземпляры по умолчанию) и определяет настроенные для них порты.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cdd1-123">Протокол</span><span class="sxs-lookup"><span data-stu-id="4cdd1-123">Protocol</span></span></th>
<th><span data-ttu-id="4cdd1-124">Порт</span><span class="sxs-lookup"><span data-stu-id="4cdd1-124">Port</span></span></th>
<th><span data-ttu-id="4cdd1-125">Direction</span><span class="sxs-lookup"><span data-stu-id="4cdd1-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cdd1-126">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="4cdd1-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="4cdd1-127">1434</span><span class="sxs-lookup"><span data-stu-id="4cdd1-127">1434</span></span></p></td>
<td><p><span data-ttu-id="4cdd1-128">Получение</span><span class="sxs-lookup"><span data-stu-id="4cdd1-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="4cdd1-129">Требования к статическим прослушивающим портам при использовании именованных экземпляров</span><span class="sxs-lookup"><span data-stu-id="4cdd1-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="4cdd1-130">При использовании именованных экземпляров в конфигурации SQL Server для баз данных, поддерживающих Lync Server 2013, вы настраиваете статические порты с помощью диспетчера конфигураций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="4cdd1-131">Назначив статические порты каждому именованному экземпляру, нужно создать в брандмауэре исключение для каждого из этих портов.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cdd1-132">Протокол</span><span class="sxs-lookup"><span data-stu-id="4cdd1-132">Protocol</span></span></th>
<th><span data-ttu-id="4cdd1-133">Порт</span><span class="sxs-lookup"><span data-stu-id="4cdd1-133">Port</span></span></th>
<th><span data-ttu-id="4cdd1-134">Direction</span><span class="sxs-lookup"><span data-stu-id="4cdd1-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cdd1-135">TCP</span><span class="sxs-lookup"><span data-stu-id="4cdd1-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="4cdd1-136">Статический</span><span class="sxs-lookup"><span data-stu-id="4cdd1-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="4cdd1-137">Получение</span><span class="sxs-lookup"><span data-stu-id="4cdd1-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="4cdd1-138">Документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="4cdd1-138">SQL Server Documentation</span></span>

<span data-ttu-id="4cdd1-139">В документации по Microsoft SQL Server 2012 содержатся подробные инструкции по настройке доступа к базам данных через брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="4cdd1-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="4cdd1-140">Дополнительные сведения о Microsoft SQL Server 2012 содержатся в [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031)разделе "Настройка брандмауэра Windows для разрешения доступа к SQL Server".</span><span class="sxs-lookup"><span data-stu-id="4cdd1-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

