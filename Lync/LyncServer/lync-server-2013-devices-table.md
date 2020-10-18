---
title: 'Lync Server 2013: таблица Devices'
description: 'Lync Server 2013: таблица Devices.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763e1788e2874f9f9831c089ffe8fa077621b030
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576245"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="8f144-103">Таблица Devices в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f144-103">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f144-104">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="8f144-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="8f144-p101">Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="8f144-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f144-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="8f144-107">Column</span></span></th>
<th><span data-ttu-id="8f144-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8f144-108">Data Type</span></span></th>
<th><span data-ttu-id="8f144-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="8f144-109">Key/Index</span></span></th>
<th><span data-ttu-id="8f144-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="8f144-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f144-111"><strong>Устройства</strong></span><span class="sxs-lookup"><span data-stu-id="8f144-111"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f144-112">int</span><span class="sxs-lookup"><span data-stu-id="8f144-112">int</span></span></p></td>
<td><p><span data-ttu-id="8f144-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8f144-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="8f144-114">Уникальный номер, идентифицирующий версию оборудования.</span><span class="sxs-lookup"><span data-stu-id="8f144-114">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f144-115"><strong>мануфактурерид</strong></span><span class="sxs-lookup"><span data-stu-id="8f144-115"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f144-116">int</span><span class="sxs-lookup"><span data-stu-id="8f144-116">int</span></span></p></td>
<td><p><span data-ttu-id="8f144-117">Правительства</span><span class="sxs-lookup"><span data-stu-id="8f144-117">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f144-118">Производитель этого устройства.</span><span class="sxs-lookup"><span data-stu-id="8f144-118">Manufacturer of this device.</span></span> <span data-ttu-id="8f144-119">Для получения дополнительных сведений ознакомьтесь со статьей <a href="lync-server-2013-manufacturers-table.md">Таблица производители в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8f144-119">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f144-120"><strong>хардвареверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="8f144-120"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f144-121">int</span><span class="sxs-lookup"><span data-stu-id="8f144-121">int</span></span></p></td>
<td><p><span data-ttu-id="8f144-122">Правительства</span><span class="sxs-lookup"><span data-stu-id="8f144-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f144-123">Версия оборудования этого устройства.</span><span class="sxs-lookup"><span data-stu-id="8f144-123">Hardware version of this device.</span></span> <span data-ttu-id="8f144-124">Дополнительные сведения см. <a href="lync-server-2013-hardwareversions-table.md">в таблице таблица hardwareversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8f144-124">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f144-125"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="8f144-125"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="8f144-126">типу</span><span class="sxs-lookup"><span data-stu-id="8f144-126">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f144-127">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="8f144-127">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

