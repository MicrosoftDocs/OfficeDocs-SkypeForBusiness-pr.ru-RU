---
title: 'Lync Server 2013: создание или изменение политики мобильности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 469b7789de98cee3d399e09c9cec4396fdb365e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="fb7b9-102">Создание или изменение политики мобильности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb7b9-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb7b9-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fb7b9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fb7b9-104">Вы можете создать или изменить политику мобильности, чтобы позволить мобильным пользователям использовать поддерживаемые мобильные устройства для доступа к функциональным возможностям Lync, таким как обмен мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="fb7b9-105">Вы можете создавать и изменять политики мобильности из панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="fb7b9-106">Создание политики мобильности с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="fb7b9-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fb7b9-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fb7b9-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fb7b9-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b9-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fb7b9-110">В левой панели навигации щелкните элемент **Клиенты** и затем нажмите кнопку навигации **Политика мобильности**.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="fb7b9-111">На странице **политика мобильности** нажмите кнопку **создать**, а затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="fb7b9-112">Чтобы создать политику мобильности сайта, щелкните элемент **Политика сайта**, выберите сайт, нажмите кнопку **ОК**, просмотрите параметры по умолчанию и при необходимости измените их.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="fb7b9-113">Чтобы создать политику мобильности сайта, щелкните элемент **Политика пользователя**, выберите имя, просмотрите параметры по умолчанию и при необходимости измените их.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="fb7b9-114">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="fb7b9-115">Изменение политики мобильности с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="fb7b9-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fb7b9-116">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fb7b9-117">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fb7b9-118">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b9-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fb7b9-119">В левой панели навигации щелкните элемент **Клиенты** и затем нажмите кнопку навигации **Политика мобильности**.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="fb7b9-120">На странице **политика мобильности** выберите одну из существующих политик мобильности.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="fb7b9-121">В меню **Правка** выберите пункт **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="fb7b9-122">Измените параметры.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="fb7b9-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fb7b9-124">Создание политик внешнего доступа с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb7b9-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fb7b9-125">С помощью Windows PowerShell и командлета **New-CsMobilityPolicy** можно создавать политики мобильной связи (на уровне сайта или на уровне пользователя).</span><span class="sxs-lookup"><span data-stu-id="fb7b9-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="fb7b9-126">Кроме того, вы можете использовать командлет **Set-CsMobilityPolicy** для изменения любых существующих политик, включая глобальную.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="fb7b9-127">Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fb7b9-128">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="fb7b9-129">Создание политики мобильности на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="fb7b9-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="fb7b9-130">Данная команда создает новую политику мобильности для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="fb7b9-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="fb7b9-131">Для всех свойств таких политик будут использоваться значения по умолчанию, так как в приведенной выше команде не заданы никакие параметры, кроме обязательного параметра Identity.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="fb7b9-132">Создание политики мобильности на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="fb7b9-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="fb7b9-133">Чтобы создать политику мобильности на уровне пользователя, укажите для нее уникальный параметр Identity:</span><span class="sxs-lookup"><span data-stu-id="fb7b9-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="fb7b9-134">Изменение значения отдельного свойства при создании политики мобильности</span><span class="sxs-lookup"><span data-stu-id="fb7b9-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="fb7b9-p105">Чтобы создать политики, использующие разные значения свойства, включайте в них соответствующий параметр со значением. Например, следующая команда создает политику мобильности, отключающую возможность "Позвонить с рабочего":</span><span class="sxs-lookup"><span data-stu-id="fb7b9-p105">To create policies that use different property values, include the appropriate parameter and parameter value. For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="fb7b9-137">Изменение значений нескольких свойств при создании политики мобильности</span><span class="sxs-lookup"><span data-stu-id="fb7b9-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="fb7b9-p106">Посредством включения нескольких параметров можно изменять значения нескольких свойств. Например, следующая команда создает политику, отключающую как мобильность, так и возможность "Позвонить с рабочего":</span><span class="sxs-lookup"><span data-stu-id="fb7b9-p106">Multiple property values can be modified by including multiple parameters. For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="fb7b9-140">Дополнительные сведения см. в разделе справки для командлетов [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) и [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="fb7b9-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb7b9-141">См. также</span><span class="sxs-lookup"><span data-stu-id="fb7b9-141">See Also</span></span>


[<span data-ttu-id="fb7b9-142">Настройка политики мобильности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb7b9-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

