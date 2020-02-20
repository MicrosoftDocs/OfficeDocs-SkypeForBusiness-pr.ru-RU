---
title: 'Lync Server 2013: Удаление правила обновления устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28b02da5927b6a33cabefd005a8f026ca65f99b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="89648-102">Удаление правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89648-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89648-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="89648-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="89648-104">При удалении правила обновления устройства он удаляется навсегда из очереди обновления устройства.</span><span class="sxs-lookup"><span data-stu-id="89648-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="89648-105">Удаление правила отличается от удаления обновления с устройств в вашем развертывании или на тестовых устройствах.</span><span class="sxs-lookup"><span data-stu-id="89648-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="89648-106">Чтобы удалить одобренное обновление из развертывания, *восстановите* правило обновления устройства.</span><span class="sxs-lookup"><span data-stu-id="89648-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="89648-107">Для получения дополнительных сведений см. [Восстановление правила обновления устройств в Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="89648-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="89648-108">Чтобы удалить обновление, которое не было утверждено на тестовых устройствах, необходимо *сбросить* его.</span><span class="sxs-lookup"><span data-stu-id="89648-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="89648-109">Подробнее: " [Сброс правила обновления устройства" в Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="89648-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="89648-110">Правило обновления устройства можно удалить с помощью панели управления Lync Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89648-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="89648-111">Удаление правил обновления устройств с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="89648-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="89648-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="89648-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89648-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89648-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="89648-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="89648-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="89648-115">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **обновления устройства** .</span><span class="sxs-lookup"><span data-stu-id="89648-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="89648-116">На странице **обновление устройства** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="89648-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="89648-117">Чтобы удалить одно правило, выберите правило, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="89648-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="89648-118">Чтобы удалить все правила, щелкните меню **Правка** и выберите команду **выбрать все**.</span><span class="sxs-lookup"><span data-stu-id="89648-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="89648-119">Щелкните **Изменить** и **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="89648-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89648-120">Удаление правил обновления устройств с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89648-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="89648-121">Правила обновления устройств также можно удалить с помощью Windows PowerShell и командлета **Remove – CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="89648-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="89648-122">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89648-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="89648-123">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="89648-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="89648-124">Удаление правила обновления одного устройства с сервера</span><span class="sxs-lookup"><span data-stu-id="89648-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="89648-125">Следующая команда удаляет правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 на веб-сервере в atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="89648-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="89648-126">Удаление всех правил обновления устройств с сервера</span><span class="sxs-lookup"><span data-stu-id="89648-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="89648-127">Эта команда удаляет все правила обновления устройств с веб-сервера в atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="89648-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="89648-128">Дополнительные сведения см. в разделе справки для командлета [Remove – CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="89648-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89648-129">См. также</span><span class="sxs-lookup"><span data-stu-id="89648-129">See Also</span></span>


[<span data-ttu-id="89648-130">Утверждение правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89648-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

