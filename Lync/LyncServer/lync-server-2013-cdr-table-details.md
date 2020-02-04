---
title: 'Lync Server 2013: сведения о таблице регистрации вызовов'
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
ms.openlocfilehash: 650caa5244eaf796c066f1388f2fcbb5d3b0703a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="1ec80-102">Сведения о таблице регистрации вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ec80-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1ec80-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1ec80-104">В следующих разделах описаны столбцы в каждой из таблиц схемы базы данных "сведения о звонке" (CDR).</span><span class="sxs-lookup"><span data-stu-id="1ec80-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ec80-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="1ec80-105">In This Section</span></span>

  - [<span data-ttu-id="1ec80-106">Таблица Application в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="1ec80-107">Таблица SessionCorrelation в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="1ec80-108">Таблица CallType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="1ec80-109">Таблица ClientVersions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="1ec80-110">Таблица Конференцежоинтимесрешолдс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="1ec80-111">Таблица ConferenceMessageCount в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="1ec80-112">Таблица Conferences в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="1ec80-113">Таблица ConferenceSessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="1ec80-114">Таблица ConferenceUris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="1ec80-115">Таблица ContentTypes в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="1ec80-116">Таблица DeRegisterType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="1ec80-117">Таблица Devices в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="1ec80-118">Таблица Dialogs в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="1ec80-119">Таблица EdgeServers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="1ec80-120">Таблица Ерроркатегори в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="1ec80-121">Таблица ErrorDef в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="1ec80-122">Таблица ErrorReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="1ec80-123">Таблица FileTransfers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="1ec80-124">Таблица FocusJoinsAndLeaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="1ec80-125">Интерфейсная таблица в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="1ec80-126">Таблица Gateways в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="1ec80-127">Таблица HardwareVersions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="1ec80-128">Таблица Имрепортсуммари в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="1ec80-129">Таблица Locations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="1ec80-130">Таблица Manufacturers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="1ec80-131">Таблица McuJoinsAndLeaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="1ec80-132">Таблица Mcus в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="1ec80-133">Таблица Media в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="1ec80-134">Таблица MediaList в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="1ec80-135">Таблица MediationServers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="1ec80-136">Таблица Мсмкпроцессинг в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="1ec80-137">Таблица Phones в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="1ec80-138">Таблица Pools в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="1ec80-139">Таблица ProgressReport в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="1ec80-140">Таблица Пуржесеттингс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="1ec80-141">Таблица Registration в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="1ec80-142">Таблица Roles в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="1ec80-143">Таблица Servers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="1ec80-144">Таблица SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="1ec80-145">Таблица Сипреспонсеметадата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="1ec80-146">Таблица "синдикации" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="1ec80-147">Таблица Синдикаторстенантмап в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="1ec80-148">Таблица задач в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="1ec80-149">Таблица Tenants в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="1ec80-150">Таблица UriTypes в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="1ec80-151">Таблица Users в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="1ec80-152">Таблица Усеражентдеф в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="1ec80-153">Таблица Усерстатистикс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="1ec80-154">Таблица VoipDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ec80-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

