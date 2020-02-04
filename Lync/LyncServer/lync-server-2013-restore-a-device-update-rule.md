---
title: 'Lync Server 2013: восстановление правила обновления устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0416092c7021d599ec7e516d72c19e8baa3c598
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="4d4f3-102">Восстановление правила обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d4f3-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d4f3-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4d4f3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4d4f3-104">Чтобы удалить правило обновления устройства с устройств в развертывании, восстановите его.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="4d4f3-105">При восстановлении правила обновления для устройства удаляется и переустанавливается Предыдущая версия правила.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="4d4f3-106">Вы можете восстановить правило обновления устройства с помощью панели управления Lync Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="4d4f3-107">Восстановление правил обновления устройства с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="4d4f3-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4d4f3-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d4f3-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d4f3-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d4f3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d4f3-111">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **обновлению устройства** .</span><span class="sxs-lookup"><span data-stu-id="4d4f3-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="4d4f3-112">На странице **обновление устройства** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="4d4f3-113">Чтобы восстановить одно правило, выберите это правило.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="4d4f3-114">Чтобы восстановить все правила, нажмите кнопку **изменить**, а затем выберите команду **выделить все**.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="4d4f3-115">Откройте меню **действия** , а затем выберите команду **восстановить**.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4d4f3-116">Восстановление правил обновления устройства с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d4f3-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4d4f3-117">Кроме того, вы можете восстановить правила обновления устройства с помощью Windows PowerShell и командлета **RESTORE-ксдевицеупдатеруле** .</span><span class="sxs-lookup"><span data-stu-id="4d4f3-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="4d4f3-118">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d4f3-119">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d4f3-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="4d4f3-120">Восстановление отдельного правила обновления устройства на сервере</span><span class="sxs-lookup"><span data-stu-id="4d4f3-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="4d4f3-121">Следующая команда восстанавливает правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 на веб-сервере atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="4d4f3-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="4d4f3-122">Восстановление всех правил обновления устройства на сервере</span><span class="sxs-lookup"><span data-stu-id="4d4f3-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="4d4f3-123">Эта команда восстанавливает все правила обновления устройств на веб-сервере atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="4d4f3-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="4d4f3-124">Дополнительные сведения можно найти в разделе справки по командлету [RESTORE-ксдевицеупдатеруле](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="4d4f3-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

