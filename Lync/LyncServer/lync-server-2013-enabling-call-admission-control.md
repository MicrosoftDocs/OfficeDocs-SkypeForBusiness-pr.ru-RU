---
title: 'Lync Server 2013: Включение управления допуском звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20cd0f7792f8db2cf1b2d817bfe79ed6d6b16fce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="f1663-102">Включение управления допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1663-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1663-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f1663-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f1663-104">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f1663-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="f1663-105">После настройки сети CAC необходимо включить функцию CAC для обеспечения ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f1663-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="f1663-106">Это можно сделать с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1663-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="f1663-107">Активация CAC с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="f1663-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f1663-108">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f1663-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1663-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1663-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f1663-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1663-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f1663-111">На панели навигации слева выберите пункт **Конфигурация сети** , а затем — **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="f1663-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="f1663-112">На **глобальной** странице щелкните глобальную конфигурацию \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="f1663-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1663-113">Для любого развертывания Microsoft Lync Server 2013 можно настроить только одну сеть, поэтому в списке никогда не будет более одной конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="f1663-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="f1663-114">Вы не можете переименовать глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f1663-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="f1663-115">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f1663-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f1663-116">На странице **изменение глобальных параметров** установите флажок **включить управление допуском звонков** , а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1663-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="f1663-117">При нажатии \*\*\*\* кнопки зафиксировать вы запускаете тест конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f1663-117">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="f1663-118">Диалоговое окно " **изменение глобальных параметров** " закроется и \*\*\*\* будет возвращено на глобальную страницу.</span><span class="sxs-lookup"><span data-stu-id="f1663-118">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="f1663-119">Вы получите предупреждение о том, что в конфигурации сети обнаружены ошибки или несоответствия (например, если каждый регион не подключен к каждому из них через маршрут между регионами).</span><span class="sxs-lookup"><span data-stu-id="f1663-119">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="f1663-120">Если вы вносите изменения в конфигурацию сети, вы можете снова выполнить проверку, открыв глобальную конфигурацию и выбрав команду **Commit (сохранить**).</span><span class="sxs-lookup"><span data-stu-id="f1663-120">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="f1663-121">Отключить CAC сначала не требуется: Оставьте флажок установленным, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1663-121">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="f1663-122">Это можно сделать в любое время, не внося каких – либо изменений в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f1663-122">You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1663-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f1663-123">See Also</span></span>


[<span data-ttu-id="f1663-124">Общие сведения об управлении допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1663-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="f1663-125">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1663-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="f1663-126">Настройка управления допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1663-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="f1663-127">Get-Кснетворкконфигуратион</span><span class="sxs-lookup"><span data-stu-id="f1663-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="f1663-128">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1663-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="f1663-129">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1663-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

