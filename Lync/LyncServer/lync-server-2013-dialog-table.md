---
title: 'Lync Server 2013: таблица Dialog'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47744cf17d3459c16e382c3551b427aa45b5ce6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="5572c-102">Таблица Dialog в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5572c-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5572c-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5572c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5572c-104">Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.</span><span class="sxs-lookup"><span data-stu-id="5572c-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5572c-105"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="5572c-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5572c-106"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="5572c-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5572c-107"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="5572c-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5572c-108"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="5572c-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5572c-109"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="5572c-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5572c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="5572c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="5572c-111">Primary</span><span class="sxs-lookup"><span data-stu-id="5572c-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="5572c-112">Время, когда агент качества (QoE) получает первый отчет от вызывающего или вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="5572c-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="5572c-113">Используется в сочетании с Сессионсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5572c-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5572c-114"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="5572c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5572c-115">целое</span><span class="sxs-lookup"><span data-stu-id="5572c-115">int</span></span></p></td>
<td><p><span data-ttu-id="5572c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="5572c-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="5572c-117">Порядковый номер, чтобы отличать сеансы связи с одинаковым Конференцедатетиме.</span><span class="sxs-lookup"><span data-stu-id="5572c-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5572c-118"><strong>Диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="5572c-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="5572c-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5572c-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5572c-120">ИДЕНТИФИКАТОР диалогового окна, который является глобально уникальным.</span><span class="sxs-lookup"><span data-stu-id="5572c-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5572c-121"><strong>Диалогидчекксум</strong></span><span class="sxs-lookup"><span data-stu-id="5572c-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="5572c-122">целое</span><span class="sxs-lookup"><span data-stu-id="5572c-122">int</span></span></p></td>
<td><p><span data-ttu-id="5572c-123">индекса</span><span class="sxs-lookup"><span data-stu-id="5572c-123">index</span></span></p></td>
<td><p><span data-ttu-id="5572c-124">Контрольная сумма идентификатора диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="5572c-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

