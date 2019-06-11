---
title: 'Lync Server 2013: настройка SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da3cea6019b6314eccb2968f9b05ef44e7de75e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="a4be3-102">Настройка SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4be3-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4be3-103">_**Тема последнего изменения:** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="a4be3-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="a4be3-104">Для каждой развертываемой базы данных можно использовать один экземпляр SQL Server для всех баз данных для развертывания Lync Server 2013, который может быть размещен на сервере базы данных.</span><span class="sxs-lookup"><span data-stu-id="a4be3-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="a4be3-105">Подробнее о размещении базы данных можно узнать [в разделе Поддерживаемые параметры выровнений сервера в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="a4be3-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a4be3-106">Кроме того, каждый экземпляр сервера SQL Server должен быть установлен и доступен перед выполнением шагов в построителе топологии, который настроил базу данных, или создании баз данных с помощью командлетов Windows PowerShell вручную.</span><span class="sxs-lookup"><span data-stu-id="a4be3-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="a4be3-107">Подробные сведения о поддержке SQL Server можно найти в разделе [Настройка оборудования для Lync server 2013](lync-server-2013-hardware-setup.md).</span><span class="sxs-lookup"><span data-stu-id="a4be3-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="a4be3-108">Установка Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="a4be3-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="a4be3-109">Ознакомьтесь с документацией по Microsoft SQL Server 2012 <https://technet.microsoft.com/en-us/library/bb500395(v=sql.110).aspx>по адресу:.</span><span class="sxs-lookup"><span data-stu-id="a4be3-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/en-us/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

