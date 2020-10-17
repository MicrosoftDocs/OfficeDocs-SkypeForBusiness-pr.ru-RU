---
title: 'Lync Server 2013: Управление архивацией'
description: 'Lync Server 2013: Управление архивацией.'
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
ms.openlocfilehash: 9c7010645f36a7144ea508447d2c628bc8feacb0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566475"
---
# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="2d674-103">Управление архивированием Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d674-103">Managing Lync Server 2013 Archiving</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d674-104">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="2d674-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="2d674-105">При развертывании архивации для организации указывается исходная конфигурация во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="2d674-105">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="2d674-106">Однако могут быть ситуации, в которых потребуется изменить реализацию поддержки архивации для ежедневного управления или для удовлетворения новых требований организации.</span><span class="sxs-lookup"><span data-stu-id="2d674-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="2d674-107">Например, может потребоваться по-другому настроить поддержку архивации для определенного сайта, пула или пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="2d674-107">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="2d674-108">Для пользователей, размещенных на Lync Server 2013, это необходимо для создания и настройки политик и конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="2d674-108">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="2d674-109">Если вы используете интеграцию с Microsoft Exchange, также необходимо настроить параметры Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2d674-109">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="2d674-110">В этом разделе предоставляются сведения и процедуры, позволяющие изменять развертывание архивации.</span><span class="sxs-lookup"><span data-stu-id="2d674-110">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d674-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="2d674-111">In This Section</span></span>

  - [<span data-ttu-id="2d674-112">Принцип работы архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d674-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="2d674-113">Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d674-113">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="2d674-114">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="2d674-114">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="2d674-115">Изменение параметров базы данных для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d674-115">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="2d674-116">Экспорт архивных данных из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d674-116">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

