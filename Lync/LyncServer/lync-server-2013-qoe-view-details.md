---
title: 'Lync Server 2013: сведения о представлении QoE'
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
ms.openlocfilehash: 6bba917427e42dcba689d3b248c7d889c798368f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512166"
---
# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="cf288-102">QoE View Details in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf288-102">QoE view details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf288-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="cf288-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="cf288-104">Представления охватывают наиболее распространенные сценарии возврата данных из базы данных SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="cf288-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="cf288-105">Рекомендуется использовать представления для создания настраиваемых отчетов вместо прямого доступа к таблицам базы данных; Это связано с тем, что представления более вероятнее всего поддерживают обратную совместимость с будущими выпусками.</span><span class="sxs-lookup"><span data-stu-id="cf288-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf288-106">Имя представления</span><span class="sxs-lookup"><span data-stu-id="cf288-106">View Name</span></span></th>
<th><span data-ttu-id="cf288-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cf288-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf288-108"><a href="lync-server-2013-audiostreamdetail-view.md">Представление Аудиостреамдетаил в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf288-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cf288-109">Хранение информации о каждом аудиопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cf288-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf288-110"><a href="lync-server-2013-medialine-view.md">Представление MediaLine в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf288-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cf288-111">Хранит сведения о каждой строке носителя в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cf288-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="cf288-112">Один звуковой сеанс обычно содержит одну линию звукового носителя.</span><span class="sxs-lookup"><span data-stu-id="cf288-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="cf288-113">Один сеанс аудио-и видеоданных (A/V) обычно содержит одну линию аудио-и видеоконференций; Однако в этом сеансе могут содержаться две видеолинии, если используется устройство конференц-связи или если используется представление галереи.</span><span class="sxs-lookup"><span data-stu-id="cf288-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf288-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Представление Нетворкконфигуратионсеттингс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf288-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cf288-115">Хранит сведения о конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="cf288-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf288-116"><a href="lync-server-2013-session-view.md">Представление сеанса в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf288-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cf288-117">Хранит информацию о сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cf288-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf288-118"><a href="lync-server-2013-useragent-view.md">Представление UserAgent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf288-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cf288-119">Хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cf288-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf288-120"><a href="lync-server-2013-videostreamdetail-view.md">Представление Видеостреамдетаил в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf288-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cf288-121">Хранит информацию о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cf288-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

