---
title: Масштабируемость Lync Server 2013
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
ms.openlocfilehash: 130b1958b418aa2b09e572f137598487dc2c3401
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="12485-102">Масштабируемость с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12485-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12485-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="12485-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="12485-104">Lync Server предлагается в двух выпусках: Enterprise Edition и Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12485-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="12485-105">Разные выпуски в основном предназначаются для разных размеров организаций.</span><span class="sxs-lookup"><span data-stu-id="12485-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="12485-106">Как показано в следующей таблице, оба выпуска поддерживают все функциональные возможности при любых рабочих нагрузках, за исключением высокого уровня доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="12485-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12485-107">Функция</span><span class="sxs-lookup"><span data-stu-id="12485-107">Feature</span></span></th>
<th><span data-ttu-id="12485-108">Поддерживается в Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="12485-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="12485-109">Поддерживается в Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="12485-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12485-110">Обмен мгновенными сообщениями и функция присутствия</span><span class="sxs-lookup"><span data-stu-id="12485-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="12485-111">Да</span><span class="sxs-lookup"><span data-stu-id="12485-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="12485-112">Да</span><span class="sxs-lookup"><span data-stu-id="12485-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12485-113">Конференции</span><span class="sxs-lookup"><span data-stu-id="12485-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="12485-114">Да</span><span class="sxs-lookup"><span data-stu-id="12485-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="12485-115">Да</span><span class="sxs-lookup"><span data-stu-id="12485-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12485-116">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="12485-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="12485-117">Да</span><span class="sxs-lookup"><span data-stu-id="12485-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="12485-118">Да</span><span class="sxs-lookup"><span data-stu-id="12485-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12485-119">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="12485-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="12485-120">Да</span><span class="sxs-lookup"><span data-stu-id="12485-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="12485-121">Да</span><span class="sxs-lookup"><span data-stu-id="12485-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12485-122">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="12485-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="12485-123">Да</span><span class="sxs-lookup"><span data-stu-id="12485-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="12485-124">Да</span><span class="sxs-lookup"><span data-stu-id="12485-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12485-125">Виртуализация</span><span class="sxs-lookup"><span data-stu-id="12485-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="12485-126">Да</span><span class="sxs-lookup"><span data-stu-id="12485-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="12485-127">Да</span><span class="sxs-lookup"><span data-stu-id="12485-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12485-128">Высокий уровень доступности, отработка отказа, аварийное восстановление</span><span class="sxs-lookup"><span data-stu-id="12485-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="12485-129">Да</span><span class="sxs-lookup"><span data-stu-id="12485-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="12485-130">Нет</span><span class="sxs-lookup"><span data-stu-id="12485-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

