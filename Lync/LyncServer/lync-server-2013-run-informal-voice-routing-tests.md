---
title: 'Lync Server 2013: выполнение неформальных тестов маршрутизации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fd8c20adfa98a10bd0b9a89ad31dda37e4510e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511166"
---
# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="9e455-102">Выполнение неформальных тестов маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e455-102">Run informal voice routing tests in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e455-103">_**Последнее изменение темы:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="9e455-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="9e455-p101">С помощью диалогового окна **Create voice routing test case information (Создание информации для тестового случая маршрутизации голосовых вызовов)** можно выполнять неформальные тесты до создания фактического тестового случая. Когда вы будете удовлетворены результатом теста, можно будет сохранить его как формальный тестовый случай.</span><span class="sxs-lookup"><span data-stu-id="9e455-p101">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case. When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="9e455-106">Выполнение неформального теста маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="9e455-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="9e455-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9e455-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9e455-108">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9e455-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9e455-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e455-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9e455-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9e455-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9e455-111">В левой области навигации щелкните элемент **Voice Routing** (Маршрутизация вызовов), а затем **Test Voice Routing** (Проверить маршрутизацию голосовых вызовов).</span><span class="sxs-lookup"><span data-stu-id="9e455-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="9e455-112">На странице **Проверка маршрутизации голосовых вызовов** выберите **Создать информацию для тестового случая маршрутизации голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="9e455-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="9e455-p104">В поле **Набранный номер** введите телефонный номер, который будет использоваться для данного теста. Этот номер будет нормализован и отображен в поле **Нормализованный номер** в области **результатов**.</span><span class="sxs-lookup"><span data-stu-id="9e455-p104">In the **Dialed number** field, type in the phone number you want to use for this test. This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="9e455-p105">В списке **Абонентская группа** выберите абонентскую группу для тестирования набранного номера. По умолчанию это глобальная абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="9e455-p105">In the **Dial plan** list, select the dial plan to use for testing the dialed number. Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="9e455-117">При запуске теста в поле **Правило нормализации** в области **результатов** будет отображаться первое правило нормализации в этой абонентской группе, которое соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="9e455-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="9e455-p106">В списке **Политика голосовой связи** выберите политику голосовой связи, которая будет использоваться для тестирования набранного номера. По умолчанию это глобальная политика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9e455-p106">In the **Voice Policy** list, select the voice policy to use for testing the dialed number. Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="9e455-p107">При запуске теста в поле **Первый режим работы с ТСОП** в области **результатов** будет отображаться первая соответствующая запись режима работы с ТСОП в этой политике голосовой связи. Кроме того, в поле **Первый маршрут** будет отображаться первый соответствующий маршрут голосового вызова, связанный с этой записью режима работы с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="9e455-p107">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="9e455-122">Установите флажок **Заполнить от пользователя**, если предполагается тестировать набранный номер по отношению к политике голосовой связи, назначенной конкретному пользователю (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="9e455-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="9e455-123">Нажмите кнопку **Обзор**, чтобы отобразить диалоговое окно **выбора пользователей корпоративной голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="9e455-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="9e455-124">Нажмите кнопку **Поиск**, чтобы отобразить список пользователей, которым разрешена корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="9e455-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="9e455-p108">Дважды щелкните имя пользователя, чью назначенную политику голосовой связи планируется использовать для данного теста. Теперь в поле **Политика** появляется политика голосовой связи, назначенная выбранному пользователю.</span><span class="sxs-lookup"><span data-stu-id="9e455-p108">Double-click the user name whose assigned voice policy you want to use for this test. The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="9e455-p109">При запуске теста в поле **Первый режим работы с ТСОП** в области **результатов** будет отображаться первая соответствующая запись режима работы с ТСОП в этой политике голосовой связи. Кроме того, в поле **Первый маршрут** будет отображаться первый соответствующий маршрут голосового вызова, связанный с этой записью режима работы с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="9e455-p109">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="9e455-p110">Нажмите кнопку **Запустить**, чтобы запустить тестовый случай. Результаты показываются в правой области этого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="9e455-p110">Click **Run** to run the test case. The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="9e455-131">Нажмите **Сохранить как**, если вы хотите сохранить эту конфигурацию теста как формальный тестовый случай (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="9e455-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="9e455-132">В поле **Имя** диалогового окна **Сохранение информации тестового случая маршрутизации голосовых вызовов** введите уникальное имя для этого тестового случая.</span><span class="sxs-lookup"><span data-stu-id="9e455-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="9e455-133">Имя должно быть уникальным среди всех тестовых случаев маршрутизации голосовой связи в развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9e455-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="9e455-134">Длина может доставлять до 32 символов и может содержать любые буквенно-цифровые символы в дополнение к символам обратной косой черты ( \\ ), точки (.) или подчеркивания ( \_ ).</span><span class="sxs-lookup"><span data-stu-id="9e455-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="9e455-p112">Обратите внимание, что остальные поля диалогового окна **Сохранение информации тестового случая маршрутизации голосовых вызовов** предназначены только для чтения и предварительно заполняются из конфигурации неформального теста *и* результатов. Убедитесь. что это именно та конфигурация, которую требуется сохранить для тестового случая.</span><span class="sxs-lookup"><span data-stu-id="9e455-p112">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results. Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9e455-137">Значения из результатов теста используются для предварительного заполнения полей в диалоговом окне <STRONG>Сохранение информации тестового случая маршрутизации голосовых вызовов</STRONG>следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9e455-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="9e455-138">Поле <STRONG>Ожидаемое преобразование</STRONG> предварительно заполняется значением из поля <STRONG>Нормализованный номер</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9e455-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="9e455-139">Поле <STRONG>Ожидаемый маршрут</STRONG> предварительно заполняется значением поля <STRONG>Первый маршрут</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9e455-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="9e455-140">Поле <STRONG>Ожидаемая запись режима работы с ТСОП </STRONG> предварительно заполняется значением поля <STRONG>Первый режим работы с ТСОП</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9e455-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="9e455-p113">Если во время выполнения теста не будут найдены соответствия для каких-либо из этих значений, то соответствующее поле в диалоговом окне <STRONG>Сохранение информации тестового случая маршрутизации голосовых вызовов</STRONG> будет пустым.</span><span class="sxs-lookup"><span data-stu-id="9e455-p113">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.   </span></span></div>
    
    3.  <span data-ttu-id="9e455-142">Чтобы сохранить тестовый случай, нажмите кнопку **ОК**, а чтобы вернуться в диалоговое окно **Просмотр информации тестового случая маршрутизации голосовых вызовов** и продолжить разработку теста до его сохранения, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="9e455-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="9e455-143">Нажмите кнопку **Зафиксировать**, а затем нажмите кнопку **Зафиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="9e455-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e455-144">Всякий раз при создании тестового случая маршрутизации голосовых вызовов необходимо нажимать кнопку <STRONG>Зафиксировать все</STRONG>, чтобы опубликовать этот тестовый случай.</span><span class="sxs-lookup"><span data-stu-id="9e455-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="9e455-145">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="9e455-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e455-146">См. также</span><span class="sxs-lookup"><span data-stu-id="9e455-146">See Also</span></span>


[<span data-ttu-id="9e455-147">Создание тестового случая маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e455-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="9e455-148">Запуск тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e455-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="9e455-149">Экспорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e455-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="9e455-150">Импорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e455-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="9e455-151">Настройка абонентских планов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e455-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="9e455-152">Настройка политик голосовой связи, записей использования PSTN и маршрутов голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e455-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

