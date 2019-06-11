---
title: 'Lync Server 2013: настройка SQL Server для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0154b468540873f9b8ae6796f30336327809d394
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="82f84-102">Настройка SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f84-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82f84-103">_**Тема последнего изменения:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="82f84-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="82f84-104">В этом разделе объясняется, как развернуть и настроить SQL Server для развертывания в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82f84-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="82f84-105">Серверы стандартных выпусков используют размещенную версию SQL Server Express на выровненном по размеру для рабочих нагрузок сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="82f84-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="82f84-106">Хранилище Lync Server 2013 Central Management содержит данные пользователей для всех серверов выпуска Enterprise Edition в рамках пула и предназначено для размещения на сервере SQL Server с интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="82f84-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="82f84-107">Централизованное хранилище не может быть установлено на том же компьютере, что и любая другая роль Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82f84-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="82f84-108">Хранилище Центрального управления не может находиться на сервере Enterprise Edition в пуле.</span><span class="sxs-lookup"><span data-stu-id="82f84-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="82f84-109">Хранилище Центрального управления создается автоматически при первой публикации топологии и выбирается для создания баз данных.</span><span class="sxs-lookup"><span data-stu-id="82f84-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="82f84-110">Чтобы установка прошла успешно, на компьютере, который вы указываете как сервер заднего использования, должно быть установлено программное обеспечение SQL Server Database.</span><span class="sxs-lookup"><span data-stu-id="82f84-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="82f84-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="82f84-111">In This Section</span></span>

  - [<span data-ttu-id="82f84-112">Размещение данных и файла журнала SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f84-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="82f84-113">Настройка SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f84-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="82f84-114">Разрешения на развертывание для SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f84-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="82f84-115">Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f84-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="82f84-116">Обзор требований к брандмауэру для SQL Server с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f84-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="82f84-117">Настройка кластеризации SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f84-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

