---
title: 'Lync Server 2013: таблица таблица medialist'
description: 'Lync Server 2013: таблица таблица medialist.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e54535cd4a081657e7dcd59446cf65aaa3af7cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572075"
---
# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="d0076-103">Таблица Таблица medialist в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0076-103">MediaList table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0076-104">_**Последнее изменение темы:** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="d0076-104">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="d0076-105">Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d0076-105">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0076-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="d0076-106">Column</span></span></th>
<th><span data-ttu-id="d0076-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d0076-107">Data Type</span></span></th>
<th><span data-ttu-id="d0076-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="d0076-108">Key/Index</span></span></th>
<th><span data-ttu-id="d0076-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="d0076-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0076-110"><strong>медиаид</strong></span><span class="sxs-lookup"><span data-stu-id="d0076-110"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="d0076-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0076-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d0076-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d0076-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0076-113">Значения: 1-7</span><span class="sxs-lookup"><span data-stu-id="d0076-113">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0076-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="d0076-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="d0076-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d0076-115">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0076-116">Статическое сопоставление значений Медиаид и мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="d0076-116">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d0076-117">1 — ОБМЕН МГНОВЕННЫМИ СООБЩЕНИЯМИ</span><span class="sxs-lookup"><span data-stu-id="d0076-117">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="d0076-118">2 — передача файла</span><span class="sxs-lookup"><span data-stu-id="d0076-118">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="d0076-119">3 — удаленный помощник</span><span class="sxs-lookup"><span data-stu-id="d0076-119">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="d0076-120">4 — совместный доступ к приложению</span><span class="sxs-lookup"><span data-stu-id="d0076-120">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="d0076-121">5 — звук</span><span class="sxs-lookup"><span data-stu-id="d0076-121">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="d0076-122">6 — видео</span><span class="sxs-lookup"><span data-stu-id="d0076-122">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="d0076-123">7 — приглашение из приложения</span><span class="sxs-lookup"><span data-stu-id="d0076-123">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d0076-124">Если вы пытаетесь определить тип модальности для значений в LcsCDR. SessionDetailsView. MediaTypes, необходимо использовать следующий фрагмент соединения:</span><span class="sxs-lookup"><span data-stu-id="d0076-124">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

