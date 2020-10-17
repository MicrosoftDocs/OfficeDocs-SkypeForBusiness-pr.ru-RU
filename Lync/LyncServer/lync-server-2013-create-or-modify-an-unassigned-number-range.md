---
title: 'Lync Server 2013: создание или изменение диапазона неназначенных номеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4409a0c5688d131b34c792230c992142dd4f9c51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514686"
---
# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="2136f-102">Создание или изменение диапазона неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2136f-102">Create or modify an unassigned number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2136f-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2136f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2136f-104">Используйте одну из следующих процедур для настройки диапазонов неназначенных номеров для приложения оповещений.</span><span class="sxs-lookup"><span data-stu-id="2136f-104">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2136f-105">Перед настройкой таблицы неназначенных номеров требуется определить оповещения или настроить автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="2136f-105">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="2136f-106">Настройка неназначенных телефонных номеров с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="2136f-106">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="2136f-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2136f-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2136f-108">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2136f-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2136f-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2136f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2136f-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2136f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2136f-111">В левой панели навигации щелкните **Функции голосовых служб**, а затем выберите **Неназначенный номер**.</span><span class="sxs-lookup"><span data-stu-id="2136f-111">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="2136f-112">На странице **Неназначенный номер** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2136f-112">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2136f-p103">Чтобы создать новый диапазон номеров, выберите **Создать**. В поле **Имя** введите имя для этого диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="2136f-p103">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2136f-115">После записи нового диапазона неназначенных номеров в базе данных вы не сможете изменить имя диапазона.</span><span class="sxs-lookup"><span data-stu-id="2136f-115">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="2136f-p104">Чтобы изменить существующий диапазон номеров, введите его имя целиком (или же его часть) в поле поиска. В списке найденных диапазонов номеров щелкните нужное имя, выберите **Изменить**, аз щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="2136f-p104">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2136f-118">В первом поле **Диапазон номеров** введите первый номер диапазона, а во втором поле **Диапазон номеров** введите последний номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="2136f-118">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="2136f-119">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="2136f-119">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2136f-120">Если начальный или конечный номер диапазона содержит добавочный номер, то и начальный, и конечный номера диапазона должны содержать добавочный номер, который должен быть одинаковым для обоих номеров.</span><span class="sxs-lookup"><span data-stu-id="2136f-120">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2136f-121">Число должно быть согласовано с регулярным выражением (Tel:)? ( \+ )? [1-9] \d {0,17} (; ext = [1-9] \d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="2136f-121">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="2136f-122">Это означает, что номер должен начинаться со строки "tel:" (если эта строка не указана, она будет добавлена автоматически), знака "плюс" (+) и цифры от 1 до 9.</span><span class="sxs-lookup"><span data-stu-id="2136f-122">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="2136f-123">Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</span><span class="sxs-lookup"><span data-stu-id="2136f-123">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="2136f-124">В диалоговом окне **Служба объявлений** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2136f-124">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="2136f-125">Щелкните **Объявление**.</span><span class="sxs-lookup"><span data-stu-id="2136f-125">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="2136f-126">Щелкните **Единая система обмена сообщениями Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2136f-126">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="2136f-127">Если при выполнении предыдущего шага вы щелкнули **Объявление**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2136f-127">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="2136f-128">В разделе **Полное доменное имя конечного сервера**, нажмите кнопку **Выбрать**, щелкните идентификатор службы приложения, выполняющую приложение объявлений, которое будет обрабатывать входящие вызовы для этого диапазона неназначенных номеров, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2136f-128">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="2136f-129">В окне **Объявление** щелкните объявление, которое будет воспроизводиться для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="2136f-129">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="2136f-130">Если при выполнении предыдущего шага вы щелкнули**Единая система обмена сообщениями Exchange**, в разделе \*\* Номер телефона автосекретаря\*\* нажмите кнопку **Выбрать**, щелкните номер телефона, который будет использоваться для данного диапазона неназначенных чисел, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2136f-130">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="2136f-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2136f-131">Click **OK**.</span></span>

10. <span data-ttu-id="2136f-p106">Убедитесь, что на странице **Неназначенный номер** диапазоны неназначенных номеров расположены в требуемом порядке. Чтобы изменить расположение диапазона в таблице, выберите одно или несколько смежных имен в списке диапазонов, а затем щелкните стрелки вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="2136f-p106">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2136f-134">Lync Server выполняет поиск в таблице неназначенных номеров сверху вниз и использует первый диапазон, соответствующий неназначенному номеру.</span><span class="sxs-lookup"><span data-stu-id="2136f-134">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="2136f-135">При наличии перекрывающихся диапазонов и одного диапазона, который задает последнее возможное действие, убедитесь, что этот диапазон находится внизу списка.</span><span class="sxs-lookup"><span data-stu-id="2136f-135">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="2136f-136">Если диапазоны неназначенных номеров расположены в требуемом порядке, щелкните **Фиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="2136f-136">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="2136f-137">Использование Windows PowerShell для настройки неназначенных телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="2136f-137">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="2136f-138">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2136f-138">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2136f-139">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2136f-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2136f-140">Используйте **New-CsUnassignedNumber** для создания нового диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="2136f-140">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="2136f-141">Используйте **Set-CsUnassignedNumber** для изменения существующего диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="2136f-141">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2136f-p109">Если имеются перекрывающиеся диапазоны и требуется, чтобы эти диапазоны применялись в определенном порядке, включите параметр Priority. В этом случае при звонке будет применяться диапазон, обладающий наибольшим приоритетом.</span><span class="sxs-lookup"><span data-stu-id="2136f-p109">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="2136f-144">В командной строке выполните один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2136f-144">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="2136f-145">Чтобы создать диапазон номеров для службы оповещения, выполните:</span><span class="sxs-lookup"><span data-stu-id="2136f-145">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="2136f-146">Или: чтобы создать диапазон номеров для автосекретаря единая система обмена сообщениями Exchange, выполните:</span><span class="sxs-lookup"><span data-stu-id="2136f-146">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="2136f-147">Пример:</span><span class="sxs-lookup"><span data-stu-id="2136f-147">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="2136f-148">или</span><span class="sxs-lookup"><span data-stu-id="2136f-148">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="2136f-149">В следующем примере показывается, как можно изменить номера в существующем диапазоне неназначенных номеров:</span><span class="sxs-lookup"><span data-stu-id="2136f-149">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2136f-150">См. также</span><span class="sxs-lookup"><span data-stu-id="2136f-150">See Also</span></span>


[<span data-ttu-id="2136f-151">Удаление диапазона неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2136f-151">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="2136f-152">New — CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="2136f-152">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="2136f-153">Set — CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="2136f-153">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="2136f-154">Get — CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="2136f-154">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

