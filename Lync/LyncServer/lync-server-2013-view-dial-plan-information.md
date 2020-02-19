---
title: 'Lync Server 2013: Просмотр сведений о абонентской схеме'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a90af8cdeffafa587f4dad87dd2b08573647df5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-dial-plan-information-in-lync-server-2013"></a><span data-ttu-id="e0aa3-102">Просмотр сведений о абонентской схеме в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0aa3-102">View dial plan information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0aa3-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e0aa3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e0aa3-104">Для просмотра сведений о существующей абонентской группе выполните действия, указанные в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="e0aa3-104">To view information for an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="e0aa3-105">Если вы хотите создать новую абонентскую схему, ознакомьтесь со статьей [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="e0aa3-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a><span data-ttu-id="e0aa3-106">Просмотр сведений о абонентской группы из панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="e0aa3-106">To view information about a dial plan from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e0aa3-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e0aa3-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e0aa3-108">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e0aa3-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e0aa3-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0aa3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e0aa3-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e0aa3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e0aa3-111">На панели навигации слева выберите **Маршрутизация телефонных звонков** и нажмите **Абонентская группа**.</span><span class="sxs-lookup"><span data-stu-id="e0aa3-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="e0aa3-112">На странице **Абонентская группа** дважды щелкните имя абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="e0aa3-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0aa3-113">Можно одновременно просматривать не более одной абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="e0aa3-113">You can view information for only one dial plan at a time.</span></span>

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e0aa3-114">Просмотр абонентских планов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0aa3-114">To view dial plans by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="e0aa3-115">Абонентские группы можно просмотреть с помощью интерфейса командной строки Windows PowerShell и командлета **Get – CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="e0aa3-115">Dial plans can be viewed by using the Windows PowerShell command-line interface and the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="e0aa3-116">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0aa3-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e0aa3-117">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="e0aa3-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="e0aa3-118">Чтобы просмотреть сведения обо всех абонентских планах, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="e0aa3-118">To view information about all your dial plans, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="e0aa3-119">Эта команда возвращает приблизительно следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e0aa3-119">That command will return information similar to this:</span></span>
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0aa3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e0aa3-120">See Also</span></span>


[<span data-ttu-id="e0aa3-121">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0aa3-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="e0aa3-122">Изменение абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0aa3-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

