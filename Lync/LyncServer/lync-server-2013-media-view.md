---
title: 'Lync Server 2013: представление мультимедиа'
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
ms.openlocfilehash: a760e3113cf12eceaa9f60c829b4d6a4a714ea25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="86538-102">Представление мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86538-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86538-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="86538-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="86538-104">В представлении "Мультимедиа" хранятся данные об одном типе мультимедийных данных, используемых в одноранговом сеансе.</span><span class="sxs-lookup"><span data-stu-id="86538-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="86538-105">Один сеанс может быть представлен несколькими записями в таблице, если используется более одного типа мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="86538-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="86538-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86538-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86538-p102">Представление "Мультимедиа" не используется для расчета продолжительности воспроизведения мультимедиа в ходе сеанса. На представлении отображены сведения о сигнале для обмена мультимедиа в рамках сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а значение StartTime определяет время отправки запроса INVITE. Время приглашения может не совпадать с временем начала воспроизведения мультимедиа, поскольку воспроизведение мультимедиа начинается только после подтверждения приема сеанса.</span><span class="sxs-lookup"><span data-stu-id="86538-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="86538-110">Представление мультимедиа содержит все столбцы в [представлении SessionDetails в Lync Server 2013](lync-server-2013-sessiondetails-view.md) , а также перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="86538-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86538-111">Столбец</span><span class="sxs-lookup"><span data-stu-id="86538-111">Column</span></span></th>
<th><span data-ttu-id="86538-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="86538-112">Data Type</span></span></th>
<th><span data-ttu-id="86538-113">Сведения</span><span class="sxs-lookup"><span data-stu-id="86538-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86538-114"><strong>Носитель</strong></span><span class="sxs-lookup"><span data-stu-id="86538-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="86538-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86538-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86538-116">Тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="86538-116">Media type.</span></span> <span data-ttu-id="86538-117">Дополнительные сведения см. <a href="lync-server-2013-medialist-table.md">в таблице таблица medialist в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="86538-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86538-118"><strong>медиастарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="86538-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86538-119">datetime</span><span class="sxs-lookup"><span data-stu-id="86538-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="86538-120">Время отправки запроса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="86538-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86538-121"><strong>медиаендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="86538-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86538-122">datetime</span><span class="sxs-lookup"><span data-stu-id="86538-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="86538-123">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="86538-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

