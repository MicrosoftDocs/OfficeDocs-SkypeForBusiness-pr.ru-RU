---
title: 'Lync Server 2013: Настройка системных платформ для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88e1a8aea999fdf134b0152a9d37b2d36fc81ee8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="0e057-102">Настройка системных платформ для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e057-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e057-103">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0e057-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0e057-104">Прежде чем начинать развертывание компонента архивации, вам следует установить требуемую операционную систему и все остальное требуемое программное обеспечение на оборудовании, соответствующем требованиям к системе:</span><span class="sxs-lookup"><span data-stu-id="0e057-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="0e057-105">\*\*\*\*   В развертываниях Lync Server 2013 для Lync Server 2013 нет серверов архивации.</span><span class="sxs-lookup"><span data-stu-id="0e057-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="0e057-106">Вместо этого на серверах переднего плана и серверах Standard Edition запускаются унифицированные агенты по сбору данных для архивации, поэтому для размещения архивации отдельная системная платформа не требуется.</span><span class="sxs-lookup"><span data-stu-id="0e057-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="0e057-107">**Платформа хранения данных**   в Lync Server 2013 можно хранить данные с помощью одного из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="0e057-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="0e057-108">**Интеграция с Microsoft Exchange**   если вы хотите хранить данные архивации Lync Server 2013 с помощью развертывания Exchange 2013, вместо или в дополнение к настройке отдельной базы данных для хранения данных архивации, развертывание Exchange должно работать под управлением Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0e057-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="0e057-109">Подробные сведения о настройке системных платформ для Exchange 2013 вы найдете в документации по продукту Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e057-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="0e057-110">**SQL Server**   если вы хотите использовать отдельную базу данных SQL Server для хранения данных архивации, а не или вместе с интеграцией Microsoft Exchange, перед развертыванием архивации необходимо настроить системную платформу для базы данных.</span><span class="sxs-lookup"><span data-stu-id="0e057-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="0e057-111">Требования к конкретной платформе системы зависят от того, используете ли вы Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012 для базы данных архивации.</span><span class="sxs-lookup"><span data-stu-id="0e057-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="0e057-112">Дополнительные сведения о настройке системных платформ для этих баз данных можно найти в документации по продукту Microsoft SQL Server 2008 R2 и Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="0e057-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="0e057-113">**Платформа файлового сервера**   Lync Server 2013 сохраняет файлы архивации Lync Server в том же расположении, что и для хранения файлов при настройке серверов переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0e057-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="0e057-114">Вы не можете указать отдельное расположение для хранения архивных файлов, поэтому соответствующая отдельная системная платформа не требуется.</span><span class="sxs-lookup"><span data-stu-id="0e057-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="0e057-115">Если вы используете интеграцию с Microsoft Exchange, Exchange 2013 файлы для архивированных коммуникаций Lync хранятся на серверах Exchange 2013 для пользователей, размещенных на этих серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e057-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

