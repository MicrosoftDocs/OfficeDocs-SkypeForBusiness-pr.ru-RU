---
title: 'Lync Server 2013: сведения о представлении QoE'
description: 'Lync Server 2013: сведения о QoE View.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b20eb083295a5f3d3ecb5be7a8c96d9c4b7cfab2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579105"
---
# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="4e463-103">QoE View Details in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e463-103">QoE view details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e463-104">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4e463-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4e463-105">Представления охватывают наиболее распространенные сценарии возврата данных из базы данных SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="4e463-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="4e463-106">Рекомендуется использовать представления для создания настраиваемых отчетов вместо прямого доступа к таблицам базы данных; Это связано с тем, что представления более вероятнее всего поддерживают обратную совместимость с будущими выпусками.</span><span class="sxs-lookup"><span data-stu-id="4e463-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e463-107">Имя представления</span><span class="sxs-lookup"><span data-stu-id="4e463-107">View Name</span></span></th>
<th><span data-ttu-id="4e463-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4e463-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e463-109"><a href="lync-server-2013-audiostreamdetail-view.md">Представление Аудиостреамдетаил в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4e463-109"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4e463-110">Хранение информации о каждом аудиопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4e463-110">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e463-111"><a href="lync-server-2013-medialine-view.md">Представление MediaLine в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4e463-111"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4e463-112">Хранит сведения о каждой строке носителя в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4e463-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="4e463-113">Один звуковой сеанс обычно содержит одну линию звукового носителя.</span><span class="sxs-lookup"><span data-stu-id="4e463-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="4e463-114">Один сеанс аудио-и видеоданных (A/V) обычно содержит одну линию аудио-и видеоконференций; Однако в этом сеансе могут содержаться две видеолинии, если используется устройство конференц-связи или если используется представление галереи.</span><span class="sxs-lookup"><span data-stu-id="4e463-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e463-115"><a href="lync-server-2013-networkconfigurationsettings-view.md">Представление Нетворкконфигуратионсеттингс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4e463-115"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4e463-116">Хранит сведения о конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="4e463-116">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e463-117"><a href="lync-server-2013-session-view.md">Представление сеанса в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4e463-117"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4e463-118">Хранит информацию о сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4e463-118">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e463-119"><a href="lync-server-2013-useragent-view.md">Представление UserAgent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4e463-119"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4e463-120">Хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4e463-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e463-121"><a href="lync-server-2013-videostreamdetail-view.md">Представление Видеостреамдетаил в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4e463-121"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4e463-122">Хранит информацию о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4e463-122">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

