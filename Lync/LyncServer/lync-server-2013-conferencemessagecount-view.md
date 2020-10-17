---
title: 'Lync Server 2013: представление Таблица conferencemessagecount'
description: 'Lync Server 2013: представление Таблица conferencemessagecount.'
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
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561615"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="cdb69-103">Представление Таблица conferencemessagecount в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdb69-103">ConferenceMessageCount view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdb69-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cdb69-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cdb69-105">В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции.</span><span class="sxs-lookup"><span data-stu-id="cdb69-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="cdb69-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdb69-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cdb69-107">В представлении Таблица conferencemessagecount содержатся все столбцы в <A href="lync-server-2013-conferencesessiondetails-view.md">представлении Таблица conferencesessiondetails в Lync Server 2013</A> , а также столбцы, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="cdb69-107">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdb69-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="cdb69-108">Column</span></span></th>
<th><span data-ttu-id="cdb69-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="cdb69-109">Data Type</span></span></th>
<th><span data-ttu-id="cdb69-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="cdb69-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdb69-111"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="cdb69-111"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb69-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cdb69-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cdb69-113">URI пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="cdb69-113">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdb69-114"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="cdb69-114"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb69-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cdb69-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cdb69-116">Тип URI пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="cdb69-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="cdb69-117">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cdb69-117">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdb69-118"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="cdb69-118"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb69-119">идентификатора</span><span class="sxs-lookup"><span data-stu-id="cdb69-119">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="cdb69-120">Клиент пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="cdb69-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="cdb69-121">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cdb69-121">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdb69-122"><strong>усермессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="cdb69-122"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="cdb69-123">smallint</span><span class="sxs-lookup"><span data-stu-id="cdb69-123">smallint</span></span></p></td>
<td><p><span data-ttu-id="cdb69-124">Количество сообщений, отправленных пользователем во время сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="cdb69-124">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

