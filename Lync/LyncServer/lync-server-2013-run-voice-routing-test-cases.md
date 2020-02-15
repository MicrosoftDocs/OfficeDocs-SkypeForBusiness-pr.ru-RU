---
title: 'Lync Server 2013: запуск тестовых примеров маршрутизации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df0a5ea6da9fad7f6a7e242bb522c493962fc603
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="efa98-102">Запуск тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa98-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efa98-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="efa98-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="efa98-104">Вы можете запустить все тестовые случаи в наборе тестовых примеров маршрутизации голосовой связи или выполнить один или несколько выбранных тестовых случаев.</span><span class="sxs-lookup"><span data-stu-id="efa98-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="efa98-105">Запуск всех тестовых случаев маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="efa98-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="efa98-106">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="efa98-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="efa98-107">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="efa98-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="efa98-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efa98-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="efa98-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="efa98-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="efa98-110">В левой области навигации щелкните элемент **Voice Routing** (Маршрутизация вызовов), а затем **Test Voice Routing** (Проверить маршрутизацию голосовых вызовов).</span><span class="sxs-lookup"><span data-stu-id="efa98-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="efa98-111">На странице **Test Voice Routing** (Проверка голосовых маршрутизации вызовов) в меню **Действие** выберите **Выполнить все**.</span><span class="sxs-lookup"><span data-stu-id="efa98-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="efa98-p103">Состояние прохождения или сбоя проверки каждого тестового случая отображается в столбце **Пройдено/сбой**. Если тестовый случай еще не запущен, в столбце **Пройдено/сбой** отображается состояние "Нет данных".</span><span class="sxs-lookup"><span data-stu-id="efa98-p103">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="efa98-p104">(Дополнительно). Чтобы увидеть подробные результаты для каждого тестового случая, дважды щелкните его название. Результаты отображаются в затененной области в правой части страницы **Edit Test Case** (Изменение тестового случая).</span><span class="sxs-lookup"><span data-stu-id="efa98-p104">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="efa98-116">**Результат теста:** Общее состояние успешного выполнения тестового случая или неудачи.</span><span class="sxs-lookup"><span data-stu-id="efa98-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="efa98-117">**Правило нормализации:** Первое правило нормализации в абонентской схеме, выбранном для этого тестового случая, которое соответствует набранному номеру (значение в поле " **проверяемое число** ").</span><span class="sxs-lookup"><span data-stu-id="efa98-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="efa98-118">**Нормализованный номер:** Значение набранного номера после его преобразования в правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="efa98-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="efa98-119">**Первая использование PSTN:** Первая запись использования телефонной сети общего пользования (PSTN) в политике голосовой связи, выбранной для этого тестового случая, которая соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="efa98-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="efa98-120">**Первый маршрут:** Первый маршрут голосовой связи в первой записи использования PSTN, который соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="efa98-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="efa98-p105">Поля <STRONG>Expected PSTN usage record</STRONG> (Ожидаемая запись режима работы с ТСОП) и <STRONG>Expected route</STRONG> (Ожидаемый маршрут) являются дополнительными в конфигурации тестовых случаев маршрутизации голосовых вызовов. Если в тестовом случае не указаны эти значения, соответствующие поля в результатах тестирования будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="efa98-p105">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="efa98-123">Запуск одного или нескольких выбранных тестовых случаев маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="efa98-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="efa98-124">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="efa98-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="efa98-125">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="efa98-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="efa98-126">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efa98-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="efa98-127">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="efa98-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="efa98-128">В левой панели навигации щелкните элемент **Маршрутизация голосовой связи** и затем элемент **Проверка маршрутизации голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="efa98-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="efa98-129">На странице **Проверка маршрутизации голосовых вызовов** щелкните имена тестовых случаев, которые требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="efa98-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="efa98-130">В меню **Действие** выберите пункт **Запустить выделенные**.</span><span class="sxs-lookup"><span data-stu-id="efa98-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="efa98-p108">Состояние прохождения или сбоя проверки каждого тестового случая отображается в столбце **Пройдено/сбой**. Если тестовый случай еще не запущен, в столбце **Пройдено/сбой** отображается состояние "Нет данных".</span><span class="sxs-lookup"><span data-stu-id="efa98-p108">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="efa98-p109">(Дополнительно). Чтобы увидеть подробные результаты для каждого тестового случая, дважды щелкните его название. Результаты отображаются в затененной области в правой части страницы **Edit Test Case** (Изменение тестового случая).</span><span class="sxs-lookup"><span data-stu-id="efa98-p109">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="efa98-135">**Результат теста:** Общее состояние успешного выполнения тестового случая или неудачи.</span><span class="sxs-lookup"><span data-stu-id="efa98-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="efa98-136">**Правило нормализации:** Первое правило нормализации в абонентской схеме, выбранном для этого тестового случая, которое соответствует набранному номеру (значение в поле " **проверяемое число** ").</span><span class="sxs-lookup"><span data-stu-id="efa98-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="efa98-137">**Нормализованный номер:** Значение набранного номера после его преобразования в правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="efa98-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="efa98-138">**Первая использование PSTN:** Первая запись использования PSTN в политике голосовой связи, выбранной для этого тестового случая, которая соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="efa98-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="efa98-139">**Первый маршрут:** Первый маршрут голосовой связи в первой записи использования PSTN, который соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="efa98-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="efa98-p110">Поля <STRONG>Expected PSTN usage record</STRONG> (Ожидаемая запись режима работы с ТСОП) и <STRONG>Expected route</STRONG> (Ожидаемый маршрут) являются дополнительными в конфигурации тестовых случаев маршрутизации голосовых вызовов. Если в тестовом случае не указаны эти значения, соответствующие поля в результатах тестирования будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="efa98-p110">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efa98-142">См. также</span><span class="sxs-lookup"><span data-stu-id="efa98-142">See Also</span></span>


[<span data-ttu-id="efa98-143">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa98-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="efa98-144">Выполнение тестов маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa98-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

