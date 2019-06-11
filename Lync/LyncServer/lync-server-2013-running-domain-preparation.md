---
title: 'Lync Server 2013: проведение подготовки домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fdd01b15fe5858129300c3a9f2f26c3d3de672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="6ace4-102">Проведение подготовки домена для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ace4-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ace4-103">_**Тема последнего изменения:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="6ace4-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="6ace4-104">Для подготовки доменов можно использовать командлеты командной консоли Setup или Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6ace4-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="6ace4-105">Командлет, подготавливающий домен, — **Enable-ксаддомаин**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="6ace4-106">Подготовка домена — это заключительный этап подготовки доменных служб Active Directory для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ace4-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="6ace4-107">Использование программы установки для подготовки доменов</span><span class="sxs-lookup"><span data-stu-id="6ace4-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="6ace4-108">Войдите на любой сервер домена, который является членом группы "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="6ace4-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="6ace4-109">В установочной папке или носителе для Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ace4-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="6ace4-110">Нажмите **Подготовить Active Directory** и подождите, пока будет определено состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="6ace4-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="6ace4-111">Когда появится окно **Шаг 5. Подготовка текущего домена**, нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="6ace4-112">На странице **Подготовка домена** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="6ace4-113">На странице **выполнения команд** подождите, пока не появится сообщение **Состояние задачи: Завершено**, а затем нажмите **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="6ace4-114">В столбце **Action (действие** ) разверните доменную версию **домена**, \*\* \<найдите\> \*\* результаты выполнения в конце каждой задачи, чтобы убедиться в том, что подготовка домена успешно завершена, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="6ace4-115">Дождитесь завершения репликации Active Directory или принудительно выполните репликацию на все контроллеры домена, указанные в оснастке "сайты и службы" Active Directory для корневого контроллера домена леса.</span><span class="sxs-lookup"><span data-stu-id="6ace4-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="6ace4-116">Использование командлетов для подготовки домена</span><span class="sxs-lookup"><span data-stu-id="6ace4-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="6ace4-117">Войдите на любой сервер домена, который является членом группы "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="6ace4-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="6ace4-118">Установите основные компоненты Lync Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="6ace4-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="6ace4-119">В установочной папке или носителе для Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ace4-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="6ace4-120">Если вам будет предложено установить распространяемый компонент Microsoft Visual C++, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="6ace4-121">Диалоговое окно установки Lync Server 2013 предлагает указать расположение для установки файлов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ace4-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="6ace4-122">Выберите расположение по умолчанию или **перейдите** в нужное место, а затем нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="6ace4-123">На странице Лицензионное соглашение установите флажок **я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="6ace4-124">Установщик установит основные компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ace4-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="6ace4-125">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6ace4-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="6ace4-126">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ace4-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="6ace4-127">Например:</span><span class="sxs-lookup"><span data-stu-id="6ace4-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="6ace4-128">Если параметр Domain не указан, по умолчанию используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="6ace4-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="6ace4-129">Убедитесь, что подготовка домена выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="6ace4-129">Verify that domain preparation was successful.</span></span> <span data-ttu-id="6ace4-130">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ace4-130">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="6ace4-131">Например:</span><span class="sxs-lookup"><span data-stu-id="6ace4-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ace4-132">Параметр Глобалсеттингсдомаинконтроллер позволяет указать, где хранятся глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="6ace4-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="6ace4-133">Если параметры хранятся в системном контейнере (обычно при развертывании обновлений без глобальных параметров, перенесенных в контейнер), вы определяете контроллер домена в корне леса Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6ace4-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="6ace4-134">Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу.</span><span class="sxs-lookup"><span data-stu-id="6ace4-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="6ace4-135">Если этот параметр не указан, командлет предполагает, что параметры хранятся в контейнере конфигурации и ссылаются на любой контроллер домена в доменных службах Active&nbsp;Directory.</span><span class="sxs-lookup"><span data-stu-id="6ace4-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="6ace4-136">Если параметр **domain** не указан, по умолчанию используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="6ace4-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="6ace4-137">Этот командлет возвращает значение **\_Домаинсеттингс состояния\_"\_LC** ", если подготовка домена выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="6ace4-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ace4-138">См. также</span><span class="sxs-lookup"><span data-stu-id="6ace4-138">See Also</span></span>


[<span data-ttu-id="6ace4-139">Использование командлетов для отмены подготовки доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ace4-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="6ace4-140">Подготовка доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ace4-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

