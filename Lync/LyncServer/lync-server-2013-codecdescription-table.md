---
title: 'Lync Server 2013: таблица Кодекдескриптион'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed272afa7fe21a7b40004fb93dcdfa239b4caf8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520666"
---
# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="fb10e-102">Таблица Кодекдескриптион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb10e-102">CodecDescription table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb10e-103">_**Последнее изменение темы:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="fb10e-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="fb10e-104">В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками.</span><span class="sxs-lookup"><span data-stu-id="fb10e-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="fb10e-105">Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="fb10e-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="fb10e-106">Эта таблица была введена в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb10e-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb10e-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="fb10e-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fb10e-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="fb10e-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fb10e-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="fb10e-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fb10e-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="fb10e-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb10e-111"><strong>кодекдескриптионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="fb10e-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fb10e-112">smallint</span><span class="sxs-lookup"><span data-stu-id="fb10e-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="fb10e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fb10e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="fb10e-114">Уникальный идентификатор, назначенный кодеку.</span><span class="sxs-lookup"><span data-stu-id="fb10e-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb10e-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="fb10e-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="fb10e-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fb10e-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb10e-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="fb10e-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="fb10e-118">Уникальное описание кодека, соответствующего CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="fb10e-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

