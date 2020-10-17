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
ms.openlocfilehash: a4c26c719e9d7e3cd0922813896896925a9bb6f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519996"
---
# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="28a44-102">Таблица диалогов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28a44-102">Dialog table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28a44-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="28a44-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="28a44-104">Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.</span><span class="sxs-lookup"><span data-stu-id="28a44-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28a44-105"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="28a44-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="28a44-106"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="28a44-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="28a44-107"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="28a44-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="28a44-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="28a44-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28a44-109"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="28a44-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="28a44-110">datetime</span><span class="sxs-lookup"><span data-stu-id="28a44-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="28a44-111">Primary</span><span class="sxs-lookup"><span data-stu-id="28a44-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="28a44-p101">Время получения  агентом качества обслуживания первого отчета от звонящего или вызываемого абонента. Используется совместно с SessionSeq для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="28a44-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a44-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="28a44-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="28a44-115">int</span><span class="sxs-lookup"><span data-stu-id="28a44-115">int</span></span></p></td>
<td><p><span data-ttu-id="28a44-116">Primary</span><span class="sxs-lookup"><span data-stu-id="28a44-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="28a44-117">Порядковый номер, позволяющий различать сеансы с одинаковым ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="28a44-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a44-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="28a44-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="28a44-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="28a44-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="28a44-120">Глобальный уникальный идентификатор диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="28a44-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a44-121"><strong>диалогидчекксум</strong></span><span class="sxs-lookup"><span data-stu-id="28a44-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="28a44-122">int</span><span class="sxs-lookup"><span data-stu-id="28a44-122">int</span></span></p></td>
<td><p><span data-ttu-id="28a44-123">index</span><span class="sxs-lookup"><span data-stu-id="28a44-123">index</span></span></p></td>
<td><p><span data-ttu-id="28a44-124">Контрольная сумма идентификатора диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="28a44-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

