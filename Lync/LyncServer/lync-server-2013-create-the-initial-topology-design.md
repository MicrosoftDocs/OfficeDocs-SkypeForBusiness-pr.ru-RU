---
title: 'Lync Server 2013: создание начальной структуры топологии'
description: 'Lync Server 2013: создание начальной схемы топологии.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c91bfe68a1de4a1f9862948edd708b8efa6a5c6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551095"
---
# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="28438-103">Создание первоначальной структуры топологии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28438-103">Create the initial topology design for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28438-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="28438-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="28438-105">После завершения установки Lync Server 2013, Planning Tool вы можете запустить средство планирования и начать разработку предлагаемой инфраструктуры Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28438-105">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28438-106">Средство планирования — это средство, основанное на мастере, с подробными руководствами для информирования процесса принятия решений при проектировании сайтов и топологии.</span><span class="sxs-lookup"><span data-stu-id="28438-106">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="28438-107">Этот раздел не является исчерпывающим руководством, но просто поможет вам приступить к работе с помощью средства планирования в сеансах создания проекта.</span><span class="sxs-lookup"><span data-stu-id="28438-107">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="28438-108">Приступая к работе с средством планирования и созданием начального дизайна</span><span class="sxs-lookup"><span data-stu-id="28438-108">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="28438-109">Запустите Lync Server 2013, средство планирования: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**, а затем щелкните **средство планирования**.</span><span class="sxs-lookup"><span data-stu-id="28438-109">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="28438-110">После запуска средства планирования откроется страница " **Добро пожаловать в средство планирования для Microsoft Lync Server 2013** ".</span><span class="sxs-lookup"><span data-stu-id="28438-110">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="28438-111">Выберите один из следующих параметров, чтобы приступить к разработке:</span><span class="sxs-lookup"><span data-stu-id="28438-111">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="28438-112">**Вариант 1: Начало работы**     Если щелкнуть приступить к **работе** , будет определен ряд вопросов по собеседованиям с соответствующими вариантами для определения критериев.</span><span class="sxs-lookup"><span data-stu-id="28438-112">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="28438-113">После выполнения начального опроса " **Получение начала работы** " вы переходите к разделу **проектирование сайтов** , чтобы определить архитектуру сайта.</span><span class="sxs-lookup"><span data-stu-id="28438-113">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="28438-114">Чтобы выполнить этот параметр, перейдите к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="28438-114">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="28438-115">**Вариант 2: дизайн сайтов**     При нажатии кнопки **дизайн сайтов** на начальной странице обходятся вопросы собеседования, представленные в разделе **Начало работы** .</span><span class="sxs-lookup"><span data-stu-id="28438-115">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="28438-116">Сведения, которые были собраны при ответе на вопросы по вопросам интервью в разделе **Начало работы** , задаются по умолчанию с помощью этого параметра.</span><span class="sxs-lookup"><span data-stu-id="28438-116">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="28438-117">Нажав кнопку **дизайн сайтов**, опытный разработчик может обойти первоначальное собеседование и при необходимости изменить значения по умолчанию на начальной странице **центральных сайтов** .</span><span class="sxs-lookup"><span data-stu-id="28438-117">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="28438-118">Чтобы выполнить этот параметр, пропустите шаги 3-5 и начните с шага 6.</span><span class="sxs-lookup"><span data-stu-id="28438-118">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="28438-119">**Вариант 3: отображение сохраненной топологии**     Если вы уже выполнили и сохранили топологию, используя предыдущее использование средства планирования, вы можете пропустить большинство этих действий и начать, открыв и отобразив топологию.</span><span class="sxs-lookup"><span data-stu-id="28438-119">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="28438-120">Вы также можете вносить изменения и обновления в топологию, повторно сохранять их, а затем экспортировать в Microsoft Excel или Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="28438-120">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="28438-121">Чтобы выполнить этот параметр, пропустите шаги 3-12 и начните с шага 13.</span><span class="sxs-lookup"><span data-stu-id="28438-121">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="28438-122">Чтобы начать разработку топологии Lync Server 2013, нажмите кнопку **начать работу** .</span><span class="sxs-lookup"><span data-stu-id="28438-122">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="28438-123">Ответьте на каждый раздел, выбрав соответствующие критерии для своего проекта, а затем нажмите кнопку **Далее** , чтобы перейти к следующей странице мастера.</span><span class="sxs-lookup"><span data-stu-id="28438-123">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="28438-124">Нажмите кнопку **назад** , чтобы внести изменения на предыдущих страницах.</span><span class="sxs-lookup"><span data-stu-id="28438-124">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="28438-125">Каждая страница содержит описание критериев выбора и рекомендации, основанные на рекомендуемых методиках и планировании мощности.</span><span class="sxs-lookup"><span data-stu-id="28438-125">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="28438-126">Если вам нужны дополнительные сведения <STRONG>, щелкните Дополнительные сведения,</STRONG> чтобы ознакомиться с подробными сведениями из документации по планированию Lync Server 2013 на веб-сайте Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="28438-126">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="28438-127">Для доступа к веб-сайту Microsoft TechNet необходимо подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="28438-127">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="28438-128">Выберите соответствующие параметры для своего макета.</span><span class="sxs-lookup"><span data-stu-id="28438-128">Select the appropriate options for your design.</span></span> <span data-ttu-id="28438-129">После определения начальных критериев страница подтвердит, что обзор функций завершен.</span><span class="sxs-lookup"><span data-stu-id="28438-129">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="28438-130">Нажмите кнопку **дизайн сайтов** , чтобы определить центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="28438-130">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28438-131">Каждая топология Lync Server 2013 будет иметь по крайней мере один центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="28438-131">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="28438-132">Ваш дизайн может иметь один центральный сайт, центральный сайт с несколькими сайтами филиалов, несколько центральных сайтов или несколько центральных сайтов с сайтами филиалов, связанными с каждым центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="28438-132">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="28438-133">В поле **имя сайта**введите имя, которое будет определять центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="28438-133">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="28438-134">В разделе **Пользователи сайта размещены**введите ожидаемое число локальных пользователей, которые будут размещены на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="28438-134">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="28438-135">В разделе **Пользователи облачного облака**введите ожидаемое количество одновременных пользователей в сети, которые будут размещены на этом центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="28438-135">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="28438-136">При необходимости измените параметры совместной работы в сети, пользователей, голосовых, дополнительных вариантов развертывания или серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="28438-136">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="28438-137">На этом шаге разработки вы можете выбрать или очистить параметры развертывания.</span><span class="sxs-lookup"><span data-stu-id="28438-137">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="28438-138">Тем не менее, вы можете настроить дополнительные параметры на более позднем этапе средства планирования.</span><span class="sxs-lookup"><span data-stu-id="28438-138">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="28438-139">Кроме того, существуют недоступные параметры, которые невозможно очистить.</span><span class="sxs-lookup"><span data-stu-id="28438-139">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="28438-140">Кроме того, может потребоваться очистить один вариант, чтобы очистить другой.</span><span class="sxs-lookup"><span data-stu-id="28438-140">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="28438-141">Например, при снятии флажка <STRONG>Корпоративная голосовая связь</STRONG> в разделе Voice параметры <STRONG>группы ответа</STRONG>, <STRONG>объявления</STRONG>и <STRONG>парковки звонков</STRONG> в разделе Application Applications (все функции корпоративной голосовой связи) также очищаются.</span><span class="sxs-lookup"><span data-stu-id="28438-141">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="28438-142">После определения имени сайта и числа пользователей нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="28438-142">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="28438-143">На следующих страницах запрашиваются сведения о доменах SIP, параметрах конференций, параметрах голосовой связи и инфраструктуре, единой системе обмена сообщениями Exchange, доступе внешних пользователей, параметрах сохраняемого чата, параметрах клиентов, параметрах выровнений и сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="28438-143">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="28438-144">Ответьте на эти вопросы соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="28438-144">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="28438-145">В последнем случае вам будет предложено создать другой центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="28438-145">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="28438-146">Если выбрано **значение Да**, средство планирования будет возвращено на страницу центральных сайтов.</span><span class="sxs-lookup"><span data-stu-id="28438-146">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="28438-147">Если выбрано значение **нет**, нажмите кнопку **Далее**, а затем нажмите кнопку **действия** , чтобы отобразить глобальное представление глобальной топологии.</span><span class="sxs-lookup"><span data-stu-id="28438-147">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="28438-148">Чтобы просмотреть существующую топологию, нажмите кнопку **Показать**.</span><span class="sxs-lookup"><span data-stu-id="28438-148">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="28438-149">Щелкните XML-файл, представляющий ранее сохраненную топологию, и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="28438-149">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="28438-150">Средство планирования отображает страницу глобальной топологии.</span><span class="sxs-lookup"><span data-stu-id="28438-150">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="28438-151">Теперь можно приступить к редактированию, обновлению или изменению топологии с помощью средств, доступных в средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="28438-151">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28438-152">См. также</span><span class="sxs-lookup"><span data-stu-id="28438-152">See Also</span></span>


[<span data-ttu-id="28438-153">Редактирование макета в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28438-153">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

