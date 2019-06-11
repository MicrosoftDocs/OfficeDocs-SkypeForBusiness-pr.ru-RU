---
title: 'Lync Server 2013: представление Конференцемессажекаунт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0324c9913a607057c4e1cd161a9040b83d6bd29b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="f02c0-102">Конференцемессажекаунт представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f02c0-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f02c0-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f02c0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f02c0-104">В представлении Конференцемессажекаунт хранятся сведения о количестве сообщений, отправленных пользователем на конференцию.</span><span class="sxs-lookup"><span data-stu-id="f02c0-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="f02c0-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f02c0-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f02c0-106">В представлении Конференцемессажекаунт содержатся все столбцы в <A href="lync-server-2013-conferencesessiondetails-view.md">представлении конференцесессиондетаилс в Lync Server 2013</A> в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="f02c0-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f02c0-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="f02c0-107">Column</span></span></th>
<th><span data-ttu-id="f02c0-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f02c0-108">Data Type</span></span></th>
<th><span data-ttu-id="f02c0-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="f02c0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f02c0-110"><strong>Усерури</strong></span><span class="sxs-lookup"><span data-stu-id="f02c0-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f02c0-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f02c0-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f02c0-112">Универсальный код ресурса (URI) пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="f02c0-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f02c0-113"><strong>Усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="f02c0-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f02c0-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f02c0-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f02c0-115">Тип URI пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="f02c0-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="f02c0-116">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f02c0-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f02c0-117"><strong>Усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="f02c0-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f02c0-118">идентификатора</span><span class="sxs-lookup"><span data-stu-id="f02c0-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f02c0-119">Клиент пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="f02c0-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="f02c0-120">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f02c0-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f02c0-121"><strong>Усермессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="f02c0-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f02c0-122">smallint</span><span class="sxs-lookup"><span data-stu-id="f02c0-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="f02c0-123">Количество сообщений, отправленных пользователем во время сеанса конференции.</span><span class="sxs-lookup"><span data-stu-id="f02c0-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

