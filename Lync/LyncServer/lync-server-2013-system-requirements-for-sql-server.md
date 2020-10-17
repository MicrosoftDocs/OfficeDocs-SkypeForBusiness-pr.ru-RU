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
ms.openlocfilehash: 6b9aa4a51ed7e75b413b0712297d02f5e8050fa2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497376"
---
# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="7ce78-102">Требования к системе для SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ce78-102">System requirements for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ce78-103">_**Последнее изменение темы:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="7ce78-103">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="7ce78-104">Перед развертыванием сервера Enterprise Edition установите Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012 на выделенном компьютере, удовлетворяющем требованиям к оборудованию.</span><span class="sxs-lookup"><span data-stu-id="7ce78-104">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="7ce78-105">Сведения о требованиях к оборудованию приведены в статье [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="7ce78-105">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="7ce78-106">Сведения о требованиях к программному обеспечению приведены в статье поддержка [программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="7ce78-106">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="7ce78-107">Сведения о разрешениях, необходимых для развертывания, приведены [в разделе разрешения развертывания для SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ce78-107">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="7ce78-108">Прежде чем создавать пул переднего плана, необходимо настроить брандмауэр Windows, чтобы разрешить доступ к серверу Lync Server 2013 для определенных портов, определив порты для сервера с помощью диспетчера конфигураций SQL Server и открытия портов в брандмауэре Windows с дополнительной безопасностью.</span><span class="sxs-lookup"><span data-stu-id="7ce78-108">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

