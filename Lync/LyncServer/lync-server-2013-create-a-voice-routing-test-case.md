---
title: 'Lync Server 2013: Создание тестового случая маршрутизации голосовой связи'
description: 'Lync Server 2013: Создание тестового случая маршрутизации голосовых вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d81f4d39a6e3972ebf036fdaca59936f3f6b86bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562405"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="c734c-103">Создание тестового случая маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c734c-103">Create a voice routing test case in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c734c-104">_**Последнее изменение темы:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c734c-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="c734c-105">Создание тестового случая</span><span class="sxs-lookup"><span data-stu-id="c734c-105">To create a test case</span></span>

1.  <span data-ttu-id="c734c-106">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c734c-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c734c-107">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c734c-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c734c-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c734c-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c734c-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c734c-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c734c-110">В левой панели навигации щелкните элемент **Voice Routing (Маршрутизация голосовых вызовов)**, а затем элемент **Test Voice Routing (Проверить маршрутизацию голосовых вызовов)**.</span><span class="sxs-lookup"><span data-stu-id="c734c-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="c734c-111">На странице **Test Voice Routing (Проверка маршрутизации голосовых вызовов)** нажмите **New (Создать)**, чтобы создать новый тестовый случай.</span><span class="sxs-lookup"><span data-stu-id="c734c-111">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="c734c-112">В поле **Имя** введите уникальное имя для тестового случая.</span><span class="sxs-lookup"><span data-stu-id="c734c-112">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="c734c-113">Имя должно быть уникальным среди всех тестовых случаев маршрутизации голосовой связи в развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c734c-113">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="c734c-114">Длина может доставлять до 32 символов и может содержать любые буквенно-цифровые символы в дополнение к символам обратной косой черты ( \\ ), точки (.) или подчеркивания ( \_ ).</span><span class="sxs-lookup"><span data-stu-id="c734c-114">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="c734c-p104">В поле **Набираемый номер для проверки** введите набираемый номер, который следует использовать для проверки конфигурации маршрутизации, заданной в тестовом случае. В зависимости от абонентской группы, маршрута и политики голосовой связи этот номер будет нормализован и отображен как результат.</span><span class="sxs-lookup"><span data-stu-id="c734c-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="c734c-p105">В списке **Dial Plan (Абонентская группа)** выберите абонентскую группу, которую следует использовать при выполнении проверки. По умолчанию это глобальная абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="c734c-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="c734c-p106">В списке **Voice Policy (Политика голосовой связи)** выберите политику голосовой связи, которая должна использоваться при выполнении проверки. По умолчанию это глобальная политика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c734c-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="c734c-p107">В поле **Ожидаемое преобразование** введите телефонный номер в формате, который предполагается увидеть после преобразования. Это значение проверяемого телефонного номера после его преобразования первым правилом нормализации, которое соответствует выбранной абонентской группе. Если при выполнении тестового случая проверяемый номер не преобразуется в значение, указанное в поле **Ожидаемое преобразование**, то проверка завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="c734c-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="c734c-p108">В списке **Ожидаемый режим работы с ТСОП** можно выбрать запись режима работы с ТСОП, которая предположительно должна использоваться при выполнении тестового случая, в зависимости от указанной абонентской группы и политики голосовой связи (не обязательно). Если используется другая запись режима работы с ТСОП, то проверка завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="c734c-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="c734c-p109">В списке **Expected route (Ожидаемый маршрут)** можно выбрать маршрут голосовых вызовов, который предположительно должен использоваться при выполнении тестового случая (не обязательно). Если используется другой маршрут голосовых вызовов, то проверка завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="c734c-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="c734c-p110">Нажмите **Run (Выполнить)**, чтобы выполнить тестовый случай (не обязательно). результаты показаны в правой области страницы.</span><span class="sxs-lookup"><span data-stu-id="c734c-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="c734c-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c734c-130">Click **OK**.</span></span>

14. <span data-ttu-id="c734c-131">Нажмите кнопку **Зафиксировать**, а затем нажмите кнопку **Зафиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="c734c-131">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c734c-132">Всякий раз при создании тестового случая маршрутизации голосовой связи необходимо выполнять команду <STRONG>Зафиксировать все</STRONG>, чтобы опубликовать это изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c734c-132">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="c734c-133">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="c734c-133">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="c734c-134">Если абонентская абонентская абонентская Абонентская служба, используемая в тесте, нормализует номера телефонов, начинающиеся со знака плюса (например, + 12065551219), этот план может привести к сбою проверки маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="c734c-134">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="c734c-135">(Абонентская план и маршрут голосовых вызовов будут работать, а на самом деле Test-CsDialPlan будет успешным.</span><span class="sxs-lookup"><span data-stu-id="c734c-135">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="c734c-136">Однако проверка маршрутизации голосовых вызовов может закончиться с ошибками.) При тестировании маршрутов голосовой связи следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="c734c-136">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c734c-137">См. также</span><span class="sxs-lookup"><span data-stu-id="c734c-137">See Also</span></span>


[<span data-ttu-id="c734c-138">Экспорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c734c-138">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="c734c-139">Импорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c734c-139">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="c734c-140">Настройка абонентских планов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c734c-140">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="c734c-141">Настройка политик голосовой связи, записей использования PSTN и маршрутов голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c734c-141">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

