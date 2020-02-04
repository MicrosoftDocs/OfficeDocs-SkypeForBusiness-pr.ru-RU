---
title: 'Lync Server 2013: Блокировка и Разблокировка PIN-кода пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce748039b0e8f19a4efee56424c7661908fe6552
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="d8545-102">Блокировка и Разблокировка PIN-кода пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8545-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8545-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d8545-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d8545-104">Вы можете заблокировать или разблокировать ПИН-код пользователя в разделе " **Пользователи** " панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8545-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="d8545-105">Блокировка PIN-кода пользователя на панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="d8545-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d8545-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d8545-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8545-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8545-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d8545-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d8545-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d8545-109">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d8545-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d8545-110">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="d8545-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="d8545-111">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="d8545-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="d8545-112">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d8545-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="d8545-113">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="d8545-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="d8545-114">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d8545-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="d8545-115">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="d8545-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="d8545-116">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="d8545-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="d8545-117">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d8545-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="d8545-118">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d8545-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="d8545-119">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d8545-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="d8545-120">Щелкните пользователя, затем пункт **Действие**, затем **Заблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="d8545-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="d8545-121">Разблокирование ПИН-кода пользователя на панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="d8545-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d8545-122">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d8545-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8545-123">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8545-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d8545-124">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d8545-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d8545-125">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d8545-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d8545-126">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="d8545-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="d8545-127">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="d8545-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="d8545-128">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d8545-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="d8545-129">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="d8545-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="d8545-130">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d8545-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="d8545-131">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="d8545-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="d8545-132">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="d8545-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="d8545-133">В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d8545-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="d8545-134">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d8545-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="d8545-135">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d8545-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="d8545-136">Щелкните пользователя, затем пункт **Действие**, затем **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="d8545-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d8545-137">Блокировка и разблокировка контактов пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8545-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d8545-138">Вы можете заблокировать и разблокировать контакты пользователей с помощью Windows PowerShell и командлетов Lock-Ксклиентпин и Unlock-Ксклиентпин.</span><span class="sxs-lookup"><span data-stu-id="d8545-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="d8545-139">Эти командлеты можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8545-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d8545-140">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8545-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="d8545-141">Чтобы заблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="d8545-141">To lock a user PIN</span></span>

  - <span data-ttu-id="d8545-p104">Чтобы заблокировать ПИН-код пользователя, используйте командлет Lock-CsClientPin. Пример:</span><span class="sxs-lookup"><span data-stu-id="d8545-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="d8545-144">Чтобы разблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="d8545-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="d8545-p105">Чтобы разблокировать ПИН-код пользователя, используйте командлет Unlock-CsClientPin. Пример:</span><span class="sxs-lookup"><span data-stu-id="d8545-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="d8545-147">Дополнительные сведения можно найти в разделе справки по командлетам [Lock-ксклиентпин](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) и [Unlock-ксклиентпин](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="d8545-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

