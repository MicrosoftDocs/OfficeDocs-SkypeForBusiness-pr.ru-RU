---
title: 'Lync Server 2013: Блокировка и разблокировка ПИН-кода пользователя'
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
ms.openlocfilehash: 698bbb2138978cea9ca5b2aa75b5370ea7e11c14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="3bf6c-102">Блокировка и разблокировка ПИН-кода пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bf6c-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bf6c-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3bf6c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3bf6c-104">Вы можете заблокировать или разблокировать ПИН-код пользователя в разделе **Пользователи** панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="3bf6c-105">Блокировка ПИН-кода пользователя в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="3bf6c-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3bf6c-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3bf6c-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3bf6c-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3bf6c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3bf6c-109">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3bf6c-110">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="3bf6c-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="3bf6c-111">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="3bf6c-112">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="3bf6c-113">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="3bf6c-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3bf6c-114">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3bf6c-115">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="3bf6c-116">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="3bf6c-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="3bf6c-117">В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="3bf6c-118">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="3bf6c-119">Нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="3bf6c-120">Щелкните пользователя, затем пункт **Действие**, затем **Заблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="3bf6c-121">Разблокировка ПИН-кода пользователя в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="3bf6c-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3bf6c-122">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3bf6c-123">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3bf6c-124">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3bf6c-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3bf6c-125">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3bf6c-126">Используйте один из следующих методов для поиска пользователя:</span><span class="sxs-lookup"><span data-stu-id="3bf6c-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="3bf6c-127">В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="3bf6c-128">Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="3bf6c-129">(Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:</span><span class="sxs-lookup"><span data-stu-id="3bf6c-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3bf6c-130">Нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3bf6c-131">Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="3bf6c-132">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="3bf6c-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="3bf6c-133">В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="3bf6c-134">Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="3bf6c-135">Щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="3bf6c-136">Щелкните пользователя, затем пункт **Действие**, затем **Разблокировать ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3bf6c-137">Блокировка и разблокировка ПИН-кодов пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bf6c-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3bf6c-138">Вы можете заблокировать и разблокировать ПИН-коды пользователей с помощью Windows PowerShell, а также командлетов Lock-CsClientPin и Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="3bf6c-139">Эти командлеты можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3bf6c-140">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="3bf6c-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="3bf6c-141">Чтобы заблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="3bf6c-141">To lock a user PIN</span></span>

  - <span data-ttu-id="3bf6c-p104">Чтобы заблокировать ПИН-код пользователя, используйте командлет Lock-CsClientPin. Пример:</span><span class="sxs-lookup"><span data-stu-id="3bf6c-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="3bf6c-144">Чтобы разблокировать ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="3bf6c-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="3bf6c-p105">Чтобы разблокировать ПИН-код пользователя, используйте командлет Unlock-CsClientPin. Пример:</span><span class="sxs-lookup"><span data-stu-id="3bf6c-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="3bf6c-147">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлетов [Lock — CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) и [Unlock – CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="3bf6c-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

