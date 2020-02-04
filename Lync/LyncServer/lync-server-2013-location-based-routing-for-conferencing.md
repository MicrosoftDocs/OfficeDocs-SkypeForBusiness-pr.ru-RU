---
title: 'Lync Server 2013: Маршрутизация на основе местоположения для конференций'
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
ms.openlocfilehash: dffc6ee9beaabc4705ac47e643a3fb19e589a745
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="33e5c-102">Маршрутизация на основе местоположения для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33e5c-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33e5c-103">_**Тема последнего изменения:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="33e5c-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="33e5c-104">Маршрутизация на основе местоположения позволяет ограничить маршрутизацию звонков между конечными точками VoIP и КОММУТИРУЕМыми конечными точками, основываясь на местоположении сторон в звонке.</span><span class="sxs-lookup"><span data-stu-id="33e5c-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="33e5c-105">Благодаря накопительному обновлению 2 для Lync Server 2013 на собраниях Lync (например, конференц-связи) можно использовать правила маршрутизации на основе местоположения, чтобы предотвратить бесплатный звонок по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="33e5c-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="33e5c-106">Приложение отслеживает активную конференцию и применяет ограничения для маршрутизации на основе местоположения на основе местоположения пользователей, участвующих в программе.</span><span class="sxs-lookup"><span data-stu-id="33e5c-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="33e5c-107">Приложение для конференц-связи с учетом местоположения дополнительно позволяет принудительно использовать ограничения маршрутизации на основе местоположения для консултативе передач, использующих конечные точки PSTN.</span><span class="sxs-lookup"><span data-stu-id="33e5c-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="33e5c-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="33e5c-108">In This Section</span></span>

  - [<span data-ttu-id="33e5c-109">Обзор маршрутизации на основе местоположения для конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33e5c-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="33e5c-110">Маршрутизация на основе местоположения и передача звонков консултативе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33e5c-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="33e5c-111">Требования для маршрутизации на основе местоположения для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33e5c-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="33e5c-112">Конфигурация маршрутизации на основе расположения для конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33e5c-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

