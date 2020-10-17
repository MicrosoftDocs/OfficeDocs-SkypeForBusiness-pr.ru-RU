---
title: 'Lync Server 2013: Просмотр сведений о правилах обновления устройств'
description: 'Lync Server 2013: Просмотр сведений о правилах обновления устройств.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4aecfd0dd778b576ea4a672e550f9e27d7ca463e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569635"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="afb32-103">Просмотр сведений о правилах обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afb32-103">View information about Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afb32-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="afb32-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="afb32-105">Просмотр сведений о правилах обновления устройств, которые уже были импортированы, включая тип, модель и фирменную символику устройств, к которым применяется обновление; версия и тип обновления; и языковой стандарт и пул для обновления.</span><span class="sxs-lookup"><span data-stu-id="afb32-105">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="afb32-106">Сведения доступны для всех импортированных правил обновления устройств, которые ожидают утверждения, развернуты (утверждены), отозваны (восстановлены) и которые вы решили не использовать (сбросить).</span><span class="sxs-lookup"><span data-stu-id="afb32-106">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="afb32-107">Доступ к этой информации осуществляется либо с помощью панели управления Lync Server, либо с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afb32-107">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afb32-108">Дополнительные сведения об импорте, утверждении, сбросе, восстановлении и удалении правил приведены в разделах, перечисленных в <A href="lync-server-2013-device-update-rules.md">статье обновление устройств в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="afb32-108">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="afb32-109">Просмотр правил обновления устройств с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="afb32-109">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="afb32-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="afb32-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="afb32-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afb32-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="afb32-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="afb32-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="afb32-113">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **обновления устройства** .</span><span class="sxs-lookup"><span data-stu-id="afb32-113">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="afb32-114">Импортированные правила перечислены на странице **обновление устройства** .</span><span class="sxs-lookup"><span data-stu-id="afb32-114">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="afb32-115">Просмотр правил обновления устройств с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="afb32-115">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="afb32-116">Подробные сведения обо всех правилах обновления устройств также можно просмотреть с помощью Windows PowerShell и командлета **Get – CsDeviceUpdateRule** .</span><span class="sxs-lookup"><span data-stu-id="afb32-116">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="afb32-117">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afb32-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afb32-118">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="afb32-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="afb32-119">Просмотр всех правил обновления устройств</span><span class="sxs-lookup"><span data-stu-id="afb32-119">To view all your device update rules</span></span>

  - <span data-ttu-id="afb32-120">Следующая команда возвращает сведения обо всех правилах обновления устройств, настроенных для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="afb32-120">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="afb32-121">Команда возвращает сведения, аналогичные приведенным ниже, для каждого правила обновления устройств.</span><span class="sxs-lookup"><span data-stu-id="afb32-121">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="afb32-122">Просмотр всех правил обновления устройств на определенном веб-сервере</span><span class="sxs-lookup"><span data-stu-id="afb32-122">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="afb32-123">Чтобы просмотреть правила обновления устройств на определенном компьютере, используйте параметр Filter, а затем идентификатор сервера и подстановочный знак ( \* ).</span><span class="sxs-lookup"><span data-stu-id="afb32-123">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="afb32-124">Например:</span><span class="sxs-lookup"><span data-stu-id="afb32-124">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="afb32-125">Дополнительные сведения см. в разделе справки по командлету [Get – CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="afb32-125">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

