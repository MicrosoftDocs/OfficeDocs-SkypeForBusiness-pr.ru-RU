---
title: 'Lync Server 2013: выполнение подготовки схемы'
description: 'Lync Server 2013: выполнение подготовки схемы.'
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
ms.openlocfilehash: 0991bbff7f54f8b8b9eb01fc87f752e00f3dcbfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569365"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="6544b-103">Выполнение подготовки схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6544b-103">Running Active Directory schema preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6544b-104">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6544b-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6544b-105">С помощью командлетов Setup или Командная консоль командной консоли Lync Server можно подготовить схему Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6544b-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="6544b-106">Командлет, расширяющий схему Active Directory, — **Install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="6544b-106">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6544b-107">Командлет подготовки схемы (<STRONG>Install-CsAdServerSchema</STRONG>) должен получить доступ к хозяину схемы, для которого необходимо, чтобы служба удаленного реестра была запущена, а ключ удаленного реестра был включен.</span><span class="sxs-lookup"><span data-stu-id="6544b-107">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="6544b-108">Если служба удаленного реестра не может быть включена на хозяине схемы, можно выполнить командлет локально на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="6544b-108">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="6544b-109">Сведения об удаленном доступе к реестру содержатся в статье базы знаний Майкрософт 314837, "как управлять удаленным доступом к реестру" в <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> .</span><span class="sxs-lookup"><span data-stu-id="6544b-109">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="6544b-110">После завершения подготовки схемы вручную убедитесь, что раздел схемы реплицирован, прежде чем переходить к подготовке леса.</span><span class="sxs-lookup"><span data-stu-id="6544b-110">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="6544b-111">Дополнительные сведения см. [в статье Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="6544b-111">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="6544b-112">Подготовка схемы текущего леса с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="6544b-112">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="6544b-113">Войдите на сервер в лесу как член группы "Администраторы схемы" и с правами администратора на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="6544b-113">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="6544b-114">В папке или на носителе установки Lync Server 2013 запустите Setup.exe, чтобы запустить мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="6544b-114">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="6544b-115">Будет предложено установить распространяемый пакет Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="6544b-115">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="6544b-116">Появится диалоговое окно установки Lync Server 2013, в котором вы можете указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6544b-116">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="6544b-117">Оставьте расположение по умолчанию или нажмите кнопку **Обзор**, чтобы выбрать другое расположение, а затем нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="6544b-117">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="6544b-118">На странице лицензионного соглашения установите флажок **Я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6544b-118">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="6544b-119">Установщик устанавливает основные компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6544b-119">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="6544b-120">Когда мастер развертывания будет готов, щелкните **подготовить Active Directory**и подождите, пока не будет определено состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="6544b-120">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="6544b-121">На **шаге 1: Prepare Schema**нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6544b-121">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="6544b-122">На странице **Подготовка схемы** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6544b-122">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="6544b-123">На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, затем нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="6544b-123">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="6544b-124">В столбце **действие** разверните узел " **Подготовка схемы**", найдите **\<Success\>** результат выполнения в конце каждой задачи, чтобы убедиться, что подготовка схемы успешно завершена, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6544b-124">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="6544b-125">Дождитесь завершения репликации Active Directory или принудительной репликации.</span><span class="sxs-lookup"><span data-stu-id="6544b-125">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="6544b-126">Вручную убедитесь, что изменения схемы реплицированы на все остальные контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="6544b-126">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="6544b-127">Дополнительные сведения см. [в статье Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="6544b-127">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="6544b-128">Использование командлетов для подготовки схемы текущего леса</span><span class="sxs-lookup"><span data-stu-id="6544b-128">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="6544b-129">Войдите на компьютер в лесу как член группы "Администраторы схемы" и с правами администратора на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="6544b-129">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="6544b-130">Установите основные компоненты Lync Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="6544b-130">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="6544b-131">В папке или на носителе установки Lync Server 2013 запустите Setup.exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6544b-131">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="6544b-132">Будет предложено установить распространяемый пакет Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="6544b-132">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="6544b-133">Появится диалоговое окно установки Lync Server 2013, в котором вы можете указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6544b-133">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="6544b-134">Оставьте расположение по умолчанию или нажмите кнопку **Обзор**, чтобы выбрать другое расположение, а затем нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="6544b-134">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="6544b-135">На странице лицензионного соглашения установите флажок **Я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6544b-135">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="6544b-136">Установщик устанавливает основные компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6544b-136">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="6544b-137">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6544b-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="6544b-138">Выполняем</span><span class="sxs-lookup"><span data-stu-id="6544b-138">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="6544b-139">Если не указать параметр LDF, значение по умолчанию — это путь установки Lync Server 2013, который считывается из реестра.</span><span class="sxs-lookup"><span data-stu-id="6544b-139">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="6544b-140">Например:</span><span class="sxs-lookup"><span data-stu-id="6544b-140">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="6544b-141">Используйте следующий командлет, чтобы проверить, была ли завершена подготовка схемы.</span><span class="sxs-lookup"><span data-stu-id="6544b-141">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="6544b-142">Этот командлет возвращает значение \*\* \_ состояния версии схемы \_ \_ Current\*\* , если подготовка схемы прошла успешно.</span><span class="sxs-lookup"><span data-stu-id="6544b-142">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="6544b-143">Дождитесь завершения репликации Active Directory или принудительной репликации.</span><span class="sxs-lookup"><span data-stu-id="6544b-143">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="6544b-144">Вручную убедитесь, что изменения схемы реплицированы на все остальные контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="6544b-144">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="6544b-145">Дополнительные сведения см. [в статье Проверка репликации схемы Active Directory в Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="6544b-145">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6544b-146">См. также</span><span class="sxs-lookup"><span data-stu-id="6544b-146">See Also</span></span>


[<span data-ttu-id="6544b-147">Проверка репликации схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6544b-147">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="6544b-148">Подготовка схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6544b-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

