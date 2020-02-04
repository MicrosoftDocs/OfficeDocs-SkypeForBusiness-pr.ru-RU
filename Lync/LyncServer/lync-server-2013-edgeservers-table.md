---
title: 'Lync Server 2013: таблица EdgeServers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EdgeServers table
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412833(v=OCS.15)
ms:contentKeyID: 48185081
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 199aadf836547ff23277374c8bd4b338b3ef5a66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edgeservers-table-in-lync-server-2013"></a><span data-ttu-id="0cafc-102">Таблица EdgeServers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cafc-102">EdgeServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cafc-103">_**Тема последнего изменения:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="0cafc-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="0cafc-104">Таблица Еджесерверс является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="0cafc-104">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="0cafc-105">Каждая запись содержит сведения о одном пограничном сервере, который участвует в звонках, которые содержат записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0cafc-105">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cafc-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="0cafc-106">Column</span></span></th>
<th><span data-ttu-id="0cafc-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0cafc-107">Data Type</span></span></th>
<th><span data-ttu-id="0cafc-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="0cafc-108">Key/Index</span></span></th>
<th><span data-ttu-id="0cafc-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="0cafc-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cafc-110"><strong>еджесерверид</strong></span><span class="sxs-lookup"><span data-stu-id="0cafc-110"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0cafc-111">целое</span><span class="sxs-lookup"><span data-stu-id="0cafc-111">int</span></span></p></td>
<td><p><span data-ttu-id="0cafc-112">Primary</span><span class="sxs-lookup"><span data-stu-id="0cafc-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0cafc-113">Уникальный номер, идентифицирующий этот сервер пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0cafc-113">Unique number identifying this Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cafc-114"><strong>Пограничный сервер</strong></span><span class="sxs-lookup"><span data-stu-id="0cafc-114"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="0cafc-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cafc-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0cafc-116">Имя пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0cafc-116">Edge Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

