---
title: 'Lync Server 2013: Просмотр состояния служб, запущенных на компьютере'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2745263bc4a179c9d99bf525aebe72b0cf299e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="5c6b3-102">Просмотр состояния служб, запущенных на компьютере в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c6b3-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c6b3-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5c6b3-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5c6b3-104">Вы можете использовать панель управления Lync Server 2013 для просмотра всех служб, запущенных на определенном компьютере в вашей топологии Lync Server, и просмотра состояния каждой службы.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="5c6b3-105">To view the status of services running on a computer</span><span class="sxs-lookup"><span data-stu-id="5c6b3-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="5c6b3-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c6b3-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5c6b3-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b3-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5c6b3-109">In the left navigation bar, click **Topology**.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="5c6b3-110">На странице **Состояние** отсортируйте список или выполните по нему поиск, чтобы найти интересующий вас компьютер, а затем щелкните имя этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="5c6b3-111">Do any of the following:</span><span class="sxs-lookup"><span data-stu-id="5c6b3-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="5c6b3-112">To see the latest status of services running on the computer, click **Get service status**.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="5c6b3-113">Чтобы просмотреть список конкретных служб, запущенных на компьютере, и состояние каждой из них, щелкните **Свойства**, а затем нажмите кнопку **Закрыть** для возврата в список.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5c6b3-114">Просмотр состояния службы с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c6b3-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5c6b3-115">Вы также можете просмотреть состояние службы с помощью Windows PowerShell и командлета **Get – CsWindowsService** .</span><span class="sxs-lookup"><span data-stu-id="5c6b3-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="5c6b3-116">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5c6b3-117">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="5c6b3-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="5c6b3-118">Просмотр состояния службы</span><span class="sxs-lookup"><span data-stu-id="5c6b3-118">To view service status</span></span>

  - <span data-ttu-id="5c6b3-119">Чтобы просмотреть состояние службы на компьютере, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="5c6b3-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="5c6b3-120">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="5c6b3-120">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="5c6b3-121">Дополнительные сведения см. в статье [Get – CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span><span class="sxs-lookup"><span data-stu-id="5c6b3-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5c6b3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5c6b3-122">See Also</span></span>


[<span data-ttu-id="5c6b3-123">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c6b3-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

