---
title: 'Lync Server 2013: Просмотр сведений о политике расположения'
description: 'Lync Server 2013: Просмотр сведений о политике расположения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fecc5de5fb71014a1641038e9e09afba0e90cdb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565425"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="23085-103">Просмотр сведений о политике расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23085-103">Viewing location policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23085-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="23085-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="23085-105">В Lync Server 2013 вы можете использовать политику расположения для применения параметров, относящихся к расширенным функциям 9-1-1 (E9-1-1), а также к параметрам расположения для пользователей или контактов.</span><span class="sxs-lookup"><span data-stu-id="23085-105">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="23085-106">Политика расположения определяет, активирована ли для пользователя функция E9-1-1 и, если да, то в каком режиме выполняются экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="23085-106">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="23085-107">Например, можно использовать политику расположения, чтобы определить номер экстренного вызова (911 в США), а также должен ли автоматически оповещаться отдел корпоративной безопасности и как маршрутизировать вызов.</span><span class="sxs-lookup"><span data-stu-id="23085-107">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="23085-108">Политики расположения можно настроить из группы **конфигурации сети** в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23085-108">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="23085-109">В панели управления Lync Server вы можете просматривать, создавать, изменять и удалять политики расположения.</span><span class="sxs-lookup"><span data-stu-id="23085-109">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="23085-110">Используйте следующую процедуру для просмотра сведений о политиках расположения.</span><span class="sxs-lookup"><span data-stu-id="23085-110">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="23085-111">Подробнее о создании или изменении политик расположения можно узнать [в статье Создание или изменение политики расположения в Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="23085-111">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="23085-112">Просмотр сведений о политике расположения</span><span class="sxs-lookup"><span data-stu-id="23085-112">To view information about a location policy</span></span>

1.  <span data-ttu-id="23085-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="23085-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23085-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23085-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="23085-115">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23085-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="23085-116">На левой панели навигации щелкните **Конфигурация сети**, затем щелкните **Политика расположения**.</span><span class="sxs-lookup"><span data-stu-id="23085-116">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="23085-117">На странице **Политика расположения** выберите политику расположения, которую хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="23085-117">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="23085-118">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="23085-118">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23085-119">Одновременно можно просматривать сведения только об одной политике расположения.</span><span class="sxs-lookup"><span data-stu-id="23085-119">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="23085-120">Отдельная политика, называемая Global, существует по умолчанию и не может быть удалена или переименована.</span><span class="sxs-lookup"><span data-stu-id="23085-120">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="23085-121">Тем не менее, вы можете изменить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="23085-121">However, you can modify the Global policy.</span></span> <span data-ttu-id="23085-122">Эта политика будет применяться ко всем пользователям и контактам, если не создавать политики сайта или политики для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="23085-122">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="23085-123">Политики для отдельных пользователей должны быть применены к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="23085-123">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23085-124">См. также</span><span class="sxs-lookup"><span data-stu-id="23085-124">See Also</span></span>


[<span data-ttu-id="23085-125">Создание или изменение политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23085-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="23085-126">Создание политик расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23085-126">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="23085-127">Создание или изменение сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23085-127">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="23085-128">New — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="23085-128">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="23085-129">Set — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="23085-129">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="23085-130">Remove — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="23085-130">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="23085-131">Get — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="23085-131">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

