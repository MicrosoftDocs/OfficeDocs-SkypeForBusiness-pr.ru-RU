---
title: 'Lync Server 2013: выполнение подготовки леса'
description: 'Lync Server 2013: запуск подготовки леса.'
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
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577765"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="7fb3b-103">Выполнение подготовки леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fb3b-103">Running forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fb3b-104">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="7fb3b-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="7fb3b-105">Для подготовки леса можно использовать командлеты Setup или Командная консоль командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="7fb3b-106">Для подготовки леса используется командлет **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-106">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="7fb3b-107">После подготовки леса необходимо проверить, что глобальные параметры были реплицированы, прежде чем переходить к подготовке домена.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-107">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="7fb3b-108">Использование программы установки для подготовки леса</span><span class="sxs-lookup"><span data-stu-id="7fb3b-108">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="7fb3b-109">Войдите в компьютер, присоединенный к домену, как член группы администраторов домена для корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-109">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="7fb3b-110">В папке или на носителе установки Lync Server 2013 запустите Setup.exe, чтобы запустить мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="7fb3b-111">Нажмите **Prepare Active Directory (Подготовка Active Directory)** и подождите, пока будет определено состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="7fb3b-112">В разделе **Step 3: Prepare Current Forest (Шаг 3. Подготовка текущего леса)** нажмите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-112">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="7fb3b-113">На странице **Prepare Forest (Подготовка леса)** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-113">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7fb3b-114">Подготовка леса позволяет выбрать место размещения универсальных групп для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-114">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="7fb3b-115">Выбирайте место в соответствии с требованиями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-115">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="7fb3b-116">На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, а затем нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-116">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="7fb3b-117">В столбце **действие** разверните узел **Подготовка леса**, найдите **\<Success\>** результат выполнения в конце каждой задачи, чтобы убедиться, что подготовка леса выполнена успешно, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-117">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="7fb3b-p103">Подождите, пока выполнится репликация Active Directory, или принудительно выполните репликацию во все контроллеры домена, перечисленные в оснастке **Active Directory — сайты и службы** для контроллера корневого домена леса, прежде чем приступить к подготовке домена. Принудительная репликация между контроллерами доменов во всех сайтах приведет к выполнению репликации в сайтах за несколько минут.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="7fb3b-120">Использование командлетов для подготовки леса</span><span class="sxs-lookup"><span data-stu-id="7fb3b-120">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="7fb3b-121">Войдите на компьютер, который присоединен к домену в качестве члена группы администраторов домена в корневом домене леса.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-121">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="7fb3b-122">Установите основные компоненты Lync Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-122">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="7fb3b-123">В папке или на носителе установки Lync Server 2013 запустите Setup.exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-123">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="7fb3b-124">Будет предложено установить распространяемый пакет Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-124">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="7fb3b-125">Появится диалоговое окно установки Lync Server 2013, в котором вы можете указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-125">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="7fb3b-126">Оставьте расположение по умолчанию или нажмите кнопку **Обзор**, чтобы выбрать другое расположение, а затем нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-126">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="7fb3b-127">На странице лицензионного соглашения установите флажок **Я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-127">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="7fb3b-128">Установщик устанавливает основные компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-128">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="7fb3b-129">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="7fb3b-130">Выполняем</span><span class="sxs-lookup"><span data-stu-id="7fb3b-130">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="7fb3b-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="7fb3b-131">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="7fb3b-p106">Если параметр GroupDomain не указан, по умолчанию используется локальный домен. Если универсальные группы были созданы ранее в домене, отличном от домена по умолчанию, необходимо задать значение параметра GroupDomain явно.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="7fb3b-134">Дождитесь выполнения репликации Active Directory или принудительно выполните репликацию во все контроллеры доменов, перечисленные в оснастке **Сайты и службы Active Directory** для контроллера корневого домена леса, перед тем как перейти к подготовке домена.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-134">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="7fb3b-p107">Убедитесь, что подготовка леса завершилась успешно. Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-p107">Verify that forest preparation was successful. Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="7fb3b-137">Этот командлет возвращает значение форестсеттингс, которое было \*\* \_ \_ \_ Готово\*\* , если подготовка леса выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="7fb3b-137">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7fb3b-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7fb3b-138">See Also</span></span>


[<span data-ttu-id="7fb3b-139">Использование командлетов для отмены подготовки леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fb3b-139">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="7fb3b-140">Подготовка леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fb3b-140">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

