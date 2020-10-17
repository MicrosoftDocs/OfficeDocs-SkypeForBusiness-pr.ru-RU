---
title: 'Lync Server 2013: сведения о таблице CDR'
description: 'Lync Server 2013: сведения о таблице CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a3dfd4ffccac2ac4a442eeb9ad9171defb41c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544395"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="68ccc-103">Сведения о таблице CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-103">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ccc-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="68ccc-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="68ccc-105">В следующих разделах описываются столбцы таблиц схемы базы данных записей регистрации вызовов.</span><span class="sxs-lookup"><span data-stu-id="68ccc-105">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68ccc-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="68ccc-106">In This Section</span></span>

  - [<span data-ttu-id="68ccc-107">Таблица Application в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-107">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="68ccc-108">Таблица Таблица callpriorities в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-108">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="68ccc-109">Таблица CallType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-109">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="68ccc-110">Таблица Таблица clientversions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-110">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="68ccc-111">Таблица Таблица conferencejointimethresholds в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-111">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="68ccc-112">Таблица Таблица conferencemessagecount в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-112">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="68ccc-113">Таблица конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-113">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="68ccc-114">Таблица Таблица conferencesessiondetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-114">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="68ccc-115">Таблица Таблица conferenceuris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-115">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="68ccc-116">Таблица ContentTypes в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-116">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="68ccc-117">Таблица Таблица deregistertype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-117">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="68ccc-118">Таблица Devices в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-118">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="68ccc-119">Таблица диалогов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-119">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="68ccc-120">Таблица Таблица edgeservers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-120">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="68ccc-121">Таблица ErrorCategory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-121">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="68ccc-122">Таблица Таблица errordef в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-122">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="68ccc-123">Таблица ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-123">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="68ccc-124">Таблица Таблица filetransfers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-124">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="68ccc-125">Таблица Таблица focusjoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-125">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="68ccc-126">Интерфейсная таблица в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-126">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="68ccc-127">Таблица Gateways в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-127">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="68ccc-128">Таблица Таблица hardwareversions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-128">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="68ccc-129">Таблица Имрепортсуммари в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-129">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="68ccc-130">Таблица Locations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-130">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="68ccc-131">Таблица производителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-131">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="68ccc-132">Таблица Таблица mcujoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-132">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="68ccc-133">Таблица MCUs в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-133">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="68ccc-134">Таблица мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-134">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="68ccc-135">Таблица Таблица medialist в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-135">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="68ccc-136">Таблица Таблица mediationservers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-136">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="68ccc-137">Таблица Мсмкпроцессинг в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-137">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="68ccc-138">Таблица phones в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-138">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="68ccc-139">Таблица Pools в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-139">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="68ccc-140">Таблица Таблица progressreport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-140">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="68ccc-141">Таблица Таблица purgesettings в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-141">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="68ccc-142">Таблица регистрации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-142">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="68ccc-143">Таблица Roles в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-143">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="68ccc-144">Таблица Servers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-144">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="68ccc-145">Таблица SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-145">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="68ccc-146">Таблица Сипреспонсеметадата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-146">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="68ccc-147">Таблица синдикации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-147">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="68ccc-148">Таблица Синдикаторстенантмап в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-148">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="68ccc-149">Таблица Task в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-149">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="68ccc-150">Таблица клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-150">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="68ccc-151">Таблица Таблица uritypes в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-151">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="68ccc-152">Таблица Users в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-152">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="68ccc-153">Таблица Таблица useragentdef в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-153">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="68ccc-154">Таблица Усерстатистикс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-154">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="68ccc-155">Таблица Таблица voipdetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ccc-155">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

