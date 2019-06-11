---
title: 'Lync Server 2013: представление Клиентверсионс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d219b8666afc0684b0d61f02f06618ea6ef60f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="dad6c-102">Клиентверсионс представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dad6c-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dad6c-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dad6c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dad6c-104">В представлении Клиентверсионс хранятся сведения о различных типах и версиях клиентов, которые принимали участие в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="dad6c-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="dad6c-105">Каждая запись в представлении представляет собой одну версию клиента.</span><span class="sxs-lookup"><span data-stu-id="dad6c-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="dad6c-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dad6c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dad6c-107">Для некоторых столбцов может быть несколько записей.</span><span class="sxs-lookup"><span data-stu-id="dad6c-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dad6c-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="dad6c-108">Column</span></span></th>
<th><span data-ttu-id="dad6c-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="dad6c-109">Data Type</span></span></th>
<th><span data-ttu-id="dad6c-110">Подробности</span><span class="sxs-lookup"><span data-stu-id="dad6c-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dad6c-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="dad6c-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="dad6c-112">целое</span><span class="sxs-lookup"><span data-stu-id="dad6c-112">int</span></span></p></td>
<td><p><span data-ttu-id="dad6c-113">Уникальный номер, показывающий этот тип клиента и версию.</span><span class="sxs-lookup"><span data-stu-id="dad6c-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dad6c-114"><strong>Версия</strong></span><span class="sxs-lookup"><span data-stu-id="dad6c-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="dad6c-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dad6c-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dad6c-116">Представляет агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="dad6c-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dad6c-117"><strong>Клиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="dad6c-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="dad6c-118">целое</span><span class="sxs-lookup"><span data-stu-id="dad6c-118">int</span></span></p></td>
<td><p><span data-ttu-id="dad6c-119">Тип клиента.</span><span class="sxs-lookup"><span data-stu-id="dad6c-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dad6c-120"><strong>Клиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="dad6c-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="dad6c-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="dad6c-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="dad6c-122">Категория, к которой относится клиент.</span><span class="sxs-lookup"><span data-stu-id="dad6c-122">Category that the client belongs to.</span></span> <span data-ttu-id="dad6c-123">Например, клиент КонференЦинг_аттендант_ 1.0 принадлежит к Клиенткатегори Каа.</span><span class="sxs-lookup"><span data-stu-id="dad6c-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

