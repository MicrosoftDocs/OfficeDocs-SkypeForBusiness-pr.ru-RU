---
title: Масштабируемость Lync Server 2013
description: Масштабируемость Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543795"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="1ac49-103">Масштабируемость с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ac49-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ac49-104">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="1ac49-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="1ac49-105">Lync Server предлагается в двух выпусках: Enterprise Edition и Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1ac49-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="1ac49-106">Разные выпуски в основном предназначаются для разных размеров организаций.</span><span class="sxs-lookup"><span data-stu-id="1ac49-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="1ac49-107">Как показано в следующей таблице, оба выпуска поддерживают все функциональные возможности при любых рабочих нагрузках, за исключением высокого уровня доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1ac49-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ac49-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="1ac49-108">Feature</span></span></th>
<th><span data-ttu-id="1ac49-109">Поддерживается в Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="1ac49-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="1ac49-110">Поддерживается в Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="1ac49-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ac49-111">Обмен мгновенными сообщениями и функция присутствия</span><span class="sxs-lookup"><span data-stu-id="1ac49-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="1ac49-112">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ac49-113">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ac49-114">Конференции</span><span class="sxs-lookup"><span data-stu-id="1ac49-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="1ac49-115">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ac49-116">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ac49-117">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="1ac49-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="1ac49-118">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ac49-119">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ac49-120">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="1ac49-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="1ac49-121">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ac49-122">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ac49-123">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="1ac49-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="1ac49-124">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ac49-125">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ac49-126">Виртуализация</span><span class="sxs-lookup"><span data-stu-id="1ac49-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="1ac49-127">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ac49-128">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ac49-129">Высокий уровень доступности, отработка отказа, аварийное восстановление</span><span class="sxs-lookup"><span data-stu-id="1ac49-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="1ac49-130">Да</span><span class="sxs-lookup"><span data-stu-id="1ac49-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ac49-131">Нет</span><span class="sxs-lookup"><span data-stu-id="1ac49-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

