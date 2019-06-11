---
title: 'Lync Server 2013: резервное копирование архивных и контрольных баз данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdc7a6c871fcb5a91b3f98e2838cb3237e945e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="79e59-102">Архивирование и мониторинг баз данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e59-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79e59-103">_**Тема последнего изменения:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="79e59-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="79e59-104">Если вы развернули архивацию или наблюдение, необходимо выполнить резервное копирование этих баз данных в соответствии с политикой архивации SQL Server в своей организации.</span><span class="sxs-lookup"><span data-stu-id="79e59-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="79e59-105">Параметры архивации и мониторинга записываются при создании резервной копии хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="79e59-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="79e59-106">Подробности можно найти <A href="lync-server-2013-backing-up-core-data-and-settings.md">в разделе Резервное копирование основных данных и параметров в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="79e59-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="79e59-107">Для архивации и мониторинга вы можете использовать средство SQL Server, например SQL Server Management Studio, для выполнения ручного резервного копирования, а также использовать средства управления SQL Server для планирования регулярных и автоматических резервных копий.</span><span class="sxs-lookup"><span data-stu-id="79e59-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

