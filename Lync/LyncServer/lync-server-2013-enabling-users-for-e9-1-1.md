---
title: 'Lync Server 2013: включение пользователей для E9 — 1 – 1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5550ec608b34b66a3e47ceb4535dd23ca7c9a7f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="21ff8-102">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21ff8-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21ff8-103">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="21ff8-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="21ff8-104">Во время регистрации клиента Lync Server использует политику расположения для настройки свойств E9 – 1 – 1 для пользователей с включенной поддержкой корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="21ff8-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="21ff8-105">Эта политика содержит параметры, которые определяют способ реализации E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="21ff8-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="21ff8-106">Например, политика расположения содержит такие сведения, как строка набора экстренных номеров, а также сведения о том, требуется ли ввод расположения вручную, если служба сведений о местоположении не предоставляет ее автоматически.</span><span class="sxs-lookup"><span data-stu-id="21ff8-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="21ff8-107">Полное определение политики расположения показано в разделе [Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="21ff8-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="21ff8-108">Lync Server может назначать политику расположения клиентам на основе подсети или для пользователей на основе глобальной или индивидуальной политики.</span><span class="sxs-lookup"><span data-stu-id="21ff8-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="21ff8-109">Чтобы облегчить принятие решения о способе реализации такой поддержки для пользователей, вам следует сначала ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="21ff8-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="21ff8-110">**Вы планируете включить поддержку для всех пользователей или ограничить ее отдельными географическими областями в рамках предприятия?**</span><span class="sxs-lookup"><span data-stu-id="21ff8-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="21ff8-111">Вы можете назначить местоположение всем пользователям предприятия с помощью глобальной политики определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="21ff8-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="21ff8-112">Однако, назначая политику расположения сетевому сайту Lync Server и затем добавляя подсети на сайт, вы можете ограничить поддержку E9-1-1 для выбранных расположений внутри предприятия и указать поведение маршрутизации E9-1-1 для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="21ff8-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="21ff8-113">**Планируете ли вы включить поддержку для отдельных пользователей с помощью ?**</span><span class="sxs-lookup"><span data-stu-id="21ff8-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="21ff8-114">Для настройки поддержки E9-1-1 вы можете назначать политики определения местоположения непосредственно отдельным пользователям или объектам-контактам телефона общего доступа.</span><span class="sxs-lookup"><span data-stu-id="21ff8-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="21ff8-115">**Следует ли включать поддержку E9-1-1 для клиентов, которые находятся в роуминге за пределами сети или подключаются из неопределенной подсети?**</span><span class="sxs-lookup"><span data-stu-id="21ff8-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="21ff8-116">Если пользователю назначена Глобальная политика, для сайта или для отдельного пользователя, они могут быть необходимы для ручного ввода в клиент, если он не находится в определенной подсети или не обнаружено в службе сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="21ff8-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="21ff8-117">Дополнительные сведения см. [в статье Определение взаимодействия с пользователем, чтобы вручную приобрести расположение в Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="21ff8-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

