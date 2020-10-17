---
title: 'Lync Server 2013: резервное копирование баз данных архивации и мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08eea156d1b12f607270ea3b6d7472519128e472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523176"
---
# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="2a734-102">Резервное копирование баз данных архивации и мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a734-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a734-103">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="2a734-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="2a734-104">Если вы развернули архивирование или мониторинг, необходимо выполнить резервное копирование этих баз данных в соответствии с политикой резервного копирования SQL Server вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2a734-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a734-105">Резервные копии и мониторинг копируются при резервном копировании центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="2a734-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="2a734-106">Дополнительные сведения см <A href="lync-server-2013-backing-up-core-data-and-settings.md">в статье резервное копирование основных данных и параметров в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2a734-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2a734-107">Для архивации и мониторинга можно использовать средство SQL Server, например SQL Server Management Studio, для выполнения ручного резервного копирования, или можно использовать средства управления SQL Server для планирования регулярных и автоматических резервных копий.</span><span class="sxs-lookup"><span data-stu-id="2a734-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

