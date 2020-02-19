---
title: 'Lync Server 2013: Просмотр политик версий клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policies
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898479(v=OCS.15)
ms:contentKeyID: 50873759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 517ef41ed2553db1c05ad98dad08c2087bec6faa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-client-version-policies-in-lync-server-2013"></a><span data-ttu-id="79f87-102">Просмотр политик версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79f87-102">View client version policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79f87-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="79f87-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="79f87-104">Политики версий клиентов используются для глобального применения набора правил управления версиями клиентов или для определенного сайта, пула или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="79f87-104">Client version policies are used to apply a set of client versioning rules globally or to a particular site, pool, or group of users.</span></span> <span data-ttu-id="79f87-105">Политики версий клиентов, настроенные в среде Lync Server 2013, можно просмотреть на панели управления Lync Server 2013 или в командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79f87-105">You can view the client version policies that have been configured in your Lync Server 2013 environment from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="79f87-106">Просмотр политик версий клиентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="79f87-106">To view client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="79f87-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="79f87-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79f87-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79f87-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="79f87-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="79f87-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="79f87-110">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации для **политики версий клиентов** .</span><span class="sxs-lookup"><span data-stu-id="79f87-110">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="79f87-111">Если вы хотите просмотреть правила для политики версий клиентов, на странице **Политика версий клиентов** дважды щелкните политику, которую нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="79f87-111">If you want to view the rules for a client version policy, on the **Client Version Policy** page, double-click the policy you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="79f87-112">Просмотр политик версий клиентов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79f87-112">Viewing Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="79f87-113">Политики версий клиентов можно просмотреть с помощью командлета **Get – CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="79f87-113">You can view client version policies by using the **Get-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="79f87-114">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79f87-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="79f87-115">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="79f87-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policies"></a><span data-ttu-id="79f87-116">Просмотр политик версий клиентов</span><span class="sxs-lookup"><span data-stu-id="79f87-116">To view client version policies</span></span>

  - <span data-ttu-id="79f87-117">Чтобы просмотреть сведения обо всех политиках версий клиентов, введите в командную консоль Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="79f87-117">To view information about all your client version policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicy
    
    <span data-ttu-id="79f87-118">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="79f87-118">That will return information similar to this:</span></span>
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

</div>

<span data-ttu-id="79f87-119">Дополнительные сведения см. в разделе справки по командлету [Get – CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="79f87-119">For details, see the Help topic for the [Get-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

