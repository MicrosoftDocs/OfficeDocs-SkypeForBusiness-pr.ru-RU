---
title: Создание или изменение диапазона ненаписаных номеров в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Корпоративная голосовая связь. Это влияет на то, как обрабатываются вызовы на ненаписаные номера.
ms.openlocfilehash: 180db35a5ea7c2c55dcdbbdcb3be70f868149d88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837089"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="e103c-104">Создание или изменение диапазона ненаписаных номеров в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e103c-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="e103c-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="e103c-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="e103c-106">Это влияет на то, как обрабатываются вызовы на ненаписаные номера.</span><span class="sxs-lookup"><span data-stu-id="e103c-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="e103c-107">Skype для бизнеса Server позволяет вам сказать, что происходит с входящие вызовы на телефонные номера, которые действительны для вашей организации, но не назначены пользователю или телефону.</span><span class="sxs-lookup"><span data-stu-id="e103c-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="e103c-108">Для обработки таких вызовов необходимо настроить таблицу ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="e103c-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="e103c-109">Таблицу можно использовать для маршрутов вызовов в приложение объявлений или на сервер exchange UM.</span><span class="sxs-lookup"><span data-stu-id="e103c-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="e103c-p104">Настройка таблицы неназначенных номеров зависит от того, как ее планируется использовать. Можно включить в эту таблицу все действительные добавочные номера для организации, только неназначенные добавочные номера или оба типа номеров. Таблица неназначенных номеров может включать как назначенные, так и неназначенные номера, но вызывается только в том случае, если вызывающий абонент набирает номер, который в текущий момент не назначен. Если в таблицу неназначенных номеров включить все действительные добавочные номера, то можно указать действие, которое должно выполняться, когда кто-либо увольняется из организации, и тогда не придется заново настраивать таблицу. Если в таблицу включить неназначенные добавочные номера, то можно настраивать действие, выполняющееся для определенных номеров. Например, если добавочный номер службы поддержки клиентов изменился, то старый номер можно включить в эту таблицу и назначить его объявлению, которое сообщает новый номер.</span><span class="sxs-lookup"><span data-stu-id="e103c-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="e103c-116">Настройка ненаписаных номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="e103c-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="e103c-117">Используйте одну из следующих процедур для настройки диапазонов ненаписаемых номеров для приложения "Объявление".</span><span class="sxs-lookup"><span data-stu-id="e103c-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e103c-118">Перед настройкой таблицы ненаписаных номеров в системе уже должны быть определены объявления или настроена автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="e103c-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="e103c-119">Когда кто-то звонит на ненаписаный номер, Skype для бизнеса Server выполняет поиск таблицы ненаписаных номеров сверху вниз и использует первый соответствующий диапазон.</span><span class="sxs-lookup"><span data-stu-id="e103c-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="e103c-120">Таким образом, действие, которое должно выполняться последним, должно быть задано для последнего диапазона в таблице.</span><span class="sxs-lookup"><span data-stu-id="e103c-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e103c-121">Использование панели управления Skype для бизнеса Server для настройки ненаписаных номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="e103c-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="e103c-122">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e103c-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e103c-123">Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="e103c-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e103c-124">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e103c-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e103c-125">В левой панели навигации щелкните **Функции голосовых служб**, а затем выберите **Неназначенный номер**.</span><span class="sxs-lookup"><span data-stu-id="e103c-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="e103c-126">На странице **Неназначенный номер** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e103c-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="e103c-p107">Чтобы создать новый диапазон номеров, выберите **Создать**. В поле **Имя** введите имя для этого диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="e103c-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="e103c-129">После записи нового диапазона неназначенных номеров в базе данных вы не сможете изменить имя диапазона.</span><span class="sxs-lookup"><span data-stu-id="e103c-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="e103c-p108">Чтобы изменить существующий диапазон номеров, введите его имя целиком (или же его часть) в поле поиска. В списке найденных диапазонов номеров щелкните нужное имя, выберите **Изменить**, аз щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="e103c-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e103c-132">В первом поле **Диапазон номеров** введите первый номер диапазона, а во втором поле **Диапазон номеров** введите последний номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="e103c-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="e103c-133">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="e103c-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="e103c-134">Если начальный или конечный номер диапазона содержит добавочный номер, то и начальный, и конечный номера диапазона должны содержать добавочный номер, который должен быть одинаковым для обоих номеров.</span><span class="sxs-lookup"><span data-stu-id="e103c-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="e103c-135">Номер должен соответствовать регулярному выражению (tel:)? \+ ()? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="e103c-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="e103c-136">Это означает, что число может начинаться со строки tel: (если не указать эту строку, она будет автоматически добавлена для вас), знак "плюс" (+) и цифры от 1 до 9.</span><span class="sxs-lookup"><span data-stu-id="e103c-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="e103c-137">Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</span><span class="sxs-lookup"><span data-stu-id="e103c-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="e103c-138">В диалоговом окне **Служба объявлений** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e103c-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="e103c-139">Щелкните **Объявление**.</span><span class="sxs-lookup"><span data-stu-id="e103c-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="e103c-140">Щелкните **Единая система обмена сообщениями Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e103c-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="e103c-141">Если при выполнении предыдущего шага вы щелкнули **Объявление**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e103c-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="e103c-142">а.</span><span class="sxs-lookup"><span data-stu-id="e103c-142">a.</span></span> <span data-ttu-id="e103c-143">В разделе **Полное доменное имя конечного сервера**, нажмите кнопку **Выбрать**, щелкните идентификатор службы приложения, выполняющую приложение объявлений, которое будет обрабатывать входящие вызовы для этого диапазона неназначенных номеров, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e103c-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="e103c-144">б.</span><span class="sxs-lookup"><span data-stu-id="e103c-144">b.</span></span> <span data-ttu-id="e103c-145">В окне **Объявление** щелкните объявление, которое будет воспроизводиться для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="e103c-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="e103c-146">Если при выполнении предыдущего шага вы щелкнули **Единая система обмена сообщениями Exchange**, в разделе **Номер телефона автосекретаря** нажмите кнопку **Выбрать**, щелкните номер телефона, который будет использоваться для данного диапазона неназначенных чисел, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e103c-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="e103c-147">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e103c-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="e103c-p112">Убедитесь, что на странице **Неназначенный номер** диапазоны неназначенных номеров расположены в требуемом порядке. Чтобы изменить расположение диапазона в таблице, выберите одно или несколько смежных имен в списке диапазонов, а затем щелкните стрелки вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="e103c-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e103c-150">Skype для бизнеса Server выполняет поиск таблицы ненаписаных номеров сверху вниз и использует первый диапазон, соответствующий нена назначенного номера.</span><span class="sxs-lookup"><span data-stu-id="e103c-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="e103c-151">При наличии перекрывающихся диапазонов и одного диапазона, который задает последнее возможное действие, убедитесь, что этот диапазон находится внизу списка.</span><span class="sxs-lookup"><span data-stu-id="e103c-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="e103c-152">Если диапазоны неназначенных номеров расположены в требуемом порядке, щелкните **Фиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="e103c-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e103c-153">Использование Skype для бизнеса Server Management Shell для настройки ненаправленных номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="e103c-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="e103c-154">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в делегирования разрешений на **установку.**</span><span class="sxs-lookup"><span data-stu-id="e103c-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e103c-155">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="e103c-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e103c-156">Используйте **New-CsUnassignedNumber** для создания нового диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="e103c-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="e103c-157">Используйте **Set-CsUnassignedNumber** для изменения существующего диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="e103c-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e103c-158">Если имеются перекрывающиеся диапазоны и требуется, чтобы эти диапазоны применялись в определенном порядке, включите параметр Priority.</span><span class="sxs-lookup"><span data-stu-id="e103c-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="e103c-159">В этом случае при звонке будет применяться диапазон, обладающий наибольшим приоритетом.</span><span class="sxs-lookup"><span data-stu-id="e103c-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="e103c-160">Значение 0 представляет собой наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="e103c-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="e103c-161">В командной строке выполните один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e103c-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="e103c-162">Чтобы создать диапазон номеров для службы оповещения, выполните:</span><span class="sxs-lookup"><span data-stu-id="e103c-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="e103c-163">Или: чтобы создать диапазон номеров для автосекретаря единая система обмена сообщениями Exchange, выполните:</span><span class="sxs-lookup"><span data-stu-id="e103c-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="e103c-164">Пример:</span><span class="sxs-lookup"><span data-stu-id="e103c-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="e103c-165">или</span><span class="sxs-lookup"><span data-stu-id="e103c-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="e103c-166">В следующем примере показывается, как можно изменить номера в существующем диапазоне неназначенных номеров:</span><span class="sxs-lookup"><span data-stu-id="e103c-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="e103c-167">Удаление диапазона ненаписаных номеров</span><span class="sxs-lookup"><span data-stu-id="e103c-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="e103c-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span><span class="sxs-lookup"><span data-stu-id="e103c-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="e103c-169">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e103c-169">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e103c-170">Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="e103c-170">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e103c-171">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e103c-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e103c-172">В левой панели навигации щелкните **Voice Features** (Функции голосовых служб) и затем выберите **Unassigned Number** (Неназначенный номер).</span><span class="sxs-lookup"><span data-stu-id="e103c-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="e103c-173">На странице **Unassigned Number** (Неназначенный номер) введите в поле поиска имя удаляемого диапазона неназначенных номеров или часть имени.</span><span class="sxs-lookup"><span data-stu-id="e103c-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="e103c-174">В списке диапазонов номеров выберите требуемое имя, а затем щелкните **Изменить** и **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e103c-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="e103c-175">Щелкните **Commit all** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="e103c-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="e103c-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span><span class="sxs-lookup"><span data-stu-id="e103c-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="e103c-177">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в делегирования разрешений на **установку.**</span><span class="sxs-lookup"><span data-stu-id="e103c-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e103c-178">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="e103c-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e103c-179">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e103c-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="e103c-180">Пример:</span><span class="sxs-lookup"><span data-stu-id="e103c-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="e103c-181">Дополнительные сведения о дополнительных параметрах см. в подстановке [Remove-CsCallParkOrbit.](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e103c-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e103c-182">См. также</span><span class="sxs-lookup"><span data-stu-id="e103c-182">See also</span></span>

[<span data-ttu-id="e103c-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e103c-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="e103c-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e103c-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="e103c-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e103c-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
