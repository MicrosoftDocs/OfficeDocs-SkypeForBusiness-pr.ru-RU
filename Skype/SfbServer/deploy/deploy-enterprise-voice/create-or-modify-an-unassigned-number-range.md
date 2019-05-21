---
title: Создание и изменение неназначенного диапазона номеров в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Создавайте, изменяйте и удаляйте неназначенные диапазоны номеров для приложения объявления в Skype для бизнеса Server Enterprise. От этих действий зависит способ обработки вызовов на неназначенные номера.
ms.openlocfilehash: 5b9afa463d6eaff2f6ba3ed283d11556bd95bc03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286185"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="2e9ea-104">Создание и изменение неназначенного диапазона номеров в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e9ea-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="2e9ea-105">Создавайте, изменяйте и удаляйте неназначенные диапазоны номеров для приложения объявления в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="2e9ea-106">От этих действий зависит способ обработки вызовов на неназначенные номера.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="2e9ea-107">Skype для бизнеса Server позволяет сказать, что происходит с входящими звонками на номера телефонов, которые действительны для вашей организации, но не назначены пользователю или телефону.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="2e9ea-108">Для обработки таких вызовов следует задать таблицу неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="2e9ea-109">Вы можете использовать таблицу для маршрутизации вызовов в приложение объявлений или на сервер Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="2e9ea-p104">Настройка таблицы неназначенных номеров зависит от того, как ее планируется использовать. Можно включить в эту таблицу все действительные добавочные номера для организации, только неназначенные добавочные номера или оба типа номеров. Таблица неназначенных номеров может включать как назначенные, так и неназначенные номера, но вызывается только в том случае, если вызывающий абонент набирает номер, который в текущий момент не назначен. Если в таблицу неназначенных номеров включить все действительные добавочные номера, то можно указать действие, которое должно выполняться, когда кто-либо увольняется из организации, и тогда не придется заново настраивать таблицу. Если в таблицу включить неназначенные добавочные номера, то можно настраивать действие, выполняющееся для определенных номеров. Например, если добавочный номер службы поддержки клиентов изменился, то старый номер можно включить в эту таблицу и назначить его объявлению, которое сообщает новый номер.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="2e9ea-116">Настройка неназначенных телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="2e9ea-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="2e9ea-117">Используйте одну из описанных ниже процедур для настройки диапазонов номеров, неназначенных для приложения извещения.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2e9ea-118">Перед настройкой таблицы неназначенные номера необходимо, чтобы в системе уже было определено извещение или он настроен с помощью автосекретаря единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="2e9ea-119">Когда кто-то звонит на неназначенный номер, Skype для бизнеса Server ищет в таблице неназначенные номера сверху вниз и использует первый совпадающий диапазон.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="2e9ea-120">Поэтому действие, которое служит последним средством, следует задать для последнего диапазона в таблице.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="2e9ea-121">Настройка неназначенных телефонных номеров с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e9ea-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="2e9ea-p106">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-p106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="2e9ea-124">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2e9ea-125">В левой области навигации щелкните **Функции голосовой связи**, затем **Неназначенный номер**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="2e9ea-126">На странице **Неназначенный номер** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="2e9ea-p107">Для создания нового диапазона номеров щелкните **Создать**. В поле **Имя** введите идентификационное имя этого диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="2e9ea-129">После записи нового диапазона неназначенных номеров в базе данных вы не сможете изменить имя диапазона.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="2e9ea-p108">Для изменения существующего диапазона номеров полностью или частично введите его имя в поле поиска. В сформированном списке найденных диапазонов номеров щелкните требуемое имя и выберите **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2e9ea-132">В первом поле **Диапазон номеров** введите начальный номер диапазона, а во втором поле **Диапазон номеров** введите его конечный номер.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="2e9ea-133">Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="2e9ea-134">Если первый номер или последний номер диапазона содержит добавочный номер, то оба номера (первый и последний) должны содержать добавочный номер. Кроме того, добавочный номер должен быть одинаковым для первого и последнего номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="2e9ea-135">Номер должен соответствовать регулярному выражению (Tel:) _Км_ (\+) _км_ [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) _км_.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="2e9ea-136">Это означает, что номер может начинаться со строки Tel: (если вы не укажете эту строку, она будет добавлена автоматически), знак "плюс" (+) и цифра 1 – 9.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="2e9ea-137">Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате ";ext=добавочный_номер".</span><span class="sxs-lookup"><span data-stu-id="2e9ea-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="2e9ea-138">В поле **Служба оповещения** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="2e9ea-139">Щелкните **Оповещение**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="2e9ea-140">Щелкните **Единая система обмена сообщениями Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="2e9ea-141">Если на предыдущем шаге выбран вариант **Оповещение**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="2e9ea-142">a)</span><span class="sxs-lookup"><span data-stu-id="2e9ea-142">a.</span></span> <span data-ttu-id="2e9ea-143">В разделе **полное доменное имя целевого сервера**нажмите кнопку **выбрать**, выберите идентификатор службы приложения, на котором будет выполняться объявление для обработки входящих звонков с этим диапазоном неназначенных номеров, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="2e9ea-144">б)</span><span class="sxs-lookup"><span data-stu-id="2e9ea-144">b.</span></span> <span data-ttu-id="2e9ea-145">В разделе **Оповещение** выберите оповещение, которое требуется воспроизводить для даннго диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="2e9ea-146">Если на предыдущем шаге выбран вариант **Единая система обмена сообщениями Exchange**, в разделе **Номер автосекретаря** щелкните **Выбрать**, выберите номер телефона для данного диапазона неназначенных номеров, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="2e9ea-147">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="2e9ea-p112">Убедитесь в том, что на странице **Неназначенный номер** диапазоны неназначенных номеров расположены в требуемом порядке. Для изменения места диапазона в таблице выберите одно или несколько смежных имен в списке диапазонов, затем щелкните стрелку вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2e9ea-150">Skype для бизнеса Server ищет в таблице неназначенные номера сверху вниз и использует первый диапазон, который соответствует неназначенному номеру.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="2e9ea-151">Если при наличии перекрывающихся диапазонов один диапазон задает действие, которое служит последним средством, убедитесь в том, что этот диапазон находится внизу списка.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="2e9ea-152">Расположив диапазоны неназначенных номеров в требуемом порядке, щелкните **Выбрать все**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="2e9ea-153">Использование командной консоли Skype для бизнеса Server для настройки неназначенных телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="2e9ea-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="2e9ea-154">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя, описанными в разделе **Делегирование разрешений на настройку**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="2e9ea-155">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2e9ea-156">Используйте **New-ксунассигнеднумбер** для создания нового неназначенного диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="2e9ea-157">С помощью **Set-ксунассигнеднумбер** можно изменить существующий диапазон номеров, отличный от назначенного.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2e9ea-158">Если имеются перекрывающиеся диапазоны и требуется, чтобы эти диапазоны применялись в определенном порядке, включите параметр Priority.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="2e9ea-159">В этом случае при звонке будет применяться диапазон, обладающий наибольшим приоритетом.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="2e9ea-160">Значение 0 соответствует наивысшему приоритету.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="2e9ea-161">В командной строке выполните один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2e9ea-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="2e9ea-162">Чтобы создать диапазон номеров для службы оповещения, выполните:</span><span class="sxs-lookup"><span data-stu-id="2e9ea-162">To create a number range for an Announcement service, run:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="2e9ea-163">Или: чтобы создать диапазон номеров для автосекретаря единая система обмена сообщениями Exchange, выполните:</span><span class="sxs-lookup"><span data-stu-id="2e9ea-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="2e9ea-164">Например:</span><span class="sxs-lookup"><span data-stu-id="2e9ea-164">For example:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="2e9ea-165">Или</span><span class="sxs-lookup"><span data-stu-id="2e9ea-165">Or</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="2e9ea-166">В следующем примере показывается, как можно изменить номера в существующем диапазоне неназначенных номеров:</span><span class="sxs-lookup"><span data-stu-id="2e9ea-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="2e9ea-167">Удаление диапазона неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="2e9ea-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="2e9ea-168">Удаление неназначенного диапазона номеров с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e9ea-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="2e9ea-p116">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-p116">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="2e9ea-171">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2e9ea-172">В левой области навигации щелкните **Функции голосовой связи**, затем **Неназначенный номер**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="2e9ea-173">На странице **Неназначенный номер** полностью или частично введите в поле поиска имя диапазона неназначенных номеров, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="2e9ea-174">В сформированном списке диапазонов номеров выберите требуемое имя и щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="2e9ea-175">Щелкните **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="2e9ea-176">Использование среды управления Skype для бизнеса Server для удаления неназначенного диапазона номеров</span><span class="sxs-lookup"><span data-stu-id="2e9ea-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="2e9ea-177">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя, описанными в разделе **Делегирование разрешений на настройку**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="2e9ea-178">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2e9ea-179">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2e9ea-179">At the command line, type:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="2e9ea-180">Например:</span><span class="sxs-lookup"><span data-stu-id="2e9ea-180">For example:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="2e9ea-181">Подробнее о дополнительных параметрах можно найти в разделе [Remove-кскаллпаркорбит](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2e9ea-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2e9ea-182">См. также</span><span class="sxs-lookup"><span data-stu-id="2e9ea-182">See also</span></span>

[<span data-ttu-id="2e9ea-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="2e9ea-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="2e9ea-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="2e9ea-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="2e9ea-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="2e9ea-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
