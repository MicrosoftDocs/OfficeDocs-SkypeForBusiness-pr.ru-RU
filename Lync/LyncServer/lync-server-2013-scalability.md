---
title: 'Lync Server 2013: масштабируемость'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dfdc96934871fd2e73af30507288c734e786cc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="ccf93-102">Масштабируемость с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccf93-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccf93-103">_**Тема последнего изменения:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="ccf93-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="ccf93-104">Lync Server предлагается в двух выпусках, Enterprise Edition и Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ccf93-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="ccf93-105">Различные выпуски предназначены преимущественно для разных размеров организаций.</span><span class="sxs-lookup"><span data-stu-id="ccf93-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="ccf93-106">Как показано в приведенной ниже таблице, оба издания поддерживают все функции во всех рабочих нагрузках, кроме случаев высокой доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="ccf93-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccf93-107">Функция</span><span class="sxs-lookup"><span data-stu-id="ccf93-107">Feature</span></span></th>
<th><span data-ttu-id="ccf93-108">Поддерживается в корпоративном выпуске?</span><span class="sxs-lookup"><span data-stu-id="ccf93-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="ccf93-109">Поддерживается в стандартном выпуске?</span><span class="sxs-lookup"><span data-stu-id="ccf93-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccf93-110">Обмен мгновенными сообщениями и присутствие</span><span class="sxs-lookup"><span data-stu-id="ccf93-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="ccf93-111">Да </span><span class="sxs-lookup"><span data-stu-id="ccf93-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="ccf93-112">Да</span><span class="sxs-lookup"><span data-stu-id="ccf93-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccf93-113">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="ccf93-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="ccf93-114">Да </span><span class="sxs-lookup"><span data-stu-id="ccf93-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="ccf93-115">Да</span><span class="sxs-lookup"><span data-stu-id="ccf93-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccf93-116">A/V conferencing (Аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="ccf93-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="ccf93-117">Да </span><span class="sxs-lookup"><span data-stu-id="ccf93-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="ccf93-118">Да</span><span class="sxs-lookup"><span data-stu-id="ccf93-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccf93-119">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="ccf93-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="ccf93-120">Да </span><span class="sxs-lookup"><span data-stu-id="ccf93-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="ccf93-121">Да</span><span class="sxs-lookup"><span data-stu-id="ccf93-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccf93-122">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="ccf93-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="ccf93-123">Да </span><span class="sxs-lookup"><span data-stu-id="ccf93-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="ccf93-124">Да</span><span class="sxs-lookup"><span data-stu-id="ccf93-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccf93-125">Виртуализаци</span><span class="sxs-lookup"><span data-stu-id="ccf93-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="ccf93-126">Да </span><span class="sxs-lookup"><span data-stu-id="ccf93-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="ccf93-127">Да</span><span class="sxs-lookup"><span data-stu-id="ccf93-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccf93-128">Высокий уровень доступности, отказов и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="ccf93-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="ccf93-129">Да</span><span class="sxs-lookup"><span data-stu-id="ccf93-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="ccf93-130">Нет</span><span class="sxs-lookup"><span data-stu-id="ccf93-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

