---
title: 'Lync Server 2013: представление Таблица clientversions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06e250528a56c10a573c19181fddb1d9acee494d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499166"
---
# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="e8f80-102">Представление Таблица clientversions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8f80-102">ClientVersions view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8f80-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e8f80-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e8f80-104">В представлении ClientVersions сохраняются сведения о различных типах клиентов и версиях, которые участвовали в сеансах, зарегистрированных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e8f80-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e8f80-105">Каждая запись в этом представлении относится к одной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="e8f80-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="e8f80-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8f80-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8f80-107">Возможно наличие нескольких записей для определенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="e8f80-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8f80-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="e8f80-108">Column</span></span></th>
<th><span data-ttu-id="e8f80-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e8f80-109">Data Type</span></span></th>
<th><span data-ttu-id="e8f80-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="e8f80-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8f80-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="e8f80-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8f80-112">int</span><span class="sxs-lookup"><span data-stu-id="e8f80-112">int</span></span></p></td>
<td><p><span data-ttu-id="e8f80-113">Уникальный номер, идентифицирующий данный тип клиента и его версию.</span><span class="sxs-lookup"><span data-stu-id="e8f80-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f80-114"><strong>Версия</strong></span><span class="sxs-lookup"><span data-stu-id="e8f80-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="e8f80-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e8f80-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e8f80-116">Служит для указания агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="e8f80-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8f80-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e8f80-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e8f80-118">int</span><span class="sxs-lookup"><span data-stu-id="e8f80-118">int</span></span></p></td>
<td><p><span data-ttu-id="e8f80-119">Тип клиента.</span><span class="sxs-lookup"><span data-stu-id="e8f80-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8f80-120"><strong>клиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="e8f80-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e8f80-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e8f80-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e8f80-p102">Категория, к которой относится клиент. Например, клиент Conferencing_Attendant_1.0 относится к категории ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="e8f80-p102">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

