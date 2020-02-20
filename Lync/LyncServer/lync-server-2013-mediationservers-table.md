---
title: 'Lync Server 2013: таблица таблица mediationservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5d8e9b1538608609137f5bfd00b18ed0452fea7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="97fcd-102">Таблица Таблица mediationservers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97fcd-102">MediationServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97fcd-103">_**Последнее изменение темы:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="97fcd-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="97fcd-104">Таблица Таблица mediationservers является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="97fcd-104">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="97fcd-105">Каждая запись содержит сведения об одном сервере-посреднике, участвующем в вызовах, содержащих записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="97fcd-105">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97fcd-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="97fcd-106">Column</span></span></th>
<th><span data-ttu-id="97fcd-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="97fcd-107">Data Type</span></span></th>
<th><span data-ttu-id="97fcd-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="97fcd-108">Key/Index</span></span></th>
<th><span data-ttu-id="97fcd-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="97fcd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97fcd-110"><strong>медиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="97fcd-110"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="97fcd-111">int</span><span class="sxs-lookup"><span data-stu-id="97fcd-111">int</span></span></p></td>
<td><p><span data-ttu-id="97fcd-112">Primary</span><span class="sxs-lookup"><span data-stu-id="97fcd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="97fcd-113">Уникальный номер, идентифицирующий сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="97fcd-113">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97fcd-114"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="97fcd-114"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="97fcd-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="97fcd-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97fcd-116">Имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="97fcd-116">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

