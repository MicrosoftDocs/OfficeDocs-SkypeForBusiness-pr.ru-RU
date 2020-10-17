---
title: 'Lync Server 2013: запуск тестовых примеров маршрутизации голосовой связи'
description: 'Lync Server 2013: выполнение тестовых случаев маршрутизации голосовых вызовов.'
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
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566795"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="cee96-103">Запуск тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cee96-103">Run voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cee96-104">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="cee96-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="cee96-105">Вы можете запустить все тестовые случаи в наборе тестовых примеров маршрутизации голосовой связи или выполнить один или несколько выбранных тестовых случаев.</span><span class="sxs-lookup"><span data-stu-id="cee96-105">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="cee96-106">Запуск всех тестовых случаев маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="cee96-106">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="cee96-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cee96-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cee96-108">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cee96-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cee96-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee96-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cee96-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cee96-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cee96-111">В левой области навигации щелкните элемент **Voice Routing** (Маршрутизация вызовов), а затем **Test Voice Routing** (Проверить маршрутизацию голосовых вызовов).</span><span class="sxs-lookup"><span data-stu-id="cee96-111">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="cee96-112">На странице **Test Voice Routing** (Проверка голосовых маршрутизации вызовов) в меню **Действие** выберите **Выполнить все**.</span><span class="sxs-lookup"><span data-stu-id="cee96-112">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="cee96-p103">Состояние прохождения или сбоя проверки каждого тестового случая отображается в столбце **Пройдено/сбой**. Если тестовый случай еще не запущен, в столбце **Пройдено/сбой** отображается состояние "Нет данных".</span><span class="sxs-lookup"><span data-stu-id="cee96-p103">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="cee96-p104">(Дополнительно). Чтобы увидеть подробные результаты для каждого тестового случая, дважды щелкните его название. Результаты отображаются в затененной области в правой части страницы **Edit Test Case** (Изменение тестового случая).</span><span class="sxs-lookup"><span data-stu-id="cee96-p104">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="cee96-117">**Результат теста:** Общее состояние успешного выполнения тестового случая или неудачи.</span><span class="sxs-lookup"><span data-stu-id="cee96-117">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="cee96-118">**Правило нормализации:** Первое правило нормализации в абонентской схеме, выбранном для этого тестового случая, которое соответствует набранному номеру (значение в поле " **проверяемое число** ").</span><span class="sxs-lookup"><span data-stu-id="cee96-118">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="cee96-119">**Нормализованный номер:** Значение набранного номера после его преобразования в правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="cee96-119">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="cee96-120">**Первая использование PSTN:** Первая запись использования телефонной сети общего пользования (PSTN) в политике голосовой связи, выбранной для этого тестового случая, которая соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="cee96-120">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="cee96-121">**Первый маршрут:** Первый маршрут голосовой связи в первой записи использования PSTN, который соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="cee96-121">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cee96-p105">Поля <STRONG>Expected PSTN usage record</STRONG> (Ожидаемая запись режима работы с ТСОП) и <STRONG>Expected route</STRONG> (Ожидаемый маршрут) являются дополнительными в конфигурации тестовых случаев маршрутизации голосовых вызовов. Если в тестовом случае не указаны эти значения, соответствующие поля в результатах тестирования будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="cee96-p105">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="cee96-124">Запуск одного или нескольких выбранных тестовых случаев маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="cee96-124">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="cee96-125">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cee96-125">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cee96-126">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cee96-126">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cee96-127">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee96-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cee96-128">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cee96-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cee96-129">В левой панели навигации щелкните элемент **Маршрутизация голосовой связи** и затем элемент **Проверка маршрутизации голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="cee96-129">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="cee96-130">На странице **Проверка маршрутизации голосовых вызовов** щелкните имена тестовых случаев, которые требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="cee96-130">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="cee96-131">В меню **Действие** выберите пункт **Запустить выделенные**.</span><span class="sxs-lookup"><span data-stu-id="cee96-131">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="cee96-p108">Состояние прохождения или сбоя проверки каждого тестового случая отображается в столбце **Пройдено/сбой**. Если тестовый случай еще не запущен, в столбце **Пройдено/сбой** отображается состояние "Нет данных".</span><span class="sxs-lookup"><span data-stu-id="cee96-p108">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="cee96-p109">(Дополнительно). Чтобы увидеть подробные результаты для каждого тестового случая, дважды щелкните его название. Результаты отображаются в затененной области в правой части страницы **Edit Test Case** (Изменение тестового случая).</span><span class="sxs-lookup"><span data-stu-id="cee96-p109">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="cee96-136">**Результат теста:** Общее состояние успешного выполнения тестового случая или неудачи.</span><span class="sxs-lookup"><span data-stu-id="cee96-136">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="cee96-137">**Правило нормализации:** Первое правило нормализации в абонентской схеме, выбранном для этого тестового случая, которое соответствует набранному номеру (значение в поле " **проверяемое число** ").</span><span class="sxs-lookup"><span data-stu-id="cee96-137">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="cee96-138">**Нормализованный номер:** Значение набранного номера после его преобразования в правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="cee96-138">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="cee96-139">**Первая использование PSTN:** Первая запись использования PSTN в политике голосовой связи, выбранной для этого тестового случая, которая соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="cee96-139">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="cee96-140">**Первый маршрут:** Первый маршрут голосовой связи в первой записи использования PSTN, который соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="cee96-140">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cee96-p110">Поля <STRONG>Expected PSTN usage record</STRONG> (Ожидаемая запись режима работы с ТСОП) и <STRONG>Expected route</STRONG> (Ожидаемый маршрут) являются дополнительными в конфигурации тестовых случаев маршрутизации голосовых вызовов. Если в тестовом случае не указаны эти значения, соответствующие поля в результатах тестирования будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="cee96-p110">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cee96-143">См. также</span><span class="sxs-lookup"><span data-stu-id="cee96-143">See Also</span></span>


[<span data-ttu-id="cee96-144">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cee96-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="cee96-145">Выполнение тестов маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cee96-145">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

