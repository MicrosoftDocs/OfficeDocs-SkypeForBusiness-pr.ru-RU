---
title: 'Lync Server 2013: список представлений CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb29608b7048e1896a731a64ee644213f513ebaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="5ebcc-102">Список представлений CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ebcc-102">List of CDR views in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ebcc-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5ebcc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5ebcc-104">Представления позволяют легко получить доступ к сведениям посредством наиболее распространенных сценариев извлечения данных из базы данных записей о звонках (CDR).</span><span class="sxs-lookup"><span data-stu-id="5ebcc-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="5ebcc-105">Рекомендуется использовать представления для создания настраиваемых отчетов, а не таблиц базы данных CDR; Это связано с тем, что представления базы данных чаще всего поддерживают обратную совместимость с будущими выпусками Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ebcc-106">Имя представления</span><span class="sxs-lookup"><span data-stu-id="5ebcc-106">View Name</span></span></th>
<th><span data-ttu-id="5ebcc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5ebcc-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ebcc-108"><a href="lync-server-2013-clientversions-view.md">Представление Таблица clientversions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-109">Возвращает сведения о программном обеспечении и устройствах клиента, которые используются в сеансах связи.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ebcc-110"><a href="lync-server-2013-conferencemessagecount-view.md">Представление Таблица conferencemessagecount в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-111">Возвращает сведения о количестве сообщений, отправленных пользователями на конференции.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ebcc-112"><a href="lync-server-2013-conferences-view.md">Представление конференций в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-113">Возвращает сведения о конференции, включая время начала, время окончания и инициатора конференции.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ebcc-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Представление Таблица conferencesessiondetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-115">Возвращает сведения о сеансе для всех сеансов конференц-связи, включая время начала и окончания, идентификаторы пользователей, коды ответа и диагностические идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ebcc-116"><a href="lync-server-2013-conferenceuris-view.md">Представление Таблица conferenceuris в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-117">Возвращает сведения о кодах URI, используемых в конференции</span><span class="sxs-lookup"><span data-stu-id="5ebcc-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ebcc-118"><a href="lync-server-2013-errorreport-view.md">Представление ErrorReport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-119">Возвращает сведения об ошибках, возникших во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ebcc-120"><a href="lync-server-2013-filetransfers-view.md">Представление Таблица filetransfers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-121">Возвращает сведения о сеансах с передачей файлов, включая имя файла и сведения о том, была ли передача принята, отклонена или отменена.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ebcc-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Представление Таблица focusjoinsandleaves в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-123">Возвращает сведения о действиях по присоединению к конференции и выходу из нее.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ebcc-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Представление Таблица mcujoinsandleaves в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-125">Возвращает объединенные сведения о действиях по присоединению к конференции и выходу из нее (каждое присоединение к конференции сопоставляется с соответствующим выходом из конференции).</span><span class="sxs-lookup"><span data-stu-id="5ebcc-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ebcc-126"><a href="lync-server-2013-mcus-view.md">Представление MCUs в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-127">Возвращает сведения о серверах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ebcc-128"><a href="lync-server-2013-media-view.md">Представление мультимедиа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-129">Возвращает сведения о типах мультимедиа, используемых в одноранговых сеансах связи.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ebcc-130"><a href="lync-server-2013-progressreport-view.md">Представление Таблица progressreport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-131">Возвращает сведения о завершенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ebcc-132"><a href="lync-server-2013-registration-view.md">Представление регистрации в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-133">Возвращает сведения о регистрациях в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ebcc-134"><a href="lync-server-2013-sessiondetails-view.md">Представление SessionDetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-135">Возвращает сведения об одноранговых сеансах, включающих телефонные звонки VoIP-VoIP, двусторонние сеансы обмена мгновенными сообщениями или другие одноранговые сеансы связи.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ebcc-136"><a href="lync-server-2013-user-view.md">Пользовательское представление в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-137">Возвращает сведения о пользователях, которые участвовали в сеансах связи.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ebcc-138"><a href="lync-server-2013-voipdetails-view.md">Представление Таблица voipdetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ebcc-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ebcc-139">Возвращает сведения об одноранговых сеансах как минимум с одним пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="5ebcc-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

