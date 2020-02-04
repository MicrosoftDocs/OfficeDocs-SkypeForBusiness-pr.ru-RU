---
title: 'Lync Server 2013: запуск тестовых случаев голосовой маршрутизации'
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
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="53ede-102">Запуск тестовых случаев маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53ede-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53ede-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="53ede-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="53ede-104">Вы можете выполнить все тестовые случаи в наборе тестовых случаев голосовой маршрутизации или выполнить один или несколько выбранных тестовых случаев.</span><span class="sxs-lookup"><span data-stu-id="53ede-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="53ede-105">Выполнение всех тестовых случаев голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="53ede-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="53ede-106">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="53ede-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="53ede-107">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="53ede-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="53ede-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53ede-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53ede-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="53ede-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53ede-110">На панели навигации слева выберите пункт **Маршрутизация голосовых сообщений** и нажмите кнопку **проверить голосовую связь**.</span><span class="sxs-lookup"><span data-stu-id="53ede-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="53ede-111">На странице **Проверка маршрутизации голосовой связи** нажмите кнопку **действие** , а затем выберите команду **выполнить все**.</span><span class="sxs-lookup"><span data-stu-id="53ede-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="53ede-112">Состояние прохождения или сбоя каждого тестового случая отображается в столбце " **успех** " или "сбой".</span><span class="sxs-lookup"><span data-stu-id="53ede-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="53ede-113">Если тестовый случай еще не выполнен, в столбце " **успех или сбой** " отображается значение "н/д".</span><span class="sxs-lookup"><span data-stu-id="53ede-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="53ede-114">Необязательно Чтобы просмотреть подробные результаты по каждому тестовому случаю, дважды щелкните имя тестового случая.</span><span class="sxs-lookup"><span data-stu-id="53ede-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="53ede-115">Результаты отображаются в области, затененной в правой части страницы " **Изменение тестового случая** ".</span><span class="sxs-lookup"><span data-stu-id="53ede-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="53ede-116">**Результат теста:** Общее состояние теста "пройден" или "сбой" при выполнении тестового случая.</span><span class="sxs-lookup"><span data-stu-id="53ede-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="53ede-117">**Правило нормализации:** Первое правило нормализации в абонентской группе, выбранном для этого тестового случая, которое соответствует номеру набора (значение в поле " **проверяемый номер** ").</span><span class="sxs-lookup"><span data-stu-id="53ede-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="53ede-118">**Нормализованный номер:** Значение набора номера после того, как оно было преобразовано в правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="53ede-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="53ede-119">**Использование первой PSTN:** Первая запись использования коммутируемой телефонной сети (КТСОП) в политике голосовой связи, выбранной для этого тестового случая, который соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="53ede-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="53ede-120">**Первый маршрут:** Первый маршрут голосовой связи в первой записи использования КТСОП, который соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="53ede-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="53ede-121"><STRONG>Ожидаемая запись использования PSTN</STRONG> и поля <STRONG>ожидаемых маршрутов</STRONG> являются необязательными в конфигурации тестового случая голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="53ede-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="53ede-122">Если в тестовом случае не указаны эти значения, соответствующее поле в результатах теста будет пустым.</span><span class="sxs-lookup"><span data-stu-id="53ede-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="53ede-123">Выполнение одной или нескольких выбранных тестовых случаев голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="53ede-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="53ede-124">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="53ede-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="53ede-125">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="53ede-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="53ede-126">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53ede-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53ede-127">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="53ede-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53ede-128">На панели навигации слева выберите пункт **Маршрутизация голосовых сообщений**и нажмите кнопку **Проверка маршрутизации голоса**.</span><span class="sxs-lookup"><span data-stu-id="53ede-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="53ede-129">На странице **Проверка маршрутизации голоса** выберите имена тестовых случаев, которые нужно выполнить.</span><span class="sxs-lookup"><span data-stu-id="53ede-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="53ede-130">В меню **действия** выберите команду **выполнить выбрано**.</span><span class="sxs-lookup"><span data-stu-id="53ede-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="53ede-131">Состояние прохождения или сбоя каждого тестового случая отображается в столбце " **успех** " или "сбой".</span><span class="sxs-lookup"><span data-stu-id="53ede-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="53ede-132">Если тестовый случай еще не выполнен, в столбце " **успех или сбой** " отображается значение "н/д".</span><span class="sxs-lookup"><span data-stu-id="53ede-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="53ede-133">Необязательно Чтобы просмотреть подробные результаты по каждому тестовому случаю, дважды щелкните имя тестового случая.</span><span class="sxs-lookup"><span data-stu-id="53ede-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="53ede-134">Результаты отображаются в области, затененной в правой части страницы " **Изменение тестового случая** ".</span><span class="sxs-lookup"><span data-stu-id="53ede-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="53ede-135">**Результат теста:** Общее состояние теста "пройден" или "сбой" при выполнении тестового случая.</span><span class="sxs-lookup"><span data-stu-id="53ede-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="53ede-136">**Правило нормализации:** Первое правило нормализации в абонентской группе, выбранном для этого тестового случая, которое соответствует номеру набора (значение в поле " **проверяемый номер** ").</span><span class="sxs-lookup"><span data-stu-id="53ede-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="53ede-137">**Нормализованный номер:** Значение набора номера после того, как оно было преобразовано в правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="53ede-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="53ede-138">**Использование первой PSTN:** Первая запись использования КТСОП в политике голосовой связи, выбранной для этого тестового случая, который соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="53ede-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="53ede-139">**Первый маршрут:** Первый маршрут голосовой связи в первой записи использования КТСОП, который соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="53ede-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="53ede-140"><STRONG>Ожидаемая запись использования PSTN</STRONG> и поля <STRONG>ожидаемых маршрутов</STRONG> являются необязательными в конфигурации тестового случая голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="53ede-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="53ede-141">Если в тестовом случае не указаны эти значения, соответствующее поле в результатах теста будет пустым.</span><span class="sxs-lookup"><span data-stu-id="53ede-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53ede-142">См. также</span><span class="sxs-lookup"><span data-stu-id="53ede-142">See Also</span></span>


[<span data-ttu-id="53ede-143">Тестирование голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53ede-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="53ede-144">Проведение тестов маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53ede-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

