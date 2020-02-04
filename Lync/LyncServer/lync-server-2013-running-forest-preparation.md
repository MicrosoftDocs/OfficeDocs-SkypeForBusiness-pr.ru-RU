---
title: 'Lync Server 2013: проведение подготовки леса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="bc8d5-102">Проведение подготовки леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc8d5-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc8d5-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="bc8d5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="bc8d5-104">Для подготовки леса можно использовать командлеты командной консоли Setup или Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="bc8d5-105">Командлет, подготавливающий лес, — **Enable-ксадфорест**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="bc8d5-106">После подготовки леса необходимо убедиться, что глобальные параметры были реплицированы перед выполнением подготовки домена.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="bc8d5-107">Подготовка леса с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="bc8d5-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="bc8d5-108">Войдите в систему на компьютере, который входит в состав домена, в качестве участника группы администраторов предприятия для корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="bc8d5-109">В установочной папке или носителе для Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="bc8d5-110">Нажмите **Подготовить Active Directory** и подождите, пока будет определено состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="bc8d5-111">На **шаге 3: подготовка текущего леса**нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="bc8d5-112">На странице **Подготовка леса** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bc8d5-113">С помощью подготовки леса вы можете выбрать, куда следует поместить универсальные группы для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="bc8d5-114">Выберите расположение в соответствии с требованиями организации.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="bc8d5-115">На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, затем нажмите кнопку **Просмотр журнала**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="bc8d5-116">В столбце **Action (действие** ) разверните элемент " **Подготовка леса**", найдите \*\* \<\> результаты выполнения в\*\* конце каждой задачи, чтобы убедиться, что подготовка леса успешно завершена, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="bc8d5-117">Дождитесь завершения репликации Active Directory или принудительно выполните репликацию на все контроллеры домена, указанные в оснастке " **сайты и службы" в службе каталогов Active Directory** для корневого контроллера домена леса, перед тем как выполнять подготовку домена.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-117">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="bc8d5-118">Принудительная репликация между контроллерами домена на всех сайтах Active Directory для репликации в течение минут между сайтами.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-118">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="bc8d5-119">Использование командлетов для подготовки леса</span><span class="sxs-lookup"><span data-stu-id="bc8d5-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="bc8d5-120">Войдите в систему на компьютере, который входит в состав домена, в качестве члена группы администраторов домена в корневом домене леса.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="bc8d5-121">Установите основные компоненты Lync Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="bc8d5-122">В установочной папке или носителе для Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="bc8d5-123">Если вам будет предложено установить распространяемый компонент Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="bc8d5-124">Диалоговое окно установки Lync Server 2013 предлагает указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="bc8d5-125">Выберите расположение по умолчанию или **перейдите** в нужное место, а затем нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="bc8d5-126">На странице Лицензионное соглашение установите флажок **я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="bc8d5-127">Установщик установит основные компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="bc8d5-128">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="bc8d5-129">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bc8d5-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="bc8d5-130">Например:</span><span class="sxs-lookup"><span data-stu-id="bc8d5-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="bc8d5-131">Если параметр Граупдомаин не указан, значение по умолчанию — локальный домен.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-131">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span> <span data-ttu-id="bc8d5-132">Если универсальные группы были созданы ранее в домене, который не является доменом по умолчанию, необходимо явно задать параметр Граупдомаин.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-132">If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="bc8d5-133">Дождитесь завершения репликации Active Directory или принудительно выполните репликацию на все контроллеры домена, указанные в оснастке " **сайты и службы" в службе каталогов Active Directory** для корневого контроллера домена леса, перед тем как выполнять подготовку домена.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="bc8d5-134">Убедитесь, что подготовка леса выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-134">Verify that forest preparation was successful.</span></span> <span data-ttu-id="bc8d5-135">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bc8d5-135">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="bc8d5-136">Этот командлет возвращает значение **форестсеттингс\_\_состоянием\_"LC** ", если подготовка леса была выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc8d5-137">См. также</span><span class="sxs-lookup"><span data-stu-id="bc8d5-137">See Also</span></span>


[<span data-ttu-id="bc8d5-138">Использование командлетов для отмены подготовки леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc8d5-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="bc8d5-139">Подготовка леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc8d5-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

