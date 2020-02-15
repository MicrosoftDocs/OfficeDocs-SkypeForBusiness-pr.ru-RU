---
title: 'Lync Server 2013: Настройка SQL Server для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e52534744849e41fa08895bd114833892f4b8a2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="ef38b-102">Настройка SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef38b-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef38b-103">_**Последнее изменение темы:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="ef38b-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="ef38b-104">В подразделах этого раздела обсуждается развертывание и настройка SQL Server для использования в корпоративном развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef38b-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="ef38b-105">Серверы Standard Edition используют совместно размещенную версию SQL Server Express SQL Server, размер которой подходит для рабочих нагрузок сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ef38b-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="ef38b-106">В центральном хранилище Lync Server 2013 хранятся пользовательские данные для всех серверов Enterprise Edition в пуле, и оно разработано на внутреннем сервере, основанном на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ef38b-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="ef38b-107">Как централизованный репозиторий, центральное хранилище управления невозможно установить на том же компьютере, что и любой другой роли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef38b-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="ef38b-108">Центральное хранилище управления не может находиться на сервере Enterprise Edition в пуле.</span><span class="sxs-lookup"><span data-stu-id="ef38b-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="ef38b-109">Центральное хранилище управления создается автоматически при первой публикации топологии и выборе для создания баз данных.</span><span class="sxs-lookup"><span data-stu-id="ef38b-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="ef38b-110">Для успешного завершения установки на компьютере, который вы указываете в качестве фонового сервера, должно быть запущено программное обеспечение базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ef38b-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ef38b-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="ef38b-111">In This Section</span></span>

  - [<span data-ttu-id="ef38b-112">Размещение данных и файлов журналов SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef38b-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="ef38b-113">Настройка SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef38b-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="ef38b-114">Разрешения развертывания для SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef38b-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="ef38b-115">Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef38b-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="ef38b-116">Общие сведения о требованиях к брандмауэру для SQL Server с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef38b-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="ef38b-117">Настройка кластеризации SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef38b-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

