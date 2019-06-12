---
title: Перенос номеров доступа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="e5b7d-102">Перенос номеров доступа</span><span class="sxs-lookup"><span data-stu-id="e5b7d-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5b7d-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e5b7d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e5b7d-104">Для миграции номеров доступа для телефонного подключения с Lync Server 2010 на Lync Server 2013 требуется запуск командлета **Move-ксаппликатионендпоинт** для миграции объектов контакта.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="e5b7d-105">В течение периода сосуществования Lync Server 2010 и Lync Server 2013 номера доступа для телефонного подключения, созданные в Lync Server 2013, будут вести себя аналогично номерам доступа для телефонного подключения, которые вы создаете в Lync Server 2010, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="e5b7d-106">Номера доступа для телефонного подключения, созданные в Lync Server 2010, но перенесенные на Lync Server 2013 или созданные в Lync Server 2013, после или после миграции, обладают следующими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="e5b7d-107">Не отображаются в приглашениях на собрание Office Communications Server 2007 R2 и на странице номера доступа для подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="e5b7d-108">Отображаются в приглашениях на собрания Lync Server 2010 и на странице номера доступа для подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="e5b7d-109">Отображаются в приглашениях на собрания Lync Server 2013 и на странице номера доступа для подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="e5b7d-110">В средстве администрирования Office Communications Server 2007 R2 нельзя просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="e5b7d-111">Можно просмотреть и изменить на панели управления Lync Server 2010 и в командной консоли Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="e5b7d-112">Можно просмотреть и изменить на панели управления Lync Server 2013 и в командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="e5b7d-113">Возможность повторной последовательности в регионе с помощью командлета Set-КсдиалинконференЦингакцесснумбер с параметром priority.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="e5b7d-114">Перед списанием пула Lync Server 2010 необходимо завершить перенос номеров доступа с телефонным подключением, указывающих на пул Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="e5b7d-115">Если вы не закончите перенос номеров доступа для телефонного подключения, как описано в приведенной ниже процедуре, входящие звонки на номера доступа завершатся сбоем.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5b7d-116">Эту процедуру необходимо выполнить перед списанием пула Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e5b7d-117">Мы рекомендуем вам перемещать номера доступа для телефонного подключения при низком использовании сети в случае короткого периода простоя службы.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="e5b7d-118">**Для идентификации и перемещения номеров доступа с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="e5b7d-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="e5b7d-119">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e5b7d-120">Чтобы переместить каждый номер доступа с телефонным подключением в пул, размещенный на Lync Server 2013, в командной строке выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="e5b7d-121">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="e5b7d-122">На левой панели навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="e5b7d-123">Откройте вкладку **номер доступа для телефонного подключения** .</span><span class="sxs-lookup"><span data-stu-id="e5b7d-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="e5b7d-124">Убедитесь, что для пула Lync Server 2010, из которого выполняется миграция, нет номеров доступа для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5b7d-125">Если все номера доступа для телефонного подключения указывают на пул Lync Server 2013, вы можете списать пул Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="e5b7d-126">**Проверка миграции номеров доступа для телефонного подключения с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="e5b7d-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="e5b7d-127">Из учетной записи пользователя, которой назначена роль **ксусерадминистратор** или роль **ксадминистратор** , войдите на любой компьютер во внутренней среде.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5b7d-128">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="e5b7d-129">На левой панели навигации щелкните элемент **Конференция**.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="e5b7d-130">Откройте вкладку **номер доступа для телефонного подключения** .</span><span class="sxs-lookup"><span data-stu-id="e5b7d-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="e5b7d-131">Убедитесь, что все номера доступа для телефонного подключения перенесены в пул, размещенный на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="e5b7d-132">**Проверка миграции номеров доступа для телефонного подключения с помощью командной консоли Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="e5b7d-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="e5b7d-133">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e5b7d-134">Чтобы вернуть все номера доступа для конференц-связи с телефонным подключением, перенесенные из командной строки, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="e5b7d-135">Убедитесь, что все номера доступа для телефонного подключения перенесены в пул, размещенный на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5b7d-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

