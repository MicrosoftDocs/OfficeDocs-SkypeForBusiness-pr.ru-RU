---
title: 'Lync Server 2013: представление Конференцемессажекаунт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73944e1561b88301b740fcb52cf301645154c6e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="981b1-102">Конференцемессажекаунт представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="981b1-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="981b1-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="981b1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="981b1-104">В представлении Конференцемессажекаунт хранятся сведения о количестве сообщений, отправленных пользователем на конференцию.</span><span class="sxs-lookup"><span data-stu-id="981b1-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="981b1-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="981b1-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="981b1-106">В представлении Конференцемессажекаунт содержатся все столбцы в <A href="lync-server-2013-conferencesessiondetails-view.md">представлении конференцесессиондетаилс в Lync Server 2013</A> в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="981b1-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="981b1-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="981b1-107">Column</span></span></th>
<th><span data-ttu-id="981b1-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="981b1-108">Data Type</span></span></th>
<th><span data-ttu-id="981b1-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="981b1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="981b1-110"><strong>усерури</strong></span><span class="sxs-lookup"><span data-stu-id="981b1-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="981b1-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="981b1-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="981b1-112">Универсальный код ресурса (URI) пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="981b1-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="981b1-113"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="981b1-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="981b1-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="981b1-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="981b1-115">Тип URI пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="981b1-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="981b1-116">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="981b1-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="981b1-117"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="981b1-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="981b1-118">идентификатора</span><span class="sxs-lookup"><span data-stu-id="981b1-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="981b1-119">Клиент пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="981b1-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="981b1-120">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="981b1-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="981b1-121"><strong>усермессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="981b1-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="981b1-122">smallint</span><span class="sxs-lookup"><span data-stu-id="981b1-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="981b1-123">Количество сообщений, отправленных пользователем во время сеанса конференции.</span><span class="sxs-lookup"><span data-stu-id="981b1-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

