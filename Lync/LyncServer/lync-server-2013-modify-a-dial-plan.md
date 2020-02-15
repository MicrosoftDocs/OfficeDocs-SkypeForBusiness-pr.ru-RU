---
title: 'Lync Server 2013: Изменение абонентской группы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e20b05a85daa50003ca0062ea427473eae1bf95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="2cbb3-102">Изменение абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cbb3-102">Modify a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cbb3-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2cbb3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2cbb3-104">Чтобы изменить существующую абонентскую группу, выполните действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="2cbb3-105">Если вы хотите создать новую абонентскую схему, ознакомьтесь со статьей [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="2cbb3-106">Изменение абонентской группы</span><span class="sxs-lookup"><span data-stu-id="2cbb3-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="2cbb3-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2cbb3-108">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2cbb3-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2cbb3-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2cbb3-111">На панели навигации слева выберите **Маршрутизация телефонных звонков** и нажмите **Абонентская группа**.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="2cbb3-112">На странице **Dial Plan** (Абонентская группа) дважды щелкните имя абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cbb3-p104">Область абонентской группы и ее имя задаются при создании абонентской группы. Они не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="2cbb3-115">В поле **Simple name** (Простое имя) (содержит имя, отображаемое в поле **Name** (Имя)) окна **Edit Dial Plan** (Изменение абонентской группы) укажите описательное имя, которое указывает на сайт, службу или пользователя, к которым применяется абонентская группа (необязательно).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2cbb3-116"><STRONG>Простое имя</STRONG> должно быть уникальным среди всех абонентских группы в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="2cbb3-117">Длина не может превышать 256 символов Юникода, каждая из которых может быть буквенным или числовым символом, дефисом (-), точкой (.), знаком плюс (+) или символом подчеркивания (_).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="2cbb3-118">В поле <STRONG>Simple name</STRONG> (Простое имя) нельзя использовать пробелы.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="2cbb3-119">В поле **Description** (Описание) укажите дополнительные сведения об абонентской группе (необязательно).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="2cbb3-p106">Если эта абонентская группа будет использоваться в качестве региона для номеров доступа к конференц-связи, то укажите **Dial-in conferencing region** (Регион конференц-связи с телефонным подключением) (необязательно). В противном случае оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cbb3-122">Регионы конференц-связи с телефонным подключением требуются для связи номеров доступа к конференц-связи с телефонным подключением с одной абонентской группой или несколькими.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="2cbb3-123">Поле **External access prefix** (Префикс выхода на внешнюю линию) должно содержать значение только в том случае, если для выхода на внешнюю линию пользователям требуется набирать дополнительные цифры, например 9 (необязательно).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="2cbb3-124">Можно ввести значение префикса длиной до четырех символов (то есть \# \*,, и 0-9).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cbb3-125">При указании префикса выхода на внешнюю линию не требуется создавать новое правило нормализации для преобразования префикса.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="2cbb3-126">Настройте и свяжите правила нормализации для абонентской группы:</span><span class="sxs-lookup"><span data-stu-id="2cbb3-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="2cbb3-127">Чтобы выбрать одно или несколько правил из списка всех правил нормализации, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="2cbb3-128">В диалоговом окне **Select Normalization Rules** (Выбор правил нормализации) выделите правила, которые необходимо связать с абонентской группой, и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="2cbb3-129">Чтобы создать новое правило нормализации и связать его с абонентской группой, щелкните **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="2cbb3-130">Дополнительные сведения об определении нового правила приведены в статье [Определение правил нормализации в Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="2cbb3-131">Чтобы изменить правило нормализации, которое уже связано с абонентской группой, выделите имя правила и щелкните **Show details** (Подробности).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="2cbb3-132">Дополнительные сведения о редактировании правила приведены [в статье Определение правил нормализации в Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="2cbb3-133">Чтобы скопировать существующее правило нормализации и использовать его в качестве шаблона для нового правила, выделите имя правила и затем щелкните **Copy** (Копировать) и **Paste** (Вставить).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="2cbb3-134">Сведения о редактировании копии приведены в статье [Определение правил нормализации в Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="2cbb3-135">Чтобы удалить правило нормализации из абонентской группы, выделите имя правила и щелкните **Remove** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cbb3-136">Каждая абонентская группа должна иметь как минимум одно правило нормализации, связанное с ней.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="2cbb3-137">Для получения дополнительных сведений о том, как определить все правила нормализации, необходимые для абонентской группы, ознакомьтесь с <A href="lync-server-2013-dial-plans-and-normalization-rules.md">разбираемыми планами и правилами нормализации в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="2cbb3-p113">Убедитесь, что правила нормализации абонентской группы расположены в правильном порядке. Чтобы изменить расположение правила в списке, выделите имя правила и нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2cbb3-140">Lync Server выполняет обход списка правил нормализации сверху вниз и использует первое правило, которое соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="2cbb3-141">Если вы настроили абонентскую группу таким образом, что набираемый номер может соответствовать нескольким правилам нормализации, убедитесь, что после сортировки более строгие правила располагаются выше менее строгих правил.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="2cbb3-142">Правило нормализации по умолчанию " <STRONG>сохранить все</STRONG> " <STRONG>^ ({11}\d) $</STRONG> соответствует любому значению из 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="2cbb3-143">Например, если вы добавляете правило нормализации, которое соответствует номерам из 11 цифр, начинающимся с 1425, убедитесь, что для параметра <STRONG>сохранить все</STRONG> сортировка ниже более ограничительного правила <STRONG>^ (1425 \{7}d) $</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="2cbb3-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="2cbb3-p116">Введите номер для проверки абонентской группы и щелкните **Go** (Проверить) (необязательно). Результаты проверки отображаются в **Enter a number to test** (Введите номер для проверки).</span><span class="sxs-lookup"><span data-stu-id="2cbb3-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cbb3-146">Если абонентской группе не удается пройти проверку, то вы можете сохранить ее и настроить позже.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="2cbb3-147">Дополнительные сведения см <A href="lync-server-2013-test-voice-routing.md">в статье Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="2cbb3-148">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-148">Click **OK**.</span></span>

13. <span data-ttu-id="2cbb3-149">На странице **Абонентская группа** нажмите кнопку **Зафиксировать**, а затем нажмите кнопку **Зафиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cbb3-150">Для публикации изменений конфигурации необходимо выполнять команду <STRONG>Commit all</STRONG> (Фиксировать все) при каждом изменении или создании абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="2cbb3-151">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="2cbb3-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2cbb3-152">См. также</span><span class="sxs-lookup"><span data-stu-id="2cbb3-152">See Also</span></span>


[<span data-ttu-id="2cbb3-153">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cbb3-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="2cbb3-154">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cbb3-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="2cbb3-155">Определение правил нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cbb3-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

