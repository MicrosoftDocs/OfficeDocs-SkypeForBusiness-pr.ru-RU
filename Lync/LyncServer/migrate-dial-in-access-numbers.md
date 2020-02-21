---
title: Перенос номеров доступа для телефонного подключения
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e808e587c9bd65668e35eba46692591bf72b9c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="58c6f-102">Перенос номеров доступа для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="58c6f-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58c6f-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="58c6f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="58c6f-104">Для переноса номеров доступа с телефонным подключением с Lync Server 2010 на Lync Server 2013 необходимо запустить командлет **Move – CsApplicationEndpoint** для переноса объектов Contact.</span><span class="sxs-lookup"><span data-stu-id="58c6f-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="58c6f-105">В течение периода сосуществования Lync Server 2010 и Lync Server 2013 номера доступа по телефонной линии, созданные в Lync Server 2013, ведут себя так же, как и номера доступа по телефонной линии, созданные в Lync Server 2010, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="58c6f-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="58c6f-106">Номера доступа с телефонным подключением, созданные в Lync Server 2010, но перемещенные на Lync Server 2013 или ранее созданные в Lync Server 2013, до, во время или после миграции, имеют следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="58c6f-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="58c6f-107">не отображаются в приглашениях на собрание Office Communications Server 2007 R2  и на странице номеров телефонного подключения;</span><span class="sxs-lookup"><span data-stu-id="58c6f-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="58c6f-108">отображаются в приглашениях на собрание Lync Server 2010 и на странице номеров телефонного подключения;</span><span class="sxs-lookup"><span data-stu-id="58c6f-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="58c6f-109">отображаются в приглашениях на собрание Lync Server 2013 и на странице номеров телефонного подключения;</span><span class="sxs-lookup"><span data-stu-id="58c6f-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="58c6f-110">их нельзя просматривать или изменять в средстве администрирования Office Communications Server 2007 R2;</span><span class="sxs-lookup"><span data-stu-id="58c6f-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="58c6f-111">их можно просматривать и изменять в панели управления Lync Server 2010 и консоли управления Lync Server 2010;</span><span class="sxs-lookup"><span data-stu-id="58c6f-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="58c6f-112">их можно просматривать и изменять в панели управления Lync Server 2013 и консоли управления Lync Server 2013;</span><span class="sxs-lookup"><span data-stu-id="58c6f-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="58c6f-113">их можно повторно упорядочивать внутри региона с помощью командлета Set-CsDialinConferencingAccessNumber с параметром Priority.</span><span class="sxs-lookup"><span data-stu-id="58c6f-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="58c6f-p102">Необходимо завершить миграцию телефонных номеров доступа, указывающих на пул Lync Server 2010 перед ликвидацией пула Lync Server 2010. Если вы не завершили миграцию телефонных номеров доступа, как описано в следующей процедуре, входящие вызовы на эти номера не будут работать.</span><span class="sxs-lookup"><span data-stu-id="58c6f-p102">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool. If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="58c6f-116">Эту процедуру необходимо выполнить перед списанием пула Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="58c6f-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="58c6f-117">Рекомендуется переместить телефонные номера доступа при незначительном использовании сети на случай короткого периода недоступности службы.</span><span class="sxs-lookup"><span data-stu-id="58c6f-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="58c6f-118">**Определение и перемещение телефонных номеров доступа**</span><span class="sxs-lookup"><span data-stu-id="58c6f-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="58c6f-119">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="58c6f-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="58c6f-120">Для перемещения каждого номера доступа с телефонным подключением в пул, размещенный на Lync Server 2013, в командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="58c6f-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="58c6f-121">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58c6f-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="58c6f-122">В левой области навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="58c6f-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="58c6f-123">Перейдите на вкладку **Телефонный номер доступа**.</span><span class="sxs-lookup"><span data-stu-id="58c6f-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="58c6f-124">Убедитесь, что номера доступа для телефонного подключения не сохраняются для пула Lync Server 2010, из которого выполняется миграция.</span><span class="sxs-lookup"><span data-stu-id="58c6f-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58c6f-125">Если номера доступа для телефонного подключения почтовые точки в пуле Lync Server 2013, можно списать пул Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="58c6f-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="58c6f-126">**Проверка миграции телефонных номеров доступа с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="58c6f-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="58c6f-127">В учетной записи пользователя, назначенной роли  **CsUserAdministrator** или **CsAdministrator**, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="58c6f-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58c6f-128">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58c6f-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="58c6f-129">В левой области навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="58c6f-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="58c6f-130">Перейдите на вкладку **Телефонный номер доступа**.</span><span class="sxs-lookup"><span data-stu-id="58c6f-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="58c6f-131">Убедитесь, что все номера доступа для телефонного подключения перенесены в пул, размещенный на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58c6f-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="58c6f-132">**Проверка миграции телефонных номеров доступа с помощью консоли управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="58c6f-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="58c6f-133">Откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58c6f-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="58c6f-134">Чтобы вернуть все перемещенные телефонные номера доступа к конференции в командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="58c6f-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="58c6f-135">Убедитесь, что все номера доступа для телефонного подключения перенесены в пул, размещенный на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58c6f-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

