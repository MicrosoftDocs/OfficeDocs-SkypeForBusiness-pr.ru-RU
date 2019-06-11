---
title: 'Lync Server 2013: проведение подготовки схемы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b743e5ef93b14279f5f2f16cb70241617a0c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="e3484-102">Проведение подготовки схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3484-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3484-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e3484-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e3484-104">Вы можете подготовить схему Active Directory с помощью командлетов командной консоли Setup или Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e3484-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="e3484-105">Командлет, расширяющий схему Active Directory, — **Install-ксадсерверсчема**.</span><span class="sxs-lookup"><span data-stu-id="e3484-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3484-106">Командлет подготовки схемы (<STRONG>Install-ксадсерверсчема</STRONG>) должен получить доступ к хозяину схемы, при этом требуется, чтобы служба удаленного реестра выполнялась, и что ключ удаленного реестра включен.</span><span class="sxs-lookup"><span data-stu-id="e3484-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="e3484-107">Если служба удаленного реестра не может быть включена на хозяине схемы, вы можете выполнить командлет локально на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="e3484-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="e3484-108">Подробнее об удаленном доступе к реестру можно найти в статье Microsoft Knowledge Base 314837, "как управлять удаленным доступом к реестру" по адресу <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span><span class="sxs-lookup"><span data-stu-id="e3484-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="e3484-109">После завершения подготовки схемы вручную убедитесь, что Секция схемы реплицирована, прежде чем переходить к подготовке леса.</span><span class="sxs-lookup"><span data-stu-id="e3484-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="e3484-110">Подробности можно найти [в разделе Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e3484-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="e3484-111">Подготовка схемы текущего леса с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="e3484-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="e3484-112">Войдите на сервер в лесу как член группы «Администраторы схемы» и с правами администратора на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="e3484-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="e3484-113">В установочной папке или носителе для Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="e3484-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="e3484-114">Если вам будет предложено установить распространяемый компонент Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="e3484-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="e3484-115">Диалоговое окно установки Lync Server 2013 предлагает указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3484-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="e3484-116">Выберите расположение по умолчанию или **перейдите** в нужное место, а затем нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="e3484-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="e3484-117">На странице Лицензионное соглашение установите флажок **я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3484-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="e3484-118">Установщик установит компоненты основных компонентов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3484-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="e3484-119">Когда мастер развертывания будет готов, нажмите кнопку **подготовить Active Directory**, а затем дождитесь, когда состояние развертывания будет определено.</span><span class="sxs-lookup"><span data-stu-id="e3484-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="e3484-120">На **шаге 1: подготовка схемы**нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e3484-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="e3484-121">На странице **Подготовка схемы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3484-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="e3484-122">На странице **выполнения команд** подождите, пока не появится сообщение **Состояние задачи: Завершено**, а затем нажмите **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="e3484-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="e3484-123">В столбце **Action (действие** ) разверните узел " \*\* \<\> \*\* **Подготовьте схему**", найдите результаты выполнения в конце каждой задачи, чтобы убедиться, что подготовка схемы завершилась успешно, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e3484-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="e3484-124">Дождитесь завершения репликации службы каталогов Active Directory или принудительной репликации.</span><span class="sxs-lookup"><span data-stu-id="e3484-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="e3484-125">Вручную убедитесь, что изменения схемы реплицированы на все другие контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="e3484-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="e3484-126">Подробности можно найти [в разделе Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e3484-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="e3484-127">Использование командлетов для подготовки схемы текущего леса</span><span class="sxs-lookup"><span data-stu-id="e3484-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="e3484-128">Войдите на компьютер в лесу как член группы "Администраторы схемы" и с правами администратора на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="e3484-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="e3484-129">Установите основные компоненты Lync Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="e3484-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="e3484-130">В установочной папке или носителе для Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3484-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="e3484-131">Если вам будет предложено установить распространяемый компонент Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="e3484-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="e3484-132">Диалоговое окно установки Lync Server 2013 предлагает указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3484-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="e3484-133">Выберите расположение по умолчанию или **перейдите** в нужное место, а затем нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="e3484-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="e3484-134">На странице Лицензионное соглашение установите флажок **я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3484-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="e3484-135">Установщик установит основные компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3484-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="e3484-136">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e3484-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="e3484-137">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e3484-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="e3484-138">Если параметр LDF не указан, значение по умолчанию — путь установки Lync Server 2013, который читается из реестра.</span><span class="sxs-lookup"><span data-stu-id="e3484-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="e3484-139">Например:</span><span class="sxs-lookup"><span data-stu-id="e3484-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="e3484-140">С помощью следующего командлета убедитесь в том, что подготовка схемы завершилась с завершением.</span><span class="sxs-lookup"><span data-stu-id="e3484-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="e3484-141">Этот командлет возвращает значение **состояния\_\_\_версии схемы Current** , если подготовка схемы завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="e3484-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="e3484-142">Дождитесь завершения репликации службы каталогов Active Directory или принудительной репликации.</span><span class="sxs-lookup"><span data-stu-id="e3484-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="e3484-143">Вручную убедитесь, что изменения схемы реплицированы на все другие контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="e3484-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="e3484-144">Подробности можно найти [в разделе Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e3484-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3484-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e3484-145">See Also</span></span>


[<span data-ttu-id="e3484-146">Проверка репликации схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3484-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="e3484-147">Подготовка схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3484-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

