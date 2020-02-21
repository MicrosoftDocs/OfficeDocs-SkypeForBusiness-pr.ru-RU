---
title: 'Lync Server 2013: Просмотр сведений о политике расположения'
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
ms.openlocfilehash: 9ebd92944d02cf899ad6da60a586cd5ec24e9aa8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="33b59-102">Просмотр сведений о политике расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33b59-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33b59-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="33b59-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="33b59-104">В Lync Server 2013 вы можете использовать политику расположения для применения параметров, относящихся к расширенным функциям 9-1-1 (E9-1-1), а также к параметрам расположения для пользователей или контактов.</span><span class="sxs-lookup"><span data-stu-id="33b59-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="33b59-105">Политика расположения определяет, активирована ли для пользователя функция E9-1-1 и, если да, то в каком режиме выполняются экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="33b59-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="33b59-106">Например, можно использовать политику расположения, чтобы определить номер экстренного вызова (911 в США), а также должен ли автоматически оповещаться отдел корпоративной безопасности и как маршрутизировать вызов.</span><span class="sxs-lookup"><span data-stu-id="33b59-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="33b59-107">Политики расположения можно настроить из группы **конфигурации сети** в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33b59-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="33b59-108">В панели управления Lync Server вы можете просматривать, создавать, изменять и удалять политики расположения.</span><span class="sxs-lookup"><span data-stu-id="33b59-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="33b59-109">Используйте следующую процедуру для просмотра сведений о политиках расположения.</span><span class="sxs-lookup"><span data-stu-id="33b59-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="33b59-110">Подробнее о создании или изменении политик расположения можно узнать [в статье Создание или изменение политики расположения в Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="33b59-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="33b59-111">Просмотр сведений о политике расположения</span><span class="sxs-lookup"><span data-stu-id="33b59-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="33b59-112">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="33b59-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33b59-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33b59-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33b59-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="33b59-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33b59-115">На левой панели навигации щелкните **Конфигурация сети**, затем щелкните **Политика расположения**.</span><span class="sxs-lookup"><span data-stu-id="33b59-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="33b59-116">На странице **Политика расположения** выберите политику расположения, которую хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="33b59-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="33b59-117">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="33b59-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33b59-118">Одновременно можно просматривать сведения только об одной политике расположения.</span><span class="sxs-lookup"><span data-stu-id="33b59-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="33b59-119">Отдельная политика, называемая Global, существует по умолчанию и не может быть удалена или переименована.</span><span class="sxs-lookup"><span data-stu-id="33b59-119">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="33b59-120">Тем не менее, вы можете изменить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="33b59-120">However, you can modify the Global policy.</span></span> <span data-ttu-id="33b59-121">Эта политика будет применяться ко всем пользователям и контактам, если не создавать политики сайта или политики для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="33b59-121">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="33b59-122">Политики для отдельных пользователей должны быть применены к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="33b59-122">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33b59-123">См. также</span><span class="sxs-lookup"><span data-stu-id="33b59-123">See Also</span></span>


[<span data-ttu-id="33b59-124">Создание или изменение политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33b59-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="33b59-125">Создание политик расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33b59-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="33b59-126">Создание или изменение сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33b59-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="33b59-127">New — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="33b59-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="33b59-128">Set — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="33b59-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="33b59-129">Remove — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="33b59-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="33b59-130">Get — CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="33b59-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

