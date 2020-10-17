---
title: 'Lync Server 2013: сведения о таблице сервера сохраняемого чата'
description: 'Lync Server 2013: сведения о таблице сервера сохраняемого чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a27feaaccf861d537127f06920cf903be5ae000
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545135"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="d2213-103">Сведения о таблице сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-103">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2213-104">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="d2213-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="d2213-105">В следующих разделах описываются столбцы каждой таблицы схемы базы данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d2213-105">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d2213-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="d2213-106">In This Section</span></span>

  - [<span data-ttu-id="d2213-107">tblADCookie в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-107">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="d2213-108">tblPrincipalMemberDifference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-108">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="d2213-109">Тбладупдатес в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-109">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="d2213-110">ТблпринЦипалмемберс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-110">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="d2213-111">tblPrincipalMeta в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-111">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="d2213-112">tblSkippedAffiliations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-112">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="d2213-113">tblPrincipalType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-113">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="d2213-114">tblPrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-114">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="d2213-115">ТблпринЦипалаффилиатионс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-115">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="d2213-116">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-116">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="d2213-117">tblRoleType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-117">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="d2213-118">tblScopePrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-118">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="d2213-119">tblPrincipalRole в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-119">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="d2213-120">tblSiopWhiteList в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-120">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="d2213-121">Тбленуматтрибуте в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-121">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="d2213-122">tblEnumValue в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-122">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="d2213-123">tblPrincipalInvites в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="d2213-124">tblChat в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="d2213-125">tblLastInviteId в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-125">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="d2213-126">tblLastChatId в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-126">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="d2213-127">Тблпреференце в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-127">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="d2213-128">Тблфилетокен в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-128">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="d2213-129">tblServerIdentity в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-129">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="d2213-130">tblAdminLock в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-130">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="d2213-131">Тблсистемревисион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-131">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="d2213-132">Тблактивепирс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-132">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="d2213-133">tblConfig в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-133">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="d2213-134">tblComplianceData в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-134">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="d2213-135">tblComplianceFanout в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-135">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="d2213-136">ТблкомплианцепартиЦипант в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-136">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="d2213-137">Тблкомплианцестате в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2213-137">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

