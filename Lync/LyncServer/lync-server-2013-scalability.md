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
ms.openlocfilehash: 3bd340d46855f01e8ff43dc9f66b527e5df1967c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="230e9-102">Масштабируемость с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="230e9-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="230e9-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="230e9-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="230e9-104">Lync Server предлагается в двух выпусках: Enterprise Edition и Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="230e9-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="230e9-105">Разные выпуски в основном предназначаются для разных размеров организаций.</span><span class="sxs-lookup"><span data-stu-id="230e9-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="230e9-106">Как показано в следующей таблице, оба выпуска поддерживают все функциональные возможности при любых рабочих нагрузках, за исключением высокого уровня доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="230e9-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="230e9-107">Функция</span><span class="sxs-lookup"><span data-stu-id="230e9-107">Feature</span></span></th>
<th><span data-ttu-id="230e9-108">Поддерживается в Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="230e9-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="230e9-109">Поддерживается в Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="230e9-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="230e9-110">Обмен мгновенными сообщениями и функция присутствия</span><span class="sxs-lookup"><span data-stu-id="230e9-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="230e9-111">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="230e9-112">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="230e9-113">Конференции</span><span class="sxs-lookup"><span data-stu-id="230e9-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="230e9-114">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="230e9-115">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="230e9-116">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="230e9-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="230e9-117">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="230e9-118">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="230e9-119">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="230e9-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="230e9-120">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="230e9-121">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="230e9-122">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="230e9-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="230e9-123">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="230e9-124">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="230e9-125">Виртуализация</span><span class="sxs-lookup"><span data-stu-id="230e9-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="230e9-126">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="230e9-127">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="230e9-128">Высокий уровень доступности, отработка отказа, аварийное восстановление</span><span class="sxs-lookup"><span data-stu-id="230e9-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="230e9-129">Да</span><span class="sxs-lookup"><span data-stu-id="230e9-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="230e9-130">Нет</span><span class="sxs-lookup"><span data-stu-id="230e9-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

