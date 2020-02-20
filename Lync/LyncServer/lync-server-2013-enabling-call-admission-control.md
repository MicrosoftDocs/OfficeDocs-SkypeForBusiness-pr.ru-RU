---
title: 'Lync Server 2013: включение контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ee956918fd56cb3fa91d1d5065f364d525f8446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="f62a0-102">Включение контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f62a0-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f62a0-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f62a0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f62a0-104">Контроль допуска звонков — это сеть, состоящая из областей, узлов и подсетей, которая позволяет размещать ограничения на передачу аудио- и видеоданных на основе доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f62a0-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="f62a0-105">После настройки сети контроля допуска звонков необходимо включить контроль допуска звонков, чтобы ограничения пропускной способности вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="f62a0-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="f62a0-106">Для этого можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f62a0-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="f62a0-107">Включение контроля допуска звонков с панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="f62a0-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f62a0-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="f62a0-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f62a0-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f62a0-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f62a0-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f62a0-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f62a0-111">На панели навигации слева выберите пункт **Конфигурация сети** и щелкните **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="f62a0-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="f62a0-112">На странице **Глобальная** выберите конфигурацию **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="f62a0-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f62a0-113">Для любого развертывания Microsoft Lync Server 2013 можно настроить только одну сеть, поэтому в списке не будет более одной конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="f62a0-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="f62a0-114">Переименовать глобальную конфигурацию нельзя.</span><span class="sxs-lookup"><span data-stu-id="f62a0-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="f62a0-115">В меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f62a0-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f62a0-116">На странице **Изменение глобальных параметров** установите флажок **Включить контроль допуска звонков** и нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="f62a0-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="f62a0-p104">При нажатии кнопки **Зафиксировать** запускается проверка конфигурации. Диалоговое окно **изменения глобальных параметров** закрывается, возвращая вас на страницу **Глобально**. Если в конфигурации будут обнаружены какие-либо ошибки или несоответствия, препятствующие ее корректной работе (например, если каждая область не связана с каждой другой областью промежуточным маршрутом), то вы получите предупреждение.</span><span class="sxs-lookup"><span data-stu-id="f62a0-p104">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="f62a0-p105">При внесении изменений в конфигурацию сети можно снова выполнить проверку правильности, открыв глобальную конфигурацию и нажав кнопку **Зафиксировать**. Предварительно отключать контроль допуска звонков не требуется: оставьте этот флажок установленным и нажмите **Зафиксировать**. Это можно делать в любое время даже без внесения изменений в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f62a0-p105">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f62a0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f62a0-123">See Also</span></span>


[<span data-ttu-id="f62a0-124">Обзор контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f62a0-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="f62a0-125">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f62a0-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="f62a0-126">Настройка контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f62a0-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="f62a0-127">Get — CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f62a0-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="f62a0-128">Set — CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f62a0-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="f62a0-129">Remove — CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f62a0-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

