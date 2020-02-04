---
title: 'Lync Server 2013: системные требования для SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c798194cd921bcf2576bc2d9199ea28f7eaeb7ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="8df3d-102">Системные требования для SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8df3d-102">System requirements for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8df3d-103">_**Тема последнего изменения:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="8df3d-103">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="8df3d-104">Перед развертыванием сервера Enterprise Edition установите Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012 на выделенный компьютер, соответствующий требованиям к оборудованию.</span><span class="sxs-lookup"><span data-stu-id="8df3d-104">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="8df3d-105">Сведения о требованиях к оборудованию можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) .</span><span class="sxs-lookup"><span data-stu-id="8df3d-105">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="8df3d-106">Сведения о требованиях к программному обеспечению можно найти в разделе [Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="8df3d-106">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="8df3d-107">Сведения о разрешениях, необходимых для развертывания, содержатся [в разделе разрешения на развертывание для SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8df3d-107">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="8df3d-108">Перед созданием пула переднего плана необходимо также настроить брандмауэр Windows, чтобы разрешить доступ к SQL Server для Lync Server 2013 через определенные порты, определив порт для сервера с помощью диспетчера конфигурации SQL Server и открыв порты в брандмауэре Windows с Улучшенная безопасность.</span><span class="sxs-lookup"><span data-stu-id="8df3d-108">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

