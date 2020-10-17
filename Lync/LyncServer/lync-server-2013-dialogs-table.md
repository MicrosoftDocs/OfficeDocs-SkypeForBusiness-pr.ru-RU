---
title: 'Lync Server 2013: таблица диалоговых окон'
description: 'Lync Server 2013: таблица диалогов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559705"
---
# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="9c84d-103">Таблица диалогов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c84d-103">Dialogs table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c84d-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9c84d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9c84d-105">Таблица диалоговых окон это вспомогательная таблица, в которой хранятся сведения о Диалогидс для одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="9c84d-105">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c84d-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="9c84d-106">Column</span></span></th>
<th><span data-ttu-id="9c84d-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9c84d-107">Data Type</span></span></th>
<th><span data-ttu-id="9c84d-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="9c84d-108">Key/Index</span></span></th>
<th><span data-ttu-id="9c84d-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="9c84d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c84d-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="9c84d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c84d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9c84d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c84d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="9c84d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9c84d-113">Время запроса сеанса; используется совместно с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="9c84d-113">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c84d-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="9c84d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9c84d-115">int</span><span class="sxs-lookup"><span data-stu-id="9c84d-115">int</span></span></p></td>
<td><p><span data-ttu-id="9c84d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="9c84d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="9c84d-117">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="9c84d-117">ID number to identify the session.</span></span> <span data-ttu-id="9c84d-118">Используется совместно с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="9c84d-118">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c84d-119"><strong>екстерналчекксум</strong></span><span class="sxs-lookup"><span data-stu-id="9c84d-119"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="9c84d-120">int</span><span class="sxs-lookup"><span data-stu-id="9c84d-120">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9c84d-121">Контрольная сумма Екстерналид.</span><span class="sxs-lookup"><span data-stu-id="9c84d-121">Checksum of the ExternalID.</span></span> <span data-ttu-id="9c84d-122">Это поле используется для увеличения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9c84d-122">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c84d-123"><strong>екстерналид</strong></span><span class="sxs-lookup"><span data-stu-id="9c84d-123"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c84d-124">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="9c84d-124">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9c84d-125">ИДЕНТИФИКАТОР диалогового окна SIP, сохраненный в виде двоичного файла.</span><span class="sxs-lookup"><span data-stu-id="9c84d-125">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="9c84d-126">Двоичный формат:</span><span class="sxs-lookup"><span data-stu-id="9c84d-126">The format of the binary is:</span></span></p>
<p><span data-ttu-id="9c84d-127">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="9c84d-127">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="9c84d-128">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9c84d-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

