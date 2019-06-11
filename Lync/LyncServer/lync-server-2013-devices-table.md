---
title: 'Lync Server 2013: таблица Devices'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="6a2dd-102">Таблица Devices в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a2dd-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a2dd-103">_**Тема последнего изменения:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="6a2dd-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="6a2dd-104">Таблица "устройства" является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="6a2dd-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="6a2dd-105">Каждая запись хранит информацию об одном устройстве (стационарном телефоне).</span><span class="sxs-lookup"><span data-stu-id="6a2dd-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a2dd-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="6a2dd-106">Column</span></span></th>
<th><span data-ttu-id="6a2dd-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6a2dd-107">Data Type</span></span></th>
<th><span data-ttu-id="6a2dd-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="6a2dd-108">Key/Index</span></span></th>
<th><span data-ttu-id="6a2dd-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="6a2dd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a2dd-110"><strong>Устройства</strong></span><span class="sxs-lookup"><span data-stu-id="6a2dd-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2dd-111">целое</span><span class="sxs-lookup"><span data-stu-id="6a2dd-111">int</span></span></p></td>
<td><p><span data-ttu-id="6a2dd-112">Primary</span><span class="sxs-lookup"><span data-stu-id="6a2dd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6a2dd-113">Уникальный номер, идентифицирующий эту аппаратную версию.</span><span class="sxs-lookup"><span data-stu-id="6a2dd-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a2dd-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="6a2dd-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2dd-115">целое</span><span class="sxs-lookup"><span data-stu-id="6a2dd-115">int</span></span></p></td>
<td><p><span data-ttu-id="6a2dd-116">Другом</span><span class="sxs-lookup"><span data-stu-id="6a2dd-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2dd-117">Производитель этого устройства.</span><span class="sxs-lookup"><span data-stu-id="6a2dd-117">Manufacturer of this device.</span></span> <span data-ttu-id="6a2dd-118">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-manufacturers-table.md">таблицей изготовителей в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2dd-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a2dd-119"><strong>Хардвареверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="6a2dd-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2dd-120">целое</span><span class="sxs-lookup"><span data-stu-id="6a2dd-120">int</span></span></p></td>
<td><p><span data-ttu-id="6a2dd-121">Другом</span><span class="sxs-lookup"><span data-stu-id="6a2dd-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6a2dd-122">Аппаратная версия этого устройства.</span><span class="sxs-lookup"><span data-stu-id="6a2dd-122">Hardware version of this device.</span></span> <span data-ttu-id="6a2dd-123">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-hardwareversions-table.md">таблицей хардвареверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6a2dd-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a2dd-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="6a2dd-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="6a2dd-125">bigint</span><span class="sxs-lookup"><span data-stu-id="6a2dd-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6a2dd-126">MAC-адрес</span><span class="sxs-lookup"><span data-stu-id="6a2dd-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

