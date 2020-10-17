---
title: 'Lync Server 2013: сведения о таблице CDR'
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
ms.openlocfilehash: 47a9554be31e4ea93d7b8a0a2fc0de040d26d78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508056"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="0ea1e-102">Сведения о таблице CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-102">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ea1e-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0ea1e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0ea1e-104">В следующих разделах описываются столбцы таблиц схемы базы данных записей регистрации вызовов.</span><span class="sxs-lookup"><span data-stu-id="0ea1e-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0ea1e-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="0ea1e-105">In This Section</span></span>

  - [<span data-ttu-id="0ea1e-106">Таблица Application в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="0ea1e-107">Таблица Таблица callpriorities в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="0ea1e-108">Таблица CallType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="0ea1e-109">Таблица Таблица clientversions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="0ea1e-110">Таблица Таблица conferencejointimethresholds в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="0ea1e-111">Таблица Таблица conferencemessagecount в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="0ea1e-112">Таблица конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="0ea1e-113">Таблица Таблица conferencesessiondetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="0ea1e-114">Таблица Таблица conferenceuris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="0ea1e-115">Таблица ContentTypes в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="0ea1e-116">Таблица Таблица deregistertype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="0ea1e-117">Таблица Devices в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="0ea1e-118">Таблица диалогов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="0ea1e-119">Таблица Таблица edgeservers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="0ea1e-120">Таблица ErrorCategory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="0ea1e-121">Таблица Таблица errordef в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="0ea1e-122">Таблица ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="0ea1e-123">Таблица Таблица filetransfers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="0ea1e-124">Таблица Таблица focusjoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="0ea1e-125">Интерфейсная таблица в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="0ea1e-126">Таблица Gateways в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="0ea1e-127">Таблица Таблица hardwareversions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="0ea1e-128">Таблица Имрепортсуммари в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="0ea1e-129">Таблица Locations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="0ea1e-130">Таблица производителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="0ea1e-131">Таблица Таблица mcujoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="0ea1e-132">Таблица MCUs в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="0ea1e-133">Таблица мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="0ea1e-134">Таблица Таблица medialist в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="0ea1e-135">Таблица Таблица mediationservers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="0ea1e-136">Таблица Мсмкпроцессинг в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="0ea1e-137">Таблица phones в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="0ea1e-138">Таблица Pools в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="0ea1e-139">Таблица Таблица progressreport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="0ea1e-140">Таблица Таблица purgesettings в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="0ea1e-141">Таблица регистрации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="0ea1e-142">Таблица Roles в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="0ea1e-143">Таблица Servers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="0ea1e-144">Таблица SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="0ea1e-145">Таблица Сипреспонсеметадата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="0ea1e-146">Таблица синдикации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="0ea1e-147">Таблица Синдикаторстенантмап в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="0ea1e-148">Таблица Task в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="0ea1e-149">Таблица клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="0ea1e-150">Таблица Таблица uritypes в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="0ea1e-151">Таблица Users в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="0ea1e-152">Таблица Таблица useragentdef в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="0ea1e-153">Таблица Усерстатистикс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="0ea1e-154">Таблица Таблица voipdetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea1e-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

