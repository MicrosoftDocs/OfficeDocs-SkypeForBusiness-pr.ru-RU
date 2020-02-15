---
title: 'Lync Server 2013: сброс правила обновления устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1079236ceab3fda42b1920675761f272333d264
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="341c1-102">Сброс правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="341c1-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="341c1-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="341c1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="341c1-104">Если вы не хотите, чтобы обновление работала на тестовых устройствах, можно сбросить правило обновления устройства, которое удаляет состояние ожидания правила и удаляет обновление с тестовых устройств.</span><span class="sxs-lookup"><span data-stu-id="341c1-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="341c1-105">Правило обновления устройства можно удалить с помощью панели управления Lync Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="341c1-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="341c1-106">Чтобы удалить правило, которое вы уже утвердили (то есть выполните откат), восстановите его.</span><span class="sxs-lookup"><span data-stu-id="341c1-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="341c1-107">Для получения дополнительных сведений см. <A href="lync-server-2013-restore-a-device-update-rule.md">Восстановление правила обновления устройств в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="341c1-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="341c1-108">Сброс правила обновления устройства с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="341c1-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="341c1-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="341c1-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="341c1-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="341c1-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="341c1-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="341c1-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="341c1-112">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **обновления устройства** .</span><span class="sxs-lookup"><span data-stu-id="341c1-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="341c1-113">На странице **обновление устройства** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="341c1-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="341c1-114">Чтобы сбросить одно правило, выберите правило, которое нужно сбросить.</span><span class="sxs-lookup"><span data-stu-id="341c1-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="341c1-115">Чтобы сбросить все правила, в меню **Правка** выберите пункт **выделить все**.</span><span class="sxs-lookup"><span data-stu-id="341c1-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="341c1-116">Чтобы сбросить все правила для одной фирменной символики, используйте меню столбец " **фирменная символика** ".</span><span class="sxs-lookup"><span data-stu-id="341c1-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="341c1-117">Щелкните **действие**, а затем — **Отмена ожидающих обновлений**.</span><span class="sxs-lookup"><span data-stu-id="341c1-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="341c1-118">Если вы уверены, что вы никогда не хотите развертывать правила обновления устройств, которые вы отменили, можете удалить их.</span><span class="sxs-lookup"><span data-stu-id="341c1-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="341c1-119">Дополнительные сведения см. <A href="lync-server-2013-remove-a-device-update-rule.md">в разделе Удаление правила обновления устройств в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="341c1-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="341c1-120">Сброс правила обновления устройства с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="341c1-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="341c1-121">Кроме того, можно сбросить правила обновления устройств с помощью Windows PowerShell и командлета **Reset – CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="341c1-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="341c1-122">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="341c1-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="341c1-123">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="341c1-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="341c1-124">Чтобы сбросить конкретное правило обновления устройства на сервере</span><span class="sxs-lookup"><span data-stu-id="341c1-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="341c1-125">Следующая команда сбрасывает правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 на веб-сервере atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="341c1-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="341c1-126">Сброс всех правил обновления устройств на сервере</span><span class="sxs-lookup"><span data-stu-id="341c1-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="341c1-127">Эта команда сбрасывает все правила обновления устройств на веб-сервере atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="341c1-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="341c1-128">Сброс всех правил обновления устройств с определенной фирменной символикой</span><span class="sxs-lookup"><span data-stu-id="341c1-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="341c1-129">В этом примере выполняется сброс всех обновлений для всех устройств в Организации, имеющей торговую марку, равную корпорации Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="341c1-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="341c1-130">Дополнительные сведения см. в разделе справки для командлета [Reset – CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="341c1-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="341c1-131">См. также</span><span class="sxs-lookup"><span data-stu-id="341c1-131">See Also</span></span>


[<span data-ttu-id="341c1-132">Утверждение правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="341c1-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

