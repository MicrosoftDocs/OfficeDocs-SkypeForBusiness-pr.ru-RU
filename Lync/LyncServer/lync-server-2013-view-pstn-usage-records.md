---
title: 'Lync Server 2013: Просмотр записей использования PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50bd216cbef24d92497d2724bd147dd92bb0abd8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="74daa-102">Просмотр записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74daa-102">View PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74daa-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="74daa-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="74daa-104">В записи использования телефонной сети общего пользования (PSTN) указывается класс вызовов (например, внутренние, локальные или междугородные), которые могут выполняться разными пользователями или группами пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="74daa-104">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="74daa-105">Сведения о [записях использования PSTN в Lync Server 2013](lync-server-2013-pstn-usage-records.md) содержатся в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="74daa-105">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="74daa-106">Просмотр записи использования PSTN с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="74daa-106">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="74daa-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74daa-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="74daa-108">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="74daa-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="74daa-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74daa-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74daa-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74daa-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74daa-111">На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем щелкните **Использование ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="74daa-111">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="74daa-112">На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="74daa-112">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74daa-113">На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="74daa-113">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74daa-114">Просмотр сведений об использовании PSTN с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74daa-114">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="74daa-115">Вы также можете просматривать использование PSTN с помощью Windows PowerShell и командлета **Get – кспстнусаже** .</span><span class="sxs-lookup"><span data-stu-id="74daa-115">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="74daa-116">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74daa-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="74daa-117">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="74daa-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74daa-118">Просмотр сведений об использовании PSTN с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74daa-118">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="74daa-119">Чтобы просмотреть сведения обо всех параметрах использования PSTN, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="74daa-119">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="74daa-120">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="74daa-120">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="74daa-121">Подробные сведения см. в разделе [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span><span class="sxs-lookup"><span data-stu-id="74daa-121">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74daa-122">См. также</span><span class="sxs-lookup"><span data-stu-id="74daa-122">See Also</span></span>


[<span data-ttu-id="74daa-123">Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74daa-123">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="74daa-124">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74daa-124">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

