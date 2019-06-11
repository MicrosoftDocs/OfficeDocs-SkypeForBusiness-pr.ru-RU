---
title: 'Lync Server 2013: развертывание архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2e9373cf49a84110c3a8b70f20dd31072a171b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="2b883-102">Развертывание архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b883-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b883-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2b883-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2b883-104">Lync Server 2013 предоставляет решение для архивации содержимого и обмена мгновенными сообщениями в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b883-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="2b883-105">Вы можете реализовать поддержку архивации путем интеграции хранилища архивации с хранилищем Exchange 2013, используя базы данных SQL Server для хранения данных архивации Lync Server 2013 или с помощью Lync Server 2013 и Exchange 2013 Storage.</span><span class="sxs-lookup"><span data-stu-id="2b883-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="2b883-106">Вы управляете архивацией данных с помощью политик и конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="2b883-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="2b883-107">Подробные сведения можно найти в разделе [Планирование архивации в Lync server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию и [о том, как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="2b883-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="2b883-108">Вы можете использовать сведения из этого раздела для первоначальной настройки и настройки архивирования.</span><span class="sxs-lookup"><span data-stu-id="2b883-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="2b883-109">После развертывания вы можете изменить параметры архивации.</span><span class="sxs-lookup"><span data-stu-id="2b883-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="2b883-110">Подробные сведения о том, как использовать поддержку архивации для повседневного управления и для соблюдения новых требований в вашей организации, можно найти в разделе [Управление архивацией Lync Server 2013](lync-server-2013-managing-archiving.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="2b883-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2b883-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="2b883-111">In This Section</span></span>

  - [<span data-ttu-id="2b883-112">Как работает архивация в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b883-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="2b883-113">Контрольный список развертывания для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b883-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="2b883-114">Настройка системы и инфраструктуры для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b883-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="2b883-115">Добавление архивных баз данных в существующую развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b883-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="2b883-116">Настройка поддержки архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b883-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

