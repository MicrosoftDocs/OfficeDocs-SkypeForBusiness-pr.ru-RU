---
title: 'Lync Server 2013: представление Таблица conferencemessagecount'
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
ms.openlocfilehash: bdba6750a24e9bc46629f4a3d264893d014f68e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="45358-102">Представление Таблица conferencemessagecount в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45358-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45358-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="45358-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="45358-104">В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции.</span><span class="sxs-lookup"><span data-stu-id="45358-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="45358-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45358-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45358-106">В представлении Таблица conferencemessagecount содержатся все столбцы в <A href="lync-server-2013-conferencesessiondetails-view.md">представлении Таблица conferencesessiondetails в Lync Server 2013</A> , а также столбцы, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="45358-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45358-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="45358-107">Column</span></span></th>
<th><span data-ttu-id="45358-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="45358-108">Data Type</span></span></th>
<th><span data-ttu-id="45358-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="45358-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45358-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="45358-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="45358-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="45358-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="45358-112">URI пользователя, отправившего сообщение.</span><span class="sxs-lookup"><span data-stu-id="45358-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45358-113"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="45358-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="45358-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="45358-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45358-115">Тип URI пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="45358-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="45358-116">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="45358-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45358-117"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="45358-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="45358-118">идентификатора</span><span class="sxs-lookup"><span data-stu-id="45358-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="45358-119">Клиент пользователя, отправившего сообщения.</span><span class="sxs-lookup"><span data-stu-id="45358-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="45358-120">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="45358-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45358-121"><strong>усермессажекаунт</strong></span><span class="sxs-lookup"><span data-stu-id="45358-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="45358-122">smallint</span><span class="sxs-lookup"><span data-stu-id="45358-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="45358-123">Количество сообщений, отправленных пользователем во время сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="45358-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

