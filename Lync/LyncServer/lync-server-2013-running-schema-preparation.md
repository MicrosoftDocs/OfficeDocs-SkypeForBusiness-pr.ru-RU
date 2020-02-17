---
title: 'Lync Server 2013: выполнение подготовки схемы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c58f50cb5c4668525450c4aa95b4a00513d5fc17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="b8e87-102">Выполнение подготовки схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8e87-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8e87-103">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="b8e87-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="b8e87-104">С помощью командлетов Setup или Командная консоль командной консоли Lync Server можно подготовить схему Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b8e87-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="b8e87-105">Командлет, расширяющий схему Active Directory, — **Install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8e87-106">Командлет подготовки схемы (<STRONG>Install-CsAdServerSchema</STRONG>) должен получить доступ к хозяину схемы, для которого необходимо, чтобы служба удаленного реестра была запущена, а ключ удаленного реестра был включен.</span><span class="sxs-lookup"><span data-stu-id="b8e87-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="b8e87-107">Если служба удаленного реестра не может быть включена на хозяине схемы, можно выполнить командлет локально на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="b8e87-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="b8e87-108">Сведения об удаленном доступе к реестру содержатся в статье базы знаний Майкрософт 314837, "как управлять удаленным доступом к реестру <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>" в.</span><span class="sxs-lookup"><span data-stu-id="b8e87-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="b8e87-109">После завершения подготовки схемы вручную убедитесь, что раздел схемы реплицирован, прежде чем переходить к подготовке леса.</span><span class="sxs-lookup"><span data-stu-id="b8e87-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="b8e87-110">Дополнительные сведения см. [в статье Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b8e87-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="b8e87-111">Подготовка схемы текущего леса с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="b8e87-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="b8e87-112">Войдите на сервер в лесу как член группы "Администраторы схемы" и с правами администратора на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="b8e87-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="b8e87-113">В установочной папке или на носителе Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="b8e87-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="b8e87-114">Будет предложено установить распространяемый пакет Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="b8e87-115">Появится диалоговое окно установки Lync Server 2013, в котором вы можете указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8e87-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="b8e87-116">Оставьте расположение по умолчанию или нажмите кнопку **Обзор**, чтобы выбрать другое расположение, а затем нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="b8e87-117">На странице лицензионного соглашения установите флажок **Я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="b8e87-118">Установщик устанавливает основные компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8e87-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="b8e87-119">Когда мастер развертывания будет готов, щелкните **подготовить Active Directory**и подождите, пока не будет определено состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="b8e87-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="b8e87-120">На **шаге 1: Prepare Schema**нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="b8e87-121">На странице **Подготовка схемы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="b8e87-122">На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, затем нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="b8e87-123">В столбце **действие** разверните узел " **Подготовка схемы**" \*\* \<\> ,\*\* найдите результат выполнения в конце каждой задачи, чтобы убедиться, что подготовка схемы завершена успешно, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="b8e87-124">Дождитесь завершения репликации Active Directory или принудительной репликации.</span><span class="sxs-lookup"><span data-stu-id="b8e87-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="b8e87-125">Вручную убедитесь, что изменения схемы реплицированы на все остальные контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="b8e87-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="b8e87-126">Дополнительные сведения см. [в статье Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b8e87-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="b8e87-127">Использование командлетов для подготовки схемы текущего леса</span><span class="sxs-lookup"><span data-stu-id="b8e87-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="b8e87-128">Войдите на компьютер в лесу как член группы "Администраторы схемы" и с правами администратора на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="b8e87-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="b8e87-129">Установите основные компоненты Lync Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="b8e87-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="b8e87-130">В установочной папке или на носителе Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8e87-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="b8e87-131">Будет предложено установить распространяемый пакет Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="b8e87-132">Появится диалоговое окно установки Lync Server 2013, в котором вы можете указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8e87-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="b8e87-133">Оставьте расположение по умолчанию или нажмите кнопку **Обзор**, чтобы выбрать другое расположение, а затем нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="b8e87-134">На странице лицензионного соглашения установите флажок **Я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="b8e87-135">Установщик устанавливает основные компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8e87-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="b8e87-136">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b8e87-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="b8e87-137">Выполняем</span><span class="sxs-lookup"><span data-stu-id="b8e87-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="b8e87-138">Если не указать параметр LDF, значение по умолчанию — это путь установки Lync Server 2013, который считывается из реестра.</span><span class="sxs-lookup"><span data-stu-id="b8e87-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="b8e87-139">Например:</span><span class="sxs-lookup"><span data-stu-id="b8e87-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="b8e87-140">Используйте следующий командлет, чтобы проверить, была ли завершена подготовка схемы.</span><span class="sxs-lookup"><span data-stu-id="b8e87-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="b8e87-141">Этот командлет возвращает значение **состояния\_\_\_версии схемы Current** , если подготовка схемы прошла успешно.</span><span class="sxs-lookup"><span data-stu-id="b8e87-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="b8e87-142">Дождитесь завершения репликации Active Directory или принудительной репликации.</span><span class="sxs-lookup"><span data-stu-id="b8e87-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="b8e87-143">Вручную убедитесь, что изменения схемы реплицированы на все остальные контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="b8e87-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="b8e87-144">Дополнительные сведения см. [в статье Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b8e87-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8e87-145">См. также</span><span class="sxs-lookup"><span data-stu-id="b8e87-145">See Also</span></span>


[<span data-ttu-id="b8e87-146">Проверка репликации схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8e87-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="b8e87-147">Подготовка схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8e87-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

