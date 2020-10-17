---
title: 'Lync Server 2013: Создание политики маршрутизации VoIP для пользователей филиалов'
description: 'Lync Server 2013: Создание политики маршрутизации VoIP для пользователей филиалов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c39cff86d9ede957fa99e7955d8a87172380f963
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551085"
---
# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="3d703-103">Создание политики маршрутизации VoIP для пользователей филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d703-103">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d703-104">_**Последнее изменение темы:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="3d703-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="3d703-105">Рекомендуется создавать отдельную политику VoIP для пользователей на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="3d703-105">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="3d703-106">Эта политика должна содержать маршруты для выхода из шлюза устройства для обеспечения связи в филиалах или внешнего шлюза сервера для обеспечения связи в филиалах и резервных маршрутов для выхода из шлюза на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="3d703-106">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="3d703-107">Независимо от того, где зарегистрирован пользователь, либо в регистраторе на устройстве для обеспечения связи в филиале, либо на сервере для обеспечения связи в филиале или на кластере регистратора резервного копирования на центральном сайте, политика VoIP пользователя действует всегда.</span><span class="sxs-lookup"><span data-stu-id="3d703-107">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="3d703-108">Настройка политики маршрутизации VoIP для пользователей филиалов</span><span class="sxs-lookup"><span data-stu-id="3d703-108">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="3d703-109">Создайте абонентскую группу на уровне пользователя и назначьте ее пользователям филиалов.</span><span class="sxs-lookup"><span data-stu-id="3d703-109">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="3d703-110">(Ознакомьтесь со статьей [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md) в документации по операциям.)</span><span class="sxs-lookup"><span data-stu-id="3d703-110">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="3d703-111">Назначьте правила нормализации, соответствующие привычкам набора номера для пользователей на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="3d703-111">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="3d703-112">Если устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах отключается к резервному пулу резервного копирования на центральном сайте, будет действовать та же самая абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="3d703-112">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="3d703-113">(Ознакомьтесь со статьей [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md) в документации по операциям.)</span><span class="sxs-lookup"><span data-stu-id="3d703-113">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="3d703-114">Настройте маршрут голосовой связи, превратиться с шлюза устройства для обеспечения связи в филиалах или с помощью внешнего шлюза сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="3d703-114">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="3d703-115">(Обратитесь к разделу [Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md) в документации по операциям.)</span><span class="sxs-lookup"><span data-stu-id="3d703-115">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="3d703-116">Настройте маршрут вызовов резервного копирования для устройства для обеспечения связи в филиалах или шлюза сервера для обеспечения связи в филиалах, чтобы он ссылался на пул резервного регистратора (сопоставленный с сервером-посредником) на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="3d703-116">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="3d703-117">(Просмотрите документацию для устройства для обеспечения связи в филиалах или для обеспечения связи поставщика сервера филиала).</span><span class="sxs-lookup"><span data-stu-id="3d703-117">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d703-118">Этот процесс резервного копирования позволяет убедиться, что входящие звонки пользователю филиала будут работать, когда устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах недоступно (например, если он отключен для обслуживания).</span><span class="sxs-lookup"><span data-stu-id="3d703-118">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="3d703-119">Если сервер регистратора и посредника на устройстве для обеспечения связи в филиале или сервере для обеспечения связи в филиалах недоступны, а пользователь зарегистрирован в резервном пуле резервного регистратора на центральном сайте, входящие звонки могут маршрутизироваться для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d703-119">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="3d703-120">**Следующий шаг**: [Настройка параметров перенаправления голосовой почты в Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3d703-120">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

