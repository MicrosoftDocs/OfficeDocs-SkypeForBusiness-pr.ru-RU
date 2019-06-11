---
title: 'Lync Server 2013: создание и изменение политики мобильности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d3f03735048ab4354db9653554b6227bb7399e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="16dd8-102">Создание и изменение политики Mobility Service в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16dd8-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16dd8-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="16dd8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="16dd8-104">Вы можете создать или изменить политику мобильности, чтобы позволить пользователям мобильных устройств использовать поддерживаемые возможности Lync, такие как обмен мгновенными сообщениями, присутствие и контакты.</span><span class="sxs-lookup"><span data-stu-id="16dd8-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="16dd8-105">Вы можете создавать и изменять политики Mobility Service из панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16dd8-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="16dd8-106">Создание политики мобильной связи с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="16dd8-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="16dd8-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="16dd8-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16dd8-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="16dd8-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="16dd8-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="16dd8-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="16dd8-110">На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Переход к **политике мобильной** связи.</span><span class="sxs-lookup"><span data-stu-id="16dd8-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="16dd8-111">На странице " **политика мобильности** " нажмите кнопку **создать**и выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="16dd8-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="16dd8-112">Чтобы создать политику мобильности сайта, нажмите кнопку **Политика сайта**, выберите сайт, нажмите кнопку **ОК**, проверьте параметры по умолчанию и, если нужно, внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="16dd8-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="16dd8-113">Чтобы создать политику мобильности пользователей, нажмите кнопку **Политика пользователя**, введите имя, проверьте параметры по умолчанию и, если нужно, внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="16dd8-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="16dd8-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="16dd8-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="16dd8-115">Изменение политики мобильной связи с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="16dd8-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="16dd8-116">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="16dd8-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16dd8-117">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="16dd8-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="16dd8-118">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="16dd8-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="16dd8-119">На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Переход к **политике мобильной** связи.</span><span class="sxs-lookup"><span data-stu-id="16dd8-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="16dd8-120">На странице " **Политика Mobility Service** " выберите одну из существующих политик мобильной связи.</span><span class="sxs-lookup"><span data-stu-id="16dd8-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="16dd8-121">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="16dd8-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="16dd8-122">Измените параметры.</span><span class="sxs-lookup"><span data-stu-id="16dd8-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="16dd8-123">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="16dd8-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="16dd8-124">Создание политик внешнего доступа с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16dd8-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="16dd8-125">С помощью Windows PowerShell и командлета **New-ксмобилитиполици** можно создавать политики мобильной связи (в области сайта или на уровне пользователей).</span><span class="sxs-lookup"><span data-stu-id="16dd8-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="16dd8-126">Кроме того, вы можете использовать командлет **Set-ксмобилитиполици** , чтобы изменить любую из существующих политик, включая глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="16dd8-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="16dd8-127">Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16dd8-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="16dd8-128">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16dd8-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="16dd8-129">Создание политики Mobility Service в области сайта</span><span class="sxs-lookup"><span data-stu-id="16dd8-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="16dd8-130">Эта команда создает новую политику мобильности для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="16dd8-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="16dd8-131">Поскольку в предыдущей команде не указаны никакие параметры (кроме обязательного параметра удостоверения), политики будут использовать значения по умолчанию для всех его свойств.</span><span class="sxs-lookup"><span data-stu-id="16dd8-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="16dd8-132">Создание политики Mobility Service в области "на пользователя"</span><span class="sxs-lookup"><span data-stu-id="16dd8-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="16dd8-133">Чтобы создать политику мобильности в области "на пользователя", укажите уникальный идентификатор для политики.</span><span class="sxs-lookup"><span data-stu-id="16dd8-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="16dd8-134">Изменение одного значения свойства при создании политики мобильной связи</span><span class="sxs-lookup"><span data-stu-id="16dd8-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="16dd8-135">Для создания политик, использующих различные значения свойств, включите соответствующие параметр и значение параметра.</span><span class="sxs-lookup"><span data-stu-id="16dd8-135">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="16dd8-136">Например, эта команда создает политику мобильности, которая отключает вызов через work.</span><span class="sxs-lookup"><span data-stu-id="16dd8-136">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="16dd8-137">Изменение нескольких значений свойства при создании политики мобильной связи</span><span class="sxs-lookup"><span data-stu-id="16dd8-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="16dd8-138">Чтобы изменить несколько значений свойств, можно включить несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="16dd8-138">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="16dd8-139">Например, эта команда создает политику, которая отключает и мобильность, и звонки через работу.</span><span class="sxs-lookup"><span data-stu-id="16dd8-139">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="16dd8-140">Дополнительные сведения можно найти в разделе справки для командлетов [New-ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) и [Set-ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .</span><span class="sxs-lookup"><span data-stu-id="16dd8-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16dd8-141">См. также</span><span class="sxs-lookup"><span data-stu-id="16dd8-141">See Also</span></span>


[<span data-ttu-id="16dd8-142">Настройка политики мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16dd8-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

