---
title: 'Lync Server 2013: Просмотр номеров доступа для конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3393fff4df6a4b506c547752feb3684b65580ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="d0882-102">Просмотр номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0882-102">View dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0882-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d0882-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d0882-104">В панели управления Lync Server 2013 вы можете предоставить пользователям номера доступа для телефонного подключения, чтобы они могли присоединяться к собранию извне.</span><span class="sxs-lookup"><span data-stu-id="d0882-104">In Lync Server 2013 Control Panel, you provide dial-in access numbers to users so that they can join a meeting externally.</span></span>

<div>

## <a name="to-view-dial-in-access-numbers"></a><span data-ttu-id="d0882-105">Чтобы просмотреть номера для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="d0882-105">To view dial-in access numbers</span></span>

1.  <span data-ttu-id="d0882-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d0882-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0882-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0882-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0882-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d0882-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0882-109">В левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="d0882-109">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="d0882-110">На странице **Номер для телефонного подключения** щелкните номер доступа, который следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="d0882-110">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>

5.  <span data-ttu-id="d0882-p102">В разделе **Изменить** установите флажок **Подробнее…**.</span><span class="sxs-lookup"><span data-stu-id="d0882-p102">In **Edit**, select the **Show Details…** check box.</span></span>

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d0882-113">Просмотр номеров доступа для конференц-связи с телефонным подключением с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0882-113">Viewing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d0882-114">Номера доступа к конференц-связи с телефонным подключением можно просмотреть с помощью Windows PowerShell и командлета Get-CsDialInConferencingAccessNumber.</span><span class="sxs-lookup"><span data-stu-id="d0882-114">Dial-in conferencing access numbers can be viewed by using Windows PowerShell and the Get-CsDialInConferencingAccessNumber cmdlet.</span></span> <span data-ttu-id="d0882-115">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0882-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d0882-116">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="d0882-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="d0882-117">Просмотр номеров доступа к конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="d0882-117">To view dial-in conferencing access numbers</span></span>

  - <span data-ttu-id="d0882-118">Чтобы просмотреть сведения обо всех номерах доступа к конференц-связи с телефонным подключением, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="d0882-118">To view information about all your dial-in conferencing access numbers, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsDialInConferencingAccessNumber
    
    <span data-ttu-id="d0882-119">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="d0882-119">That will return information similar to this:</span></span>
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

<span data-ttu-id="d0882-120">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="d0882-120">For more information, see the help topic for the [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

