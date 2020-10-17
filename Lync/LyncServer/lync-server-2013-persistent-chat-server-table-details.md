---
title: 'Lync Server 2013: сведения о таблице сервера сохраняемого чата'
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
ms.openlocfilehash: cde75ceb141a81af1b6a093742edd23b4adf1716
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524226"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="75d31-102">Сведения о таблице сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-102">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75d31-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="75d31-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="75d31-104">В следующих разделах описываются столбцы каждой таблицы схемы базы данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="75d31-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="75d31-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="75d31-105">In This Section</span></span>

  - [<span data-ttu-id="75d31-106">tblADCookie в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="75d31-107">tblPrincipalMemberDifference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="75d31-108">Тбладупдатес в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="75d31-109">ТблпринЦипалмемберс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="75d31-110">tblPrincipalMeta в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="75d31-111">tblSkippedAffiliations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="75d31-112">tblPrincipalType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="75d31-113">tblPrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="75d31-114">ТблпринЦипалаффилиатионс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="75d31-115">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="75d31-116">tblRoleType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="75d31-117">tblScopePrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="75d31-118">tblPrincipalRole в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="75d31-119">tblSiopWhiteList в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="75d31-120">Тбленуматтрибуте в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="75d31-121">tblEnumValue в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="75d31-122">tblPrincipalInvites в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="75d31-123">tblChat в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="75d31-124">tblLastInviteId в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="75d31-125">tblLastChatId в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="75d31-126">Тблпреференце в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="75d31-127">Тблфилетокен в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="75d31-128">tblServerIdentity в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="75d31-129">tblAdminLock в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="75d31-130">Тблсистемревисион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="75d31-131">Тблактивепирс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="75d31-132">tblConfig в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="75d31-133">tblComplianceData в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="75d31-134">tblComplianceFanout в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="75d31-135">ТблкомплианцепартиЦипант в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="75d31-136">Тблкомплианцестате в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d31-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

