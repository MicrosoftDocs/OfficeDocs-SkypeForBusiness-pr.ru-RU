---
title: 'Lync Server 2013: представление мультимедиа'
description: 'Lync Server 2013: представление мультимедиа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558015"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="ae68e-103">Представление мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae68e-103">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae68e-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ae68e-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ae68e-105">В представлении "Мультимедиа" хранятся данные об одном типе мультимедийных данных, используемых в одноранговом сеансе.</span><span class="sxs-lookup"><span data-stu-id="ae68e-105">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="ae68e-106">Один сеанс может быть представлен несколькими записями в таблице, если используется более одного типа мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ae68e-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="ae68e-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ae68e-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae68e-p102">Представление "Мультимедиа" не используется для расчета продолжительности воспроизведения мультимедиа в ходе сеанса. На представлении отображены сведения о сигнале для обмена мультимедиа в рамках сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а значение StartTime определяет время отправки запроса INVITE. Время приглашения может не совпадать с временем начала воспроизведения мультимедиа, поскольку воспроизведение мультимедиа начинается только после подтверждения приема сеанса.</span><span class="sxs-lookup"><span data-stu-id="ae68e-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="ae68e-111">Представление мультимедиа содержит все столбцы в [представлении SessionDetails в Lync Server 2013](lync-server-2013-sessiondetails-view.md) , а также перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="ae68e-111">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae68e-112">Столбец</span><span class="sxs-lookup"><span data-stu-id="ae68e-112">Column</span></span></th>
<th><span data-ttu-id="ae68e-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ae68e-113">Data Type</span></span></th>
<th><span data-ttu-id="ae68e-114">Сведения</span><span class="sxs-lookup"><span data-stu-id="ae68e-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae68e-115"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="ae68e-115"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="ae68e-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ae68e-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae68e-117">Тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ae68e-117">Media type.</span></span> <span data-ttu-id="ae68e-118">Дополнительные сведения см. <a href="lync-server-2013-medialist-table.md">в таблице таблица medialist в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ae68e-118">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae68e-119"><strong>медиастарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="ae68e-119"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae68e-120">datetime</span><span class="sxs-lookup"><span data-stu-id="ae68e-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae68e-121">Время отправки запроса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ae68e-121">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae68e-122"><strong>медиаендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="ae68e-122"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae68e-123">datetime</span><span class="sxs-lookup"><span data-stu-id="ae68e-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae68e-124">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="ae68e-124">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

