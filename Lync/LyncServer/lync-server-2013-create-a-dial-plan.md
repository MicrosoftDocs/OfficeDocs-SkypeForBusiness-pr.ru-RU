---
title: 'Lync Server 2013: Создание абонентской группы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d4647f374fd65c0be52da111b7ef2d41c0faae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="866c9-102">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="866c9-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="866c9-103">_**Тема последнего изменения:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="866c9-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="866c9-104">Чтобы создать новую абонентскую группу, выполните действия, описанные в описанной ниже процедуре.</span><span class="sxs-lookup"><span data-stu-id="866c9-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="866c9-105">Если вы хотите изменить абонентскую группу, ознакомьтесь со сведениями [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="866c9-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="866c9-106">Создание абонентской группы</span><span class="sxs-lookup"><span data-stu-id="866c9-106">To create a dial plan</span></span>

1.  <span data-ttu-id="866c9-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="866c9-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="866c9-108">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="866c9-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="866c9-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="866c9-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="866c9-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="866c9-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="866c9-111">В левой панели навигации щелкните **Маршрутизация голосовой связи** и затем щелкните **Абонентская группа**.</span><span class="sxs-lookup"><span data-stu-id="866c9-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="866c9-112">На странице **Абонентская группа** нажмите кнопку **Создать**, а затем выберите область для абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="866c9-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="866c9-p104">**Абонентская группа сайта** применяется к целому сайту, кроме пользователей и групп, которым назначена пользовательская абонентская группа. Если выбрать параметр **Сайт** для области абонентской группы, необходимо выбрать сайт в диалоговом окне **Выбор сайта**. Если абонентская группа уже создана для сайта, он не отображается в диалоговом окне **Выбор сайта**.</span><span class="sxs-lookup"><span data-stu-id="866c9-p104">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan. If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box. If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="866c9-p105">**Абонентская группа пула** может применяться к шлюзу телефонной сети общего пользования (ТСОП) или регистратору. Если параметр **Пул** выбран в качестве области абонентской группы, выберите шлюз ТСОП или регистратора в диалоговом окне **Выбор службы**. Если абонентская группа уже создана для службы (шлюза ТСОП или регистратора), служба не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="866c9-p105">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar. If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box. If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="866c9-119">**Абонентская группа пользователя** может применяться к определенным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="866c9-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="866c9-120">После выбора области действия абонентской группы изменить ее нельзя.</span><span class="sxs-lookup"><span data-stu-id="866c9-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="866c9-p106">Если вы создаете абонентскую группу пользователя, введите ее имя в поле **Имя** в диалоговом окне **Создание абонентской группы**. После сохранения имени изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="866c9-p106">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="866c9-123">Для абонентских групп сайта в поле <STRONG>Имя</STRONG> автоматически добавляется имя сайта, его изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="866c9-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="866c9-124">Для абонентских групп пула в поле <STRONG>Имя</STRONG> автоматически добавляется имя шлюза ТСОП или регистратора, его изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="866c9-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="866c9-p107">В поле **Простое имя**, которое содержит имя, отображаемое в поле **Имя**, укажите описательное имя, которое указывает на сайт, службу или пользователя, к которым применяется абонентская группа (необязательно).</span><span class="sxs-lookup"><span data-stu-id="866c9-p107">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="866c9-127"><STRONG>Простое имя</STRONG> должно быть уникальным среди всех абонентских планов в рамках развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="866c9-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="866c9-128">Она не может содержать 256 символов Юникода, каждый из которых может представлять собой алфавитную или цифровую цифру, дефис (-), точку (.) или символ подчеркивания (_).</span><span class="sxs-lookup"><span data-stu-id="866c9-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="866c9-129">Неподдерживаемые символы включают пробелы и зарезервированные символы, как определено в RFC 3966 (. <STRONG></STRONG> http://www.ietf.org/rfc/rfc3966.txt)</span><span class="sxs-lookup"><span data-stu-id="866c9-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="866c9-130">Зарезервированные символы, которые <STRONG>не поддерживаются</STRONG> в <STRONG>простом имени</STRONG>, включают в себя следующие:</span><span class="sxs-lookup"><span data-stu-id="866c9-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="866c9-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="866c9-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="866c9-132">(Необязательно) В поле **Описание** можно ввести дополнительные сведения об абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="866c9-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="866c9-p110">Если эта абонентская группа будет использоваться в качестве региона для номеров доступа к конференц-связи, то укажите **Регион конференц-связи с телефонным подключением** (необязательно). В противном случае оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="866c9-p110">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="866c9-135">Регионы конференц-связи с телефонным подключением требуются для связи номеров доступа к конференц-связи с телефонным подключением с одной абонентской группой или несколькими.</span><span class="sxs-lookup"><span data-stu-id="866c9-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="866c9-136">Поле **Префикс внешнего доступа** должно содержать значение только в том случае, если для выхода на внешнюю линию пользователям требуется набирать дополнительные цифры, например 9 (необязательно).</span><span class="sxs-lookup"><span data-stu-id="866c9-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="866c9-137">Вы можете ввести значение префикса длиной до четырех символов (\# \*и 0-9).</span><span class="sxs-lookup"><span data-stu-id="866c9-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="866c9-138">При указании префикса выхода на внешнюю линию не требуется создавать новое правило нормализации для преобразования префикса.</span><span class="sxs-lookup"><span data-stu-id="866c9-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="866c9-139">Настройте и свяжите правила нормализации для абонентской группы:</span><span class="sxs-lookup"><span data-stu-id="866c9-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="866c9-140">Чтобы выбрать одно или несколько правил из списка всех правил нормализации, доступных в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="866c9-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="866c9-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="866c9-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="866c9-142">Чтобы создать новое правило нормализации и связать его с абонентской группой, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="866c9-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="866c9-143">Подробнее о том, как определить новое правило, можно найти [в разделе Определение правил нормализации в Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="866c9-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="866c9-144">Чтобы изменить правило нормализации, которое уже связано с абонентской группой, выделите имя правила и нажмите кнопку **Подробности**.</span><span class="sxs-lookup"><span data-stu-id="866c9-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="866c9-145">Подробнее об изменении правила можно найти в разделе [Определение правил нормализации в Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="866c9-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="866c9-146">Чтобы скопировать существующее правило нормализации и использовать его в качестве шаблона для нового правила, выделите имя правила и затем нажмите кнопку **Копировать** и **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="866c9-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="866c9-147">Подробнее об изменении копии [в разделе Определение правил нормализации в Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="866c9-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="866c9-148">Чтобы удалить правило нормализации из абонентской группы, выделите имя правила и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="866c9-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="866c9-149">Каждая абонентская группа должна иметь как минимум одно правило нормализации, связанное с ней.</span><span class="sxs-lookup"><span data-stu-id="866c9-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="866c9-150">Сведения о том, как определить все правила нормализации, необходимые для абонентской группы, приведены в разделе <A href="lync-server-2013-dial-plans-and-normalization-rules.md">планы звонков и нормализация в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="866c9-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="866c9-p117">Убедитесь, что правила нормализации абонентской группы расположены в правильном порядке. Чтобы изменить расположение правила в списке, выделите имя правила и нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="866c9-p117">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="866c9-153">Lync Server обходит список правил нормализации сверху вниз и использует первое правило, которое соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="866c9-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="866c9-154">Если вы настроили абонентскую группу таким образом, что набираемый номер может соответствовать нескольким правилам нормализации, убедитесь, что после сортировки более строгие правила располагаются выше, чем менее строгие правила.</span><span class="sxs-lookup"><span data-stu-id="866c9-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="866c9-155">По умолчанию правило " <STRONG>сохранить все</STRONG> нормализации <STRONG>^{11}(\d) $</STRONG> " соответствует любому 11-значному числу.</span><span class="sxs-lookup"><span data-stu-id="866c9-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="866c9-156">Например, если вы добавите правило нормализации <STRONG>, которое соответствует</STRONG> 11-значным числам, начинающимся с 1425, убедитесь, что они отсортированы ниже более ограниченного правила <STRONG>^ (1425 \{7}d) $</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="866c9-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="866c9-p120">Введите номер для проверки абонентской группы и щелкните **Проверить** (необязательно). Результаты проверки отображаются в **Введите номер для проверки**.</span><span class="sxs-lookup"><span data-stu-id="866c9-p120">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="866c9-159">Если абонентской группе не удается пройти проверку, то вы можете сохранить ее и настроить позже.</span><span class="sxs-lookup"><span data-stu-id="866c9-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="866c9-160">Подробные сведения можно найти <A href="lync-server-2013-test-voice-routing.md">в разделе Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="866c9-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="866c9-161">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="866c9-161">Click **OK**.</span></span>

14. <span data-ttu-id="866c9-162">На странице **Абонентская группа** нажмите кнопку **Сохранить**, а затем нажмите кнопку **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="866c9-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="866c9-163">Для публикации изменений конфигурации необходимо выполнять команду <STRONG>Сохранить все</STRONG> при каждом создании абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="866c9-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="866c9-164">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="866c9-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="866c9-165">См. также</span><span class="sxs-lookup"><span data-stu-id="866c9-165">See Also</span></span>


[<span data-ttu-id="866c9-166">Изменение абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="866c9-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="866c9-167">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="866c9-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="866c9-168">Определение правил нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="866c9-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

