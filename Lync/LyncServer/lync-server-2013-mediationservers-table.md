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
ms.openlocfilehash: 07fd3905fcf6876af270cdab437691edb68cff98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513676"
---
# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="42320-102">Таблица Таблица mediationservers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42320-102">MediationServers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42320-103">_**Последнее изменение темы:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="42320-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="42320-104">Таблица Таблица mediationservers является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="42320-104">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="42320-105">Каждая запись содержит сведения об одном сервере-посреднике, участвующем в вызовах, содержащих записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="42320-105">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42320-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="42320-106">Column</span></span></th>
<th><span data-ttu-id="42320-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="42320-107">Data Type</span></span></th>
<th><span data-ttu-id="42320-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="42320-108">Key/Index</span></span></th>
<th><span data-ttu-id="42320-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="42320-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42320-110"><strong>медиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="42320-110"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42320-111">int</span><span class="sxs-lookup"><span data-stu-id="42320-111">int</span></span></p></td>
<td><p><span data-ttu-id="42320-112">Primary</span><span class="sxs-lookup"><span data-stu-id="42320-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="42320-113">Уникальный номер, идентифицирующий сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="42320-113">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42320-114"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="42320-114"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="42320-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42320-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="42320-116">Имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="42320-116">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

