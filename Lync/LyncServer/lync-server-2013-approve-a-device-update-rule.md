---
title: 'Lync Server 2013: утверждение правила обновления устройства'
description: 'Lync Server 2013: утверждение правила обновления устройства.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 127d16dad6329e952b9033db07ac2f4a4fe9112c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550725"
---
# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="90526-103">Утверждение правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90526-103">Approve a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90526-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="90526-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="90526-105">После импорта правила обновления устройств оно устанавливается на тестовые устройства.</span><span class="sxs-lookup"><span data-stu-id="90526-105">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="90526-106">Если проверка прошла успешно, и вы хотите развернуть обновление в Организации, утвердите его с помощью панели управления Lync Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90526-106">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="90526-107">Утверждение правила обновления устройства с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="90526-107">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="90526-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="90526-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90526-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="90526-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="90526-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="90526-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="90526-111">На странице **обновление устройства** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="90526-111">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="90526-112">Чтобы утвердить одно правило, выберите это правило.</span><span class="sxs-lookup"><span data-stu-id="90526-112">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="90526-113">Чтобы утвердить все правила, нажмите кнопку **изменить**, а затем выберите пункт **выбрать все**.</span><span class="sxs-lookup"><span data-stu-id="90526-113">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="90526-114">Щелкните **действие**, а затем нажмите кнопку **утвердить**.</span><span class="sxs-lookup"><span data-stu-id="90526-114">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90526-115">Утверждение правила обновления устройства с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90526-115">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90526-116">Правила обновления устройств также могут быть утверждены с помощью Windows PowerShell и командлета **утвержденного CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="90526-116">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="90526-117">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90526-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90526-118">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="90526-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="90526-119">Утверждение правила обновления одного устройства</span><span class="sxs-lookup"><span data-stu-id="90526-119">To approve a single device update rule</span></span>

  - <span data-ttu-id="90526-120">Следующая команда утверждает правило обновления устройства d5ce3c10-2588-420A-82ac-dc2d9b1222ff9, обнаруженное на веб-сервере atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="90526-120">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="90526-121">Утверждение нескольких правил обновления устройств</span><span class="sxs-lookup"><span data-stu-id="90526-121">To approve multiple device update rules</span></span>

  - <span data-ttu-id="90526-122">Эта команда утверждает все правила обновления устройств для устройств с фирменной символикой Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="90526-122">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="90526-123">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [утверждений CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="90526-123">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90526-124">См. также</span><span class="sxs-lookup"><span data-stu-id="90526-124">See Also</span></span>


[<span data-ttu-id="90526-125">Импорт правил обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90526-125">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="90526-126">Восстановление правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90526-126">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

