---
title: 'Lync Server 2013: Просмотр состояния служб, запущенных на компьютере'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7b1628f9e9fcd99eea84ebda2cbfe934fc7d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="4786b-102">Просмотр состояния служб, запущенных на компьютере в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4786b-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4786b-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4786b-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4786b-104">Вы можете использовать панель управления Lync Server 2013 для просмотра всех служб, запущенных на определенном компьютере в топологии Lync Server, и посмотреть состояние каждой службы.</span><span class="sxs-lookup"><span data-stu-id="4786b-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="4786b-105">Просмотр состояния служб, запущенных на компьютере</span><span class="sxs-lookup"><span data-stu-id="4786b-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="4786b-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4786b-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4786b-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4786b-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4786b-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4786b-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4786b-109">На панели навигации слева выберите пункт **топология**.</span><span class="sxs-lookup"><span data-stu-id="4786b-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="4786b-110">На странице **Status (состояние** ) отсортируйте или выполните поиск по мере необходимости, чтобы найти нужный вам компьютер, а затем щелкните имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="4786b-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="4786b-111">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4786b-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="4786b-112">Чтобы просмотреть последние сведения о состоянии служб, запущенных на компьютере, щелкните **получить состояние службы**.</span><span class="sxs-lookup"><span data-stu-id="4786b-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="4786b-113">Чтобы просмотреть список конкретных служб, запущенных на компьютере, и состояние каждой из них, нажмите кнопку **Свойства**, а затем — кнопку **Закрыть** , чтобы вернуться в список.</span><span class="sxs-lookup"><span data-stu-id="4786b-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4786b-114">Просмотр состояния службы с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4786b-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4786b-115">Вы также можете просмотреть состояние службы с помощью Windows PowerShell и командлета **Get-ксвиндовссервице** .</span><span class="sxs-lookup"><span data-stu-id="4786b-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="4786b-116">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4786b-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4786b-117">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4786b-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="4786b-118">Просмотр состояния службы</span><span class="sxs-lookup"><span data-stu-id="4786b-118">To view service status</span></span>

  - <span data-ttu-id="4786b-119">Чтобы просмотреть состояние службы на компьютере, введите в командной консоли Lync Server такую команду, как показано ниже, и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="4786b-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="4786b-120">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="4786b-120">This command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="4786b-121">Подробности можно найти в [статьях Get-ксвиндовссервице](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span><span class="sxs-lookup"><span data-stu-id="4786b-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4786b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4786b-122">See Also</span></span>


[<span data-ttu-id="4786b-123">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4786b-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

