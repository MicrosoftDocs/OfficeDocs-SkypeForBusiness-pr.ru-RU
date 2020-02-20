---
title: 'Lync Server 2013: таблица диалоговых окон'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fb3fd81eb9128dea5479868617bb429b271719
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="61304-102">Таблица диалогов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61304-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61304-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="61304-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="61304-104">Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.</span><span class="sxs-lookup"><span data-stu-id="61304-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61304-105"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="61304-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="61304-106"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="61304-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="61304-107"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="61304-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="61304-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="61304-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61304-109"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="61304-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61304-110">datetime</span><span class="sxs-lookup"><span data-stu-id="61304-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="61304-111">Primary</span><span class="sxs-lookup"><span data-stu-id="61304-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="61304-p101">Время получения  агентом качества обслуживания первого отчета от звонящего или вызываемого абонента. Используется совместно с SessionSeq для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="61304-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61304-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="61304-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61304-115">int</span><span class="sxs-lookup"><span data-stu-id="61304-115">int</span></span></p></td>
<td><p><span data-ttu-id="61304-116">Primary</span><span class="sxs-lookup"><span data-stu-id="61304-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="61304-117">Порядковый номер, позволяющий различать сеансы с одинаковым ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="61304-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61304-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="61304-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="61304-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61304-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61304-120">Глобальный уникальный идентификатор диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="61304-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61304-121"><strong>диалогидчекксум</strong></span><span class="sxs-lookup"><span data-stu-id="61304-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="61304-122">int</span><span class="sxs-lookup"><span data-stu-id="61304-122">int</span></span></p></td>
<td><p><span data-ttu-id="61304-123">index</span><span class="sxs-lookup"><span data-stu-id="61304-123">index</span></span></p></td>
<td><p><span data-ttu-id="61304-124">Контрольная сумма идентификатора диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="61304-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

