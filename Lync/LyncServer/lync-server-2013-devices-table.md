---
title: 'Lync Server 2013: таблица Devices'
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
ms.openlocfilehash: 1270557e5d02fd1764957d75441ecc33ad11588c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="f0be4-102">Таблица Devices в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0be4-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0be4-103">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="f0be4-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="f0be4-p101">Таблица устройств является вспомогательной. В каждой записи хранится информация об одном устройстве (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="f0be4-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0be4-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="f0be4-106">Column</span></span></th>
<th><span data-ttu-id="f0be4-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f0be4-107">Data Type</span></span></th>
<th><span data-ttu-id="f0be4-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="f0be4-108">Key/Index</span></span></th>
<th><span data-ttu-id="f0be4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="f0be4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0be4-110"><strong>Устройства</strong></span><span class="sxs-lookup"><span data-stu-id="f0be4-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0be4-111">int</span><span class="sxs-lookup"><span data-stu-id="f0be4-111">int</span></span></p></td>
<td><p><span data-ttu-id="f0be4-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f0be4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0be4-113">Уникальный номер, идентифицирующий версию оборудования.</span><span class="sxs-lookup"><span data-stu-id="f0be4-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0be4-114"><strong>мануфактурерид</strong></span><span class="sxs-lookup"><span data-stu-id="f0be4-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0be4-115">int</span><span class="sxs-lookup"><span data-stu-id="f0be4-115">int</span></span></p></td>
<td><p><span data-ttu-id="f0be4-116">Правительства</span><span class="sxs-lookup"><span data-stu-id="f0be4-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0be4-117">Производитель этого устройства.</span><span class="sxs-lookup"><span data-stu-id="f0be4-117">Manufacturer of this device.</span></span> <span data-ttu-id="f0be4-118">Для получения дополнительных сведений ознакомьтесь со статьей <a href="lync-server-2013-manufacturers-table.md">Таблица производители в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f0be4-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0be4-119"><strong>хардвареверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="f0be4-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0be4-120">int</span><span class="sxs-lookup"><span data-stu-id="f0be4-120">int</span></span></p></td>
<td><p><span data-ttu-id="f0be4-121">Правительства</span><span class="sxs-lookup"><span data-stu-id="f0be4-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0be4-122">Версия оборудования этого устройства.</span><span class="sxs-lookup"><span data-stu-id="f0be4-122">Hardware version of this device.</span></span> <span data-ttu-id="f0be4-123">Дополнительные сведения см. <a href="lync-server-2013-hardwareversions-table.md">в таблице таблица hardwareversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f0be4-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0be4-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f0be4-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f0be4-125">типу</span><span class="sxs-lookup"><span data-stu-id="f0be4-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0be4-126">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="f0be4-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

