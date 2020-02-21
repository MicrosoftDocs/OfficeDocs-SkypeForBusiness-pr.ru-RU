---
title: 'Lync Server 2013: выполнение подготовки домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d22c35f4e1a2b117ffa765446a94c9a7d2b0fd0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="85961-102">Выполнение подготовки домена для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85961-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85961-103">_**Последнее изменение темы:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="85961-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="85961-104">Для подготовки доменов можно использовать командлеты Setup или Командная консоль командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85961-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="85961-105">Для подготовки домена используется командлет **Enable-CsAdDomain**.</span><span class="sxs-lookup"><span data-stu-id="85961-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="85961-106">Подготовка домена — это завершающий этап подготовки доменных служб Active Directory для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85961-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="85961-107">Подготовка доменов с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="85961-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="85961-108">Войдите на любой сервер в домене с помощью учетной записи, входящей в группу "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="85961-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="85961-109">В установочной папке или на носителе Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85961-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="85961-110">Щелкните **Подготовить Active Directory** и дождитесь, когда определится состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="85961-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="85961-111">Когда появится окно **Шаг 5. Подготовка текущего домена**, нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="85961-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="85961-112">На странице **Подготовка домена** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="85961-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="85961-113">На странице **Выполнение команд** найдите сообщение **Состояние задачи: завершено** и нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="85961-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="85961-114">В столбце **действие** разверните узел **Подготовка домена**, найдите \*\* \<\> результат выполнения в\*\* конце каждой задачи, чтобы убедиться, что подготовка домена выполнена успешно, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="85961-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="85961-115">Дождитесь, пока завершится репликация Active Directory, или выполните принудительную репликацию на все контроллеры домена, перечисленные в оснастке "Active Directory — сайты и службы" для контроллера корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="85961-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="85961-116">Использование командлетов для подготовки домена</span><span class="sxs-lookup"><span data-stu-id="85961-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="85961-117">Войдите на любой сервер в домене в качестве члена группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="85961-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="85961-118">Установите основные компоненты Lync Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="85961-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="85961-119">В установочной папке или на носителе Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85961-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="85961-120">Будет предложено установить распространяемый пакет Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="85961-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="85961-121">Появится диалоговое окно установки Lync Server 2013, в котором вы можете указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85961-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="85961-122">Оставьте расположение по умолчанию или нажмите кнопку **Обзор**, чтобы выбрать другое расположение, а затем нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="85961-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="85961-123">На странице лицензионного соглашения установите флажок **Я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="85961-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="85961-124">Установщик устанавливает основные компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85961-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="85961-125">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="85961-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="85961-126">Выполняем</span><span class="sxs-lookup"><span data-stu-id="85961-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="85961-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="85961-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="85961-128">Если не указать параметр Domain, значением по умолчанию будет локальный домен.</span><span class="sxs-lookup"><span data-stu-id="85961-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="85961-p104">Убедитесь, что подготовка домена завершилась успешно. Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="85961-p104">Verify that domain preparation was successful. Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="85961-131">Например:</span><span class="sxs-lookup"><span data-stu-id="85961-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85961-132">Параметр GlobalSettingsDomainController позволяет указать, где хранятся глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="85961-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="85961-133">Если параметры хранятся в контейнере System (это обычная ситуация при обновлении развертываний, когда глобальные параметры не переносятся в контейнер Configuration), определите контроллер домена в корне леса Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85961-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="85961-134">Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу.</span><span class="sxs-lookup"><span data-stu-id="85961-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="85961-135">Если не указать этот параметр, командлет предполагает, что параметры хранятся в контейнере конфигурации и ссылаются на любой контроллер домена в доменных службах Active&nbsp;Directory.</span><span class="sxs-lookup"><span data-stu-id="85961-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="85961-136">Если параметр **domain** не указан, по умолчанию используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="85961-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="85961-137">Этот командлет возвращает значение **\_домаинсеттингс\_\_** , которое было готово, если подготовка домена выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="85961-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85961-138">См. также</span><span class="sxs-lookup"><span data-stu-id="85961-138">See Also</span></span>


[<span data-ttu-id="85961-139">Использование командлетов для обратной подготовки домена для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85961-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="85961-140">Подготовка доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85961-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

