---
title: 'Lync Server 2013: выполнение проверок маршрутизации для неформальной голосовой связи'
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
ms.openlocfilehash: 2f916de228545a560c94bc45ea0a774ccc538c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="b980f-102">Выполнение неформальных проверок голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b980f-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b980f-103">_**Тема последнего изменения:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="b980f-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="b980f-104">Вы можете использовать диалоговое окно **Создание сведений о тестовом случае голосовой связи** для выполнения неформальных тестов перед созданием фактического тестового случая.</span><span class="sxs-lookup"><span data-stu-id="b980f-104">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="b980f-105">Если вы удовлетворены результатами теста, вы сможете сохранить его в виде формального тестового случая.</span><span class="sxs-lookup"><span data-stu-id="b980f-105">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="b980f-106">Выполнение неформального теста голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="b980f-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="b980f-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b980f-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b980f-108">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b980f-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b980f-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b980f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b980f-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b980f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b980f-111">На панели навигации слева выберите пункт **Маршрутизация голосовых сообщений**и нажмите кнопку **Проверка маршрутизации голоса**.</span><span class="sxs-lookup"><span data-stu-id="b980f-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="b980f-112">На странице **Проверка маршрутизации голоса** выберите команду **создать данные тестового случая голосовой маршрутизации**.</span><span class="sxs-lookup"><span data-stu-id="b980f-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="b980f-113">В поле **набранный номер** введите номер телефона, который вы хотите использовать для этого теста.</span><span class="sxs-lookup"><span data-stu-id="b980f-113">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="b980f-114">Этот номер будет нормализован и отображен в поле " **нормализованное число** " в области " **результаты** ".</span><span class="sxs-lookup"><span data-stu-id="b980f-114">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="b980f-115">В списке **абонентская группа** выберите абонентскую группу, которая будет использоваться для проверки набора номера.</span><span class="sxs-lookup"><span data-stu-id="b980f-115">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="b980f-116">По умолчанию используется глобальная абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="b980f-116">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="b980f-117">При выполнении теста в поле " **правило нормализации** " области **результатов** будет отображаться первое правило нормализации, совпадающее с числом с набором.</span><span class="sxs-lookup"><span data-stu-id="b980f-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="b980f-118">В списке **политика голосовой связи** выберите политику голосовой связи, которую нужно использовать для проверки набора номера.</span><span class="sxs-lookup"><span data-stu-id="b980f-118">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="b980f-119">По умолчанию используется глобальная политика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b980f-119">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="b980f-120">При выполнении теста в поле « **Использование** сети PSTN» в области **результатов** будет выводиться первая совпадающая запись использования PSTN в этой политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b980f-120">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="b980f-121">Кроме того, первый совпадающий маршрут голосовой связи, связанный с этой записью об использовании PSTN, будет отображаться в поле **первый маршрут** .</span><span class="sxs-lookup"><span data-stu-id="b980f-121">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="b980f-122">Необязательно Установите флажок **заполнить от пользователя** , если вы хотите проверить набранный номер по политике голосовой связи, назначенной определенному пользователю.</span><span class="sxs-lookup"><span data-stu-id="b980f-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="b980f-123">Нажмите кнопку **Обзор** , чтобы открыть диалоговое окно **Выбор пользователей корпоративной голосовой связи** .</span><span class="sxs-lookup"><span data-stu-id="b980f-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="b980f-124">Нажмите кнопку **найти** , чтобы отобразить список пользователей, имеющих доступ к корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b980f-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="b980f-125">Дважды щелкните имя пользователя, которому назначена политика голосовой связи, которую вы хотите использовать для этого теста.</span><span class="sxs-lookup"><span data-stu-id="b980f-125">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="b980f-126">Поле **политики** будет заполнено политикой голосовой связи, назначенной выбранному пользователю.</span><span class="sxs-lookup"><span data-stu-id="b980f-126">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="b980f-127">При выполнении теста в поле « **использование сети PSTN** » в области **результатов** будет выводиться первая совпадающая запись об использовании частной коммутируемой телефонной линии (PSTN) в этой политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b980f-127">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="b980f-128">Кроме того, первый совпадающий маршрут голосовой связи, связанный с этой записью об использовании PSTN, будет отображаться в поле **первый маршрут** .</span><span class="sxs-lookup"><span data-stu-id="b980f-128">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="b980f-129">Нажмите кнопку **выполнить** , чтобы запустить тестовый случай.</span><span class="sxs-lookup"><span data-stu-id="b980f-129">Click **Run** to run the test case.</span></span> <span data-ttu-id="b980f-130">Результаты отображаются на правой панели диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="b980f-130">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="b980f-131">Необязательно Нажмите кнопку **Сохранить как** , чтобы сохранить конфигурацию теста в формальном тестовом случае.</span><span class="sxs-lookup"><span data-stu-id="b980f-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="b980f-132">В поле **имя** диалогового окна **Сохранение сведений о тестовых сценариях голосовой маршрутизации** введите уникальное имя тестового случая.</span><span class="sxs-lookup"><span data-stu-id="b980f-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="b980f-133">Это имя должно быть уникальным среди всех тестовых случаев голосовой маршрутизации при развертывании вашей корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b980f-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="b980f-134">Длина может составлять до 32 знаков и может содержать любые алфавитно-цифровые символы, а также символ обратной\\косой черты (), точку (.) или\_символ подчеркивания ().</span><span class="sxs-lookup"><span data-stu-id="b980f-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="b980f-135">Обратите внимание, что оставшиеся поля в диалоговом окне " **Сохранение сведений о тестовых сценариях голосовой связи** " доступны только для чтения и предварительно заполнены из неформальных конфигураций тестов *и* результатов.</span><span class="sxs-lookup"><span data-stu-id="b980f-135">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="b980f-136">Убедитесь в том, что это конфигурация, которую вы хотите сохранить для тестового случая.</span><span class="sxs-lookup"><span data-stu-id="b980f-136">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b980f-137">Значения из результатов теста используются для предварительного заполнения полей в диалоговом окне <STRONG>Сохранение сведений о тестовых сценариях голосовой маршрутизации</STRONG> , как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="b980f-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="b980f-138"><STRONG>Ожидаемый перевод</STRONG> предварительно заполняется значением в поле " <STRONG>нормализованное число</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="b980f-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="b980f-139"><STRONG>Ожидаемый маршрут</STRONG> предварительно заполняется значением из первого поля <STRONG>Route</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b980f-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="b980f-140"><STRONG>Ожидаемая запись использования PSTN</STRONG> предзаполнена значением из <STRONG>первого поля использования КТСОП</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b980f-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="b980f-141">Если в ходе тестового запуска не было найдено совпадений для какого-либо из этих значений, соответствующее поле будет пустым в диалоговом окне " <STRONG>Сохранение сведений о тестовых сценариях голосовой маршрутизации</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="b980f-141">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="b980f-142">Нажмите кнопку **ОК** , чтобы сохранить тестовый случай, или кнопку **"Отмена"** , чтобы вернуться к диалоговому окну **Просмотр сведений о тестовом случае голосовой маршрутизации** для дальнейшей разработки теста перед его сохранением.</span><span class="sxs-lookup"><span data-stu-id="b980f-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="b980f-143">Нажмите кнопку **Сохранить**, а затем нажмите кнопку **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="b980f-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b980f-144">Каждый раз, когда вы создаете тестовый случай для голосовой маршрутизации, необходимо выполнить команду <STRONG>commit all</STRONG> для публикации тестового случая.</span><span class="sxs-lookup"><span data-stu-id="b980f-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="b980f-145">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="b980f-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b980f-146">См. также</span><span class="sxs-lookup"><span data-stu-id="b980f-146">See Also</span></span>


[<span data-ttu-id="b980f-147">Создание тестового примера маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b980f-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="b980f-148">Запуск тестовых случаев маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b980f-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="b980f-149">Экспорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b980f-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="b980f-150">Импорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b980f-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="b980f-151">Настройка абонентских групп в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b980f-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="b980f-152">Настройка политик голосовой связи, записей использования КТСОП и голосовых маршрутов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b980f-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

