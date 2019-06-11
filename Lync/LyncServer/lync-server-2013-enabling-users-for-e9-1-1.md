---
title: 'Lync Server 2013: включение пользователей для E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="01e97-102">Включение пользователей для E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e97-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01e97-103">_**Тема последнего изменения:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="01e97-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="01e97-104">Во время регистрации клиента Lync Server использует политику расположения для настройки свойств E9-1-1 для корпоративных пользователей с поддержкой голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="01e97-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="01e97-105">Эта политика содержит параметры, которые определяют способ реализации E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="01e97-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="01e97-106">Например, политика "расположение" содержит такие сведения, как строка набора номера, а также укажите, требуется ли пользователю вручную вводить расположение, если служба сведений о расположении не предоставляет ее автоматически.</span><span class="sxs-lookup"><span data-stu-id="01e97-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="01e97-107">Полное определение политики расположения показано в разделе [Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="01e97-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="01e97-108">Lync Server может назначать политику местоположений клиентам в зависимости от подсети или пользователей на основе глобальной или индивидуальной политики.</span><span class="sxs-lookup"><span data-stu-id="01e97-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="01e97-109">Чтобы облегчить принятие решения о способе реализации такой поддержки для пользователей, вам следует сначала ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="01e97-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="01e97-110">**Вы планируете включить поддержку для всех пользователей или ограничить ее отдельными географическими областями в рамках предприятия?**</span><span class="sxs-lookup"><span data-stu-id="01e97-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="01e97-111">Вы можете назначить расположение всем пользователям предприятия с помощью глобальной политики расположения.</span><span class="sxs-lookup"><span data-stu-id="01e97-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="01e97-112">Тем не менее, назначая политику местоположения на сайте Lync Server Network и затем добавляя подсети на сайт, вы можете ограничить поддержку E9-1-1 для выбранных расположений в масштабах предприятия и задать процесс маршрутизации E9-1-1 для конкретных сайтов.</span><span class="sxs-lookup"><span data-stu-id="01e97-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="01e97-113">**Планируете ли вы включить поддержку для отдельных пользователей с помощью ?**</span><span class="sxs-lookup"><span data-stu-id="01e97-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="01e97-114">Для настройки поддержки E9-1-1 вы можете назначать политики расположения непосредственно отдельным пользователям или контактным объектам телефона общего доступа.</span><span class="sxs-lookup"><span data-stu-id="01e97-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="01e97-115">**Следует ли включать поддержку E9-1-1 для клиентов, которые находятся в роуминге за пределами сети или подключаются из неопределенной подсети?**</span><span class="sxs-lookup"><span data-stu-id="01e97-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="01e97-116">Если пользователям назначены глобальные, сайты или индивидуальные параметры, они могут быть необходимы для того, чтобы вручную указать расположение в клиенте, если клиент не находится в определенной подсети или расположение не обнаружено службой сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="01e97-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="01e97-117">Подробности можно найти [в разделе Определение интерфейса пользователя, чтобы вручную приобрести расположение в Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="01e97-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

