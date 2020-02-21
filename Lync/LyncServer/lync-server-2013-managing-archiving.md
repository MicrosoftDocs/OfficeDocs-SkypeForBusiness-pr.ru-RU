---
title: 'Lync Server 2013: Управление архивацией'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b7e27efc0c691f83df685b441d38e0b26f5239
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="93fb5-102">Управление архивированием Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fb5-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93fb5-103">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="93fb5-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="93fb5-104">При развертывании архивации для организации указывается исходная конфигурация во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="93fb5-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="93fb5-105">Однако могут быть ситуации, в которых потребуется изменить реализацию поддержки архивации для ежедневного управления или для удовлетворения новых требований организации.</span><span class="sxs-lookup"><span data-stu-id="93fb5-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="93fb5-106">Например, может потребоваться по-другому настроить поддержку архивации для определенного сайта, пула или пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="93fb5-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="93fb5-107">Для пользователей, размещенных на Lync Server 2013, это необходимо для создания и настройки политик и конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="93fb5-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="93fb5-108">Если вы используете интеграцию с Microsoft Exchange, также необходимо настроить параметры Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="93fb5-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="93fb5-109">В этом разделе предоставляются сведения и процедуры, позволяющие изменять развертывание архивации.</span><span class="sxs-lookup"><span data-stu-id="93fb5-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93fb5-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="93fb5-110">In This Section</span></span>

  - [<span data-ttu-id="93fb5-111">Принцип работы архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fb5-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="93fb5-112">Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fb5-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="93fb5-113">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="93fb5-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="93fb5-114">Изменение параметров базы данных для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fb5-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="93fb5-115">Экспорт архивных данных из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fb5-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

