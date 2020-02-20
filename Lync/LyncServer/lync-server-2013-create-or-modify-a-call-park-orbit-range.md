---
title: 'Lync Server 2013: создание или изменение диапазона орбит для парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddf119e62d7e7c8ecd71fc8c121a4a623440d6f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="15acb-102">Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15acb-102">Create or modify a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15acb-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="15acb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="15acb-104">Используйте одну из следующих процедур для создания или изменения диапазона парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="15acb-104">Use one of the following procedures to create or modify a call park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="15acb-105">Создание или изменение диапазона номеров для вызовов парковки с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="15acb-105">To use Lync Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="15acb-106">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="15acb-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="15acb-107">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="15acb-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="15acb-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15acb-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="15acb-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="15acb-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="15acb-110">В левой панели навигации выберите **Компоненты голосовой связи**, а затем щелкните **Парковка вызовов**.</span><span class="sxs-lookup"><span data-stu-id="15acb-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="15acb-111">На странице **Парковка вызовов** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="15acb-111">On the **Call Park** page, do one of the following:</span></span>
    
      - <span data-ttu-id="15acb-p103">Чтобы создать новый диапазон орбиты, щелкните **Создать**. В поле **Имя** введите имя, определяющее этот диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="15acb-p103">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="15acb-114">После фиксации диапазона орбиты в базе данных, это имя невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="15acb-114">After you commit the orbit range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="15acb-p104">Чтобы изменить существующий диапазон орбиты, введите все части имени диапазона орбиты в поле поиска. В списке результатов орбит щелкните нужную орбиту, щелкните **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="15acb-p104">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="15acb-117">В первом поле **Диапазон номеров** введите начальный номер диапазона добавочных номеров для этой орбиты парковки вызовов, а во втором поле **Диапазон номеров** введите конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="15acb-117">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="15acb-118">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="15acb-118">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="15acb-119">Длина значений начального и конечного номеров диапазона должна быть одинаковой.</span><span class="sxs-lookup"><span data-stu-id="15acb-119">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="15acb-p105">Диапазон орбиты должен быть уникальным и не должен перекрываться ни с одним другим диапазоном.</span><span class="sxs-lookup"><span data-stu-id="15acb-p105">The orbit range must be unique. This range cannot overlap with any other range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="15acb-122">Если диапазон орбиты начинается с символа \* или #, то диапазон должен быть больше 100.</span><span class="sxs-lookup"><span data-stu-id="15acb-122">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="15acb-123">Допустимые значения: должны быть согласованы со строкой\*регулярного выражения ([| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="15acb-123">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="15acb-124">Это означает, что значение должно представлять собою строку, которая начинается с символа "\*" или "#" либо с цифры в диапазоне от 1 до 9 (первым символом не может быть нуль).</span><span class="sxs-lookup"><span data-stu-id="15acb-124">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="15acb-125">Если первым символом является "\*" или "#", за ним должна следовать цифра в диапазоне от 1 до 9 (опять же, не нуль).</span><span class="sxs-lookup"><span data-stu-id="15acb-125">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="15acb-126">Последующими символами могут быть цифры от 0 до 9 до семи дополнительных символов (например, "#6000", "*92000", "* 95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="15acb-126">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "* 95551212", and "915551212").</span></span> <span data-ttu-id="15acb-127">Если же первым символом не является "\*" или "#", первым символом должна являться цифра в диапазоне от 1 до 9 (нуль не допускается), за которой следуют до восьми цифр в диапазоне от 0 до 9 (например:  "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="15acb-127">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span></P>
    > <LI>
    > <P><span data-ttu-id="15acb-p107">В пуле не должно быть более 50 000 орбит. Каждый диапазон орбиты обычно включает не более 100 орбит, но может быть гораздо больше, до 10 000 орбит. Например, вместо указания начального номера "7000000" и конечного номера  "8000000" рекомендуется указывать начальный номер "7000000" и конечный номер "7000100".</span><span class="sxs-lookup"><span data-stu-id="15acb-p107">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="15acb-p108">В поле **Полное доменное имя сервера назначения** выберите полное доменное имя или идентификатор службы приложений, где размещается приложение парковки вызовов. Все вызовы, припаркованные по номерам в диапазоне, заданном начальным и конечным номерами диапазона орбиты, будут маршрутизироваться на этот сервер или в этот пул.</span><span class="sxs-lookup"><span data-stu-id="15acb-p108">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7.  <span data-ttu-id="15acb-133">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="15acb-133">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="15acb-134">Использование Windows PowerShell для создания или изменения диапазона номеров для вызовов парковки</span><span class="sxs-lookup"><span data-stu-id="15acb-134">To use Windows PowerShell to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="15acb-135">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="15acb-135">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="15acb-136">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="15acb-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="15acb-137">Используйте командлет **New-CsCallParkOrbit** для создания нового диапазона номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="15acb-137">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="15acb-138">Используйте командлет **Set-CsCallParkOrbit** для изменения существующего диапазона номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="15acb-138">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="15acb-139">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="15acb-139">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    <span data-ttu-id="15acb-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="15acb-140">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    <span data-ttu-id="15acb-141">В приведенном ниже примере показано, как изменять номера в существующем диапазоне орбиты.</span><span class="sxs-lookup"><span data-stu-id="15acb-141">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15acb-142">См. также</span><span class="sxs-lookup"><span data-stu-id="15acb-142">See Also</span></span>


[<span data-ttu-id="15acb-143">Удаление диапазона орбит парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15acb-143">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="15acb-144">New — CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="15acb-144">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="15acb-145">Set — CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="15acb-145">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

