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
ms.openlocfilehash: 10bf167538158e0f427b1522738374ae7c2b5320
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="adefe-102">Масштабируемость с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adefe-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adefe-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="adefe-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="adefe-104">Lync Server предлагается в двух выпусках: Enterprise Edition и Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="adefe-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="adefe-105">Разные выпуски в основном предназначаются для разных размеров организаций.</span><span class="sxs-lookup"><span data-stu-id="adefe-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="adefe-106">Как показано в следующей таблице, оба выпуска поддерживают все функциональные возможности при любых рабочих нагрузках, за исключением высокого уровня доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="adefe-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adefe-107">Функция</span><span class="sxs-lookup"><span data-stu-id="adefe-107">Feature</span></span></th>
<th><span data-ttu-id="adefe-108">Поддерживается в Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="adefe-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="adefe-109">Поддерживается в Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="adefe-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adefe-110">Обмен мгновенными сообщениями и функция присутствия</span><span class="sxs-lookup"><span data-stu-id="adefe-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="adefe-111">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="adefe-112">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adefe-113">Конференции</span><span class="sxs-lookup"><span data-stu-id="adefe-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="adefe-114">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="adefe-115">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adefe-116">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="adefe-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="adefe-117">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="adefe-118">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adefe-119">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="adefe-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="adefe-120">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="adefe-121">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adefe-122">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="adefe-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="adefe-123">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="adefe-124">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adefe-125">Виртуализация</span><span class="sxs-lookup"><span data-stu-id="adefe-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="adefe-126">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="adefe-127">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adefe-128">Высокий уровень доступности, отработка отказа, аварийное восстановление</span><span class="sxs-lookup"><span data-stu-id="adefe-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="adefe-129">Да</span><span class="sxs-lookup"><span data-stu-id="adefe-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="adefe-130">Нет</span><span class="sxs-lookup"><span data-stu-id="adefe-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

