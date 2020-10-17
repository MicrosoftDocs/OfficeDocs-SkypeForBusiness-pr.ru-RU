---
title: 'Lync Server 2013: определение требований для экстренных вызовов'
description: 'Lync Server 2013: определение требований для экстренных вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3c9908dcb4008a1442af86971e42eb4096a98b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545405"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="7624a-103">Определение требований для экстренных вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-103">Defining your requirements for emergency calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7624a-104">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="7624a-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="7624a-105">Прежде чем приступить к развертыванию Microsoft Lync Server 2013 E9 – 1 – 1, сначала необходимо ответить на вопросы, описанные в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="7624a-105">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="7624a-106">Необходимое планирование зависит от типа решения E9-1-1, которое планируется разворачивать — канал SIP для подключения к поставщику услуг E9-1-1  или шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="7624a-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="7624a-107">В следующей таблице приведены разделы данного руководства по планированию, которые необходимо изучить для каждого из этих решений.</span><span class="sxs-lookup"><span data-stu-id="7624a-107">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="7624a-108">Этапы планирования типа решения E9-1-1</span><span class="sxs-lookup"><span data-stu-id="7624a-108">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7624a-109">Поставщик услуг по каналу SIP</span><span class="sxs-lookup"><span data-stu-id="7624a-109">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="7624a-110">Шлюз ELIN</span><span class="sxs-lookup"><span data-stu-id="7624a-110">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7624a-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7624a-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7624a-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7624a-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7624a-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7624a-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7624a-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Управление расположениями для поставщиков услуг магистрали SIP в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7624a-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Управление расположениями для шлюзов ELIN в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7624a-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7624a-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7624a-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Проектирование магистрали SIP для E9 – 1 – 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7624a-122"><a href="lync-server-2013-including-the-security-desk.md">Включая службу безопасности в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7624a-123"><a href="lync-server-2013-including-the-security-desk.md">Включая службу безопасности в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-123"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7624a-124"><a href="lync-server-2013-defining-the-location-policy.md">Определение политики расположения для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-124"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7624a-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Выбор поставщика услуг E9 – 1 – 1 для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7624a-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Назначение области действия политики расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7624a-127"><a href="lync-server-2013-defining-the-location-policy.md">Определение политики расположения для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-127"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7624a-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Назначение области действия политики расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7624a-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="7624a-129">Содержание</span><span class="sxs-lookup"><span data-stu-id="7624a-129">In This Section</span></span>

  - [<span data-ttu-id="7624a-130">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-130">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="7624a-131">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-131">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="7624a-132">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-132">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="7624a-133">Управление расположениями для поставщиков услуг магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-133">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="7624a-134">Управление расположениями для шлюзов ELIN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-134">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="7624a-135">Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-135">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="7624a-136">Проектирование магистрали SIP для E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-136">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="7624a-137">Включая службу безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-137">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="7624a-138">Выбор поставщика услуг E9 – 1 – 1 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-138">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="7624a-139">Определение политики расположения для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-139">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="7624a-140">Назначение области действия политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7624a-140">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

