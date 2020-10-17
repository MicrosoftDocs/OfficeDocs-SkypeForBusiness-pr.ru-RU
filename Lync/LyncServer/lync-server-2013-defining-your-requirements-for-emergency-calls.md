---
title: 'Lync Server 2013: определение требований для экстренных вызовов'
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
ms.openlocfilehash: 2d190d240db85016bd13bfd2480b42b088ca5f88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504366"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="f4b9b-102">Определение требований для экстренных вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4b9b-103">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="f4b9b-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="f4b9b-104">Прежде чем приступить к развертыванию Microsoft Lync Server 2013 E9 – 1 – 1, сначала необходимо ответить на вопросы, описанные в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="f4b9b-105">Необходимое планирование зависит от типа решения E9-1-1, которое планируется разворачивать — канал SIP для подключения к поставщику услуг E9-1-1  или шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="f4b9b-106">В следующей таблице приведены разделы данного руководства по планированию, которые необходимо изучить для каждого из этих решений.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="f4b9b-107">Этапы планирования типа решения E9-1-1</span><span class="sxs-lookup"><span data-stu-id="f4b9b-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4b9b-108">Поставщик услуг по каналу SIP</span><span class="sxs-lookup"><span data-stu-id="f4b9b-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="f4b9b-109">Шлюз ELIN</span><span class="sxs-lookup"><span data-stu-id="f4b9b-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4b9b-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4b9b-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4b9b-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4b9b-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4b9b-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4b9b-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4b9b-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Управление расположениями для поставщиков услуг магистрали SIP в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4b9b-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Управление расположениями для шлюзов ELIN в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4b9b-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4b9b-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4b9b-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Проектирование магистрали SIP для E9 – 1 – 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4b9b-121"><a href="lync-server-2013-including-the-security-desk.md">Включая службу безопасности в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4b9b-122"><a href="lync-server-2013-including-the-security-desk.md">Включая службу безопасности в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4b9b-123"><a href="lync-server-2013-defining-the-location-policy.md">Определение политики расположения для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4b9b-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Выбор поставщика услуг E9 – 1 – 1 для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4b9b-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Назначение области действия политики расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4b9b-126"><a href="lync-server-2013-defining-the-location-policy.md">Определение политики расположения для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4b9b-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Назначение области действия политики расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f4b9b-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="f4b9b-128">Содержание</span><span class="sxs-lookup"><span data-stu-id="f4b9b-128">In This Section</span></span>

  - [<span data-ttu-id="f4b9b-129">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="f4b9b-130">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="f4b9b-131">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="f4b9b-132">Управление расположениями для поставщиков услуг магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="f4b9b-133">Управление расположениями для шлюзов ELIN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="f4b9b-134">Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="f4b9b-135">Проектирование магистрали SIP для E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="f4b9b-136">Включая службу безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="f4b9b-137">Выбор поставщика услуг E9 – 1 – 1 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="f4b9b-138">Определение политики расположения для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="f4b9b-139">Назначение области действия политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9b-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

