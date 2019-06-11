---
title: 'Lync Server 2013: список представлений CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112e565c07c685c1ecdf5db1d8a2de8717ba959e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="20a41-102">Список представлений CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20a41-102">List of CDR views in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20a41-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="20a41-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="20a41-104">Представления предоставляют простой способ получить доступ к сведениям о наиболее распространенных сценариях, используемых для возврата данных из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="20a41-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="20a41-105">Рекомендуется использовать представления для создания настраиваемых отчетов вместо использования таблиц баз данных реальных CDR; Это связано с тем, что представления базы данных более удобны для обеспечения обратной совместимости с будущими выпусками Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20a41-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20a41-106">Имя представления</span><span class="sxs-lookup"><span data-stu-id="20a41-106">View Name</span></span></th>
<th><span data-ttu-id="20a41-107">Описание</span><span class="sxs-lookup"><span data-stu-id="20a41-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20a41-108"><a href="lync-server-2013-clientversions-view.md">Клиентверсионс представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-109">Возвращает сведения о клиентском программном обеспечении и устройствах, используемых в сеансе связи.</span><span class="sxs-lookup"><span data-stu-id="20a41-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a41-110"><a href="lync-server-2013-conferencemessagecount-view.md">Конференцемессажекаунт представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-111">Возвращает сведения о количестве сообщений, отправленных пользователями на Конференции.</span><span class="sxs-lookup"><span data-stu-id="20a41-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a41-112"><a href="lync-server-2013-conferences-view.md">Представление "Конференции" в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-113">Возвращает сведения о конференции, в том числе время начала, время окончания и организатора конференции.</span><span class="sxs-lookup"><span data-stu-id="20a41-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a41-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Конференцесессиондетаилс представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-115">Возвращает сведения о сеансе для всех сеансов конференц-связи, в том числе время начала и окончания, идентификаторы пользователей, коды ответа и диагностические идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="20a41-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a41-116"><a href="lync-server-2013-conferenceuris-view.md">Конференцеурис представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-117">Возвращает сведения о URI конференций, используемых на Конференции.</span><span class="sxs-lookup"><span data-stu-id="20a41-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a41-118"><a href="lync-server-2013-errorreport-view.md">Ерроррепорт представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-119">Возвращает сведения об ошибках, произошедших во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="20a41-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a41-120"><a href="lync-server-2013-filetransfers-view.md">Филетрансферс представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-121">Возвращает сведения о сеансах передачи файлов, в том числе имя файла и о том, были ли данные приняты, отклонены или отменены.</span><span class="sxs-lookup"><span data-stu-id="20a41-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a41-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Фокусжоинсандлеавес представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-123">Возвращает сведения о присоединении к Конференции и оставлении действий.</span><span class="sxs-lookup"><span data-stu-id="20a41-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a41-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Мкужоинсандлеавес представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-125">Возвращает объединенные сведения о присоединениях к Конференции и оставлении действий (каждое присоединение к Конференции сопоставлено с выходом на соответствующую конференцию).</span><span class="sxs-lookup"><span data-stu-id="20a41-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a41-126"><a href="lync-server-2013-mcus-view.md">Мкус представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-127">Возвращает сведения о серверах конференций.</span><span class="sxs-lookup"><span data-stu-id="20a41-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a41-128"><a href="lync-server-2013-media-view.md">Представление мультимедиа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-129">Возвращает сведения о типах мультимедиа, используемых в одноранговых сеансах связи.</span><span class="sxs-lookup"><span data-stu-id="20a41-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a41-130"><a href="lync-server-2013-progressreport-view.md">Прогрессрепорт представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-131">Возвращает сведения о завершенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="20a41-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a41-132"><a href="lync-server-2013-registration-view.md">Представление регистрации в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-133">Возвращает сведения о регистрациях с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20a41-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a41-134"><a href="lync-server-2013-sessiondetails-view.md">Сессиондетаилс представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-135">Возвращает сведения о одноранговых сеансах, включая VoIP-звонки по телефонным каналам, два сеанса обмена мгновенными сообщениями и другие одноранговые сеансы связи.</span><span class="sxs-lookup"><span data-stu-id="20a41-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a41-136"><a href="lync-server-2013-user-view.md">Представление пользователя в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-137">Возвращает сведения о пользователях, участвующих в сеансах связи.</span><span class="sxs-lookup"><span data-stu-id="20a41-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a41-138"><a href="lync-server-2013-voipdetails-view.md">Воипдетаилс представления в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="20a41-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="20a41-139">Возвращает сведения о одноранговых сеансах с участием по крайней мере одного пользователя VoIP (с голосовым вводом-выводом).</span><span class="sxs-lookup"><span data-stu-id="20a41-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

