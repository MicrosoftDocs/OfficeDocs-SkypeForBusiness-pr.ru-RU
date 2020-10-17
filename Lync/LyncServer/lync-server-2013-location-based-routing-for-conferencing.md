---
title: 'Lync Server 2013: Маршрутизация Location-Based для конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03e216e80b50bd7b2d5c0515700c4f1cd7260f22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513806"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f8757-102">Маршрутизация Location-Based для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8757-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8757-103">_**Последнее изменение темы:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="f8757-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="f8757-104">Маршрутизация Location-Based позволяет ограничить маршрутизацию вызовов между конечными точками VoIP и PSTN в зависимости от расположения сторон в вызове.</span><span class="sxs-lookup"><span data-stu-id="f8757-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="f8757-105">С накопительным пакетом обновления 2 (SP2) для Lync Server 2013 Location-Based правила маршрутизации могут быть применены к собраниям Lync (например, конференциям), чтобы предотвратить обход платных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8757-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f8757-106">Приложение отслеживает активную конференцию и применяет ограничения Location-Based маршрутизации на основе расположения участвующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8757-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="f8757-107">Кроме того, приложение для конференц-связи с Location-Based маршрутизации дополнительно позволяет принудительно применять ограничения маршрутизации Location-Based Консультативного для передачи данных с использованием конечных точек PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8757-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8757-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="f8757-108">In This Section</span></span>

  - [<span data-ttu-id="f8757-109">Обзор маршрутизации Location-Based для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8757-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="f8757-110">Маршрутизация на основе расположения и передачи вызовов Консультативного в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8757-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="f8757-111">Требования к маршрутизации Location-Based для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8757-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="f8757-112">Настройка маршрутизации Location-Based для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8757-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

