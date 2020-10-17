---
title: 'Lync Server 2013: включение пользователей для E9 — 1 – 1'
description: 'Lync Server 2013: включение пользователей для E9 — 1 – 1.'
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
ms.openlocfilehash: 6ba29406dc0d7a1140c83a1a9d271afca5d6b0c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546445"
---
# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="f1b28-103">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b28-103">Enabling users for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1b28-104">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="f1b28-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="f1b28-105">Во время регистрации клиента Lync Server использует политику расположения для настройки свойств E9 – 1 – 1 для пользователей с включенной поддержкой корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f1b28-105">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="f1b28-106">Эта политика содержит параметры, которые определяют способ реализации E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f1b28-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="f1b28-107">Например, политика расположения содержит такие сведения, как строка набора экстренных номеров, а также сведения о том, требуется ли ввод расположения вручную, если служба сведений о местоположении не предоставляет ее автоматически.</span><span class="sxs-lookup"><span data-stu-id="f1b28-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="f1b28-108">Полное определение политики расположения показано в разделе [Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f1b28-108">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="f1b28-109">Lync Server может назначать политику расположения клиентам на основе подсети или для пользователей на основе глобальной или индивидуальной политики.</span><span class="sxs-lookup"><span data-stu-id="f1b28-109">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="f1b28-110">Чтобы облегчить принятие решения о способе реализации такой поддержки для пользователей, вам следует сначала ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="f1b28-110">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="f1b28-111">**Вы планируете включить поддержку для всех пользователей или ограничить ее отдельными географическими областями в рамках предприятия?**</span><span class="sxs-lookup"><span data-stu-id="f1b28-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="f1b28-112">Вы можете назначить местоположение всем пользователям предприятия с помощью глобальной политики определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="f1b28-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="f1b28-113">Однако, назначая политику расположения сетевому сайту Lync Server и затем добавляя подсети на сайт, вы можете ограничить поддержку E9-1-1 для выбранных расположений внутри предприятия и указать поведение маршрутизации E9-1-1 для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="f1b28-113">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="f1b28-114">**Планируете ли вы включить поддержку для отдельных пользователей с помощью ?**</span><span class="sxs-lookup"><span data-stu-id="f1b28-114">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="f1b28-115">Для настройки поддержки E9-1-1 вы можете назначать политики определения местоположения непосредственно отдельным пользователям или объектам-контактам телефона общего доступа.</span><span class="sxs-lookup"><span data-stu-id="f1b28-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="f1b28-116">**Следует ли включать поддержку E9-1-1 для клиентов, которые находятся в роуминге за пределами сети или подключаются из неопределенной подсети?**</span><span class="sxs-lookup"><span data-stu-id="f1b28-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="f1b28-117">Если пользователю назначена Глобальная политика, для сайта или для отдельного пользователя, они могут быть необходимы для ручного ввода в клиент, если он не находится в определенной подсети или не обнаружено в службе сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="f1b28-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="f1b28-118">Дополнительные сведения см. [в статье Определение взаимодействия с пользователем, чтобы вручную приобрести расположение в Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="f1b28-118">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

