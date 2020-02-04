---
title: 'Lync Server 2013: Просмотр сведений о правилах обновления устройств'
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
ms.openlocfilehash: 6e26b67aba2bf792b3248e7771f938a8bced1668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="99cb7-102">Просмотр сведений о правилах обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99cb7-102">View information about Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99cb7-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="99cb7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="99cb7-104">Просмотр сведений о правилах обновления устройств, которые уже были импортированы, в том числе тип, модель и фирменные символики устройств, к которым применяется обновление. версия и тип обновления; и Национальная настройка и пул для обновления.</span><span class="sxs-lookup"><span data-stu-id="99cb7-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="99cb7-105">Информация доступна для всех импортированных правил обновления устройства — тех, которые ожидают утверждения, развернуты (утверждены), отозваны (восстановлены) и которые вы решили не использовать (сбросить).</span><span class="sxs-lookup"><span data-stu-id="99cb7-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="99cb7-106">Получить доступ к этим сведениям можно на панели управления Lync Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99cb7-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99cb7-107">Подробнее об импорте, утверждении, сбросе, восстановлении и удалении правил можно найти в разделах, перечисленных в разделе <A href="lync-server-2013-device-update-rules.md">правила обновления устройств в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99cb7-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="99cb7-108">Просмотр правил обновления устройства с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="99cb7-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="99cb7-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="99cb7-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99cb7-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99cb7-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99cb7-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99cb7-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99cb7-112">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **обновлению устройства** .</span><span class="sxs-lookup"><span data-stu-id="99cb7-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="99cb7-113">Импортированные правила перечислены на странице **обновления устройства** .</span><span class="sxs-lookup"><span data-stu-id="99cb7-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="99cb7-114">Просмотр правил обновления устройства с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99cb7-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="99cb7-115">Подробные сведения о всех правилах обновления устройств также можно просмотреть с помощью Windows PowerShell и командлета **Get-ксдевицеупдатеруле** .</span><span class="sxs-lookup"><span data-stu-id="99cb7-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="99cb7-116">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99cb7-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99cb7-117">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99cb7-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="99cb7-118">Просмотр всех правил обновления устройства</span><span class="sxs-lookup"><span data-stu-id="99cb7-118">To view all your device update rules</span></span>

  - <span data-ttu-id="99cb7-119">Следующая команда возвращает сведения о всех правилах обновления устройства, настроенных для использования в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="99cb7-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="99cb7-120">Команда возвращает данные, аналогичные приведенным ниже, для каждого правила обновления устройства.</span><span class="sxs-lookup"><span data-stu-id="99cb7-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
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

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="99cb7-121">Просмотр всех правил обновления устройства на определенном веб-сервере</span><span class="sxs-lookup"><span data-stu-id="99cb7-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="99cb7-122">Чтобы просмотреть правила обновления устройства на определенном компьютере, используйте параметр фильтра, а затем идентификатор сервера и подстановочный знак (\*).</span><span class="sxs-lookup"><span data-stu-id="99cb7-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="99cb7-123">Например:</span><span class="sxs-lookup"><span data-stu-id="99cb7-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="99cb7-124">Дополнительные сведения можно найти в разделе справки по командлету [Get-ксдевицеупдатеруле](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="99cb7-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

