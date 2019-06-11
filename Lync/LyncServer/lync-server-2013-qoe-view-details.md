---
title: 'Lync Server 2013: сведения о просмотре QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e223ff2adee63eb8e13304e4df6db519e85014f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="cb1b3-102">QoE просмотра данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb1b3-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb1b3-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="cb1b3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="cb1b3-104">В представлениях рассматриваются наиболее распространенные сценарии возврата данных из базы данных SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="cb1b3-105">Рекомендуется использовать представления для создания настраиваемых отчетов вместо прямого доступа к таблицам базы данных; Это связано с тем, что представления более удобны для обеспечения обратной совместимости с будущими выпусками.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb1b3-106">Имя представления</span><span class="sxs-lookup"><span data-stu-id="cb1b3-106">View Name</span></span></th>
<th><span data-ttu-id="cb1b3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cb1b3-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb1b3-108"><a href="lync-server-2013-audiostreamdetail-view.md">Аудиостреамдетаил представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb1b3-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb1b3-109">Хранит сведения о каждом звуковом потоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb1b3-110"><a href="lync-server-2013-medialine-view.md">Медиалине представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb1b3-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb1b3-111">Хранит сведения о каждой строке мультимедиа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="cb1b3-112">Один звуковой сеанс обычно состоит из одной линии звукового файла.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="cb1b3-113">Один из звуковых и видеофайлов (A/V) обычно состоит из одной линии звукового файла и одной линии видеоклипа; Тем не менее, в этом сеансе могут содержаться две строки видеофайла, если используется устройство конференц-связи или если используется представление коллекции.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb1b3-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Нетворкконфигуратионсеттингс представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb1b3-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb1b3-115">Хранит сведения о конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb1b3-116"><a href="lync-server-2013-session-view.md">Представление сеанса в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb1b3-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb1b3-117">Хранит сведения о сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb1b3-118"><a href="lync-server-2013-useragent-view.md">Представление "UserAgent" в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb1b3-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb1b3-119">Хранит сведения об агентах пользователей, вовлеченных в сеансы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb1b3-120"><a href="lync-server-2013-videostreamdetail-view.md">Видеостреамдетаил представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb1b3-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb1b3-121">Хранит сведения о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb1b3-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

