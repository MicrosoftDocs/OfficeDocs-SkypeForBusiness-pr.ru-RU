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
ms.openlocfilehash: d2b26f8f7b7b254a8576a08e9b24fdeb2da633b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510966"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="9feaf-102">Масштабируемость с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9feaf-102">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9feaf-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="9feaf-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="9feaf-104">Lync Server предлагается в двух выпусках: Enterprise Edition и Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9feaf-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="9feaf-105">Разные выпуски в основном предназначаются для разных размеров организаций.</span><span class="sxs-lookup"><span data-stu-id="9feaf-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="9feaf-106">Как показано в следующей таблице, оба выпуска поддерживают все функциональные возможности при любых рабочих нагрузках, за исключением высокого уровня доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="9feaf-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9feaf-107">Компонент</span><span class="sxs-lookup"><span data-stu-id="9feaf-107">Feature</span></span></th>
<th><span data-ttu-id="9feaf-108">Поддерживается в Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="9feaf-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="9feaf-109">Поддерживается в Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="9feaf-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9feaf-110">Обмен мгновенными сообщениями и функция присутствия</span><span class="sxs-lookup"><span data-stu-id="9feaf-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="9feaf-111">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="9feaf-112">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9feaf-113">Конференции</span><span class="sxs-lookup"><span data-stu-id="9feaf-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="9feaf-114">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="9feaf-115">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9feaf-116">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="9feaf-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="9feaf-117">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="9feaf-118">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9feaf-119">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="9feaf-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="9feaf-120">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="9feaf-121">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9feaf-122">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="9feaf-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="9feaf-123">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="9feaf-124">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9feaf-125">Виртуализация</span><span class="sxs-lookup"><span data-stu-id="9feaf-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="9feaf-126">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="9feaf-127">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9feaf-128">Высокий уровень доступности, отработка отказа, аварийное восстановление</span><span class="sxs-lookup"><span data-stu-id="9feaf-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="9feaf-129">Да</span><span class="sxs-lookup"><span data-stu-id="9feaf-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="9feaf-130">Нет</span><span class="sxs-lookup"><span data-stu-id="9feaf-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

