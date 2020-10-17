---
title: 'Lync Server 2013: Просмотр политики ПИН-кода сведений о'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f73d3ccf2ebf1083b834ab711ae43f582063520c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518456"
---
# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a><span data-ttu-id="cb232-102">Просмотр политики ПИН-кода сведений о в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb232-102">View PIN policy inforrmation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb232-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cb232-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cb232-104">Вы можете использовать вкладку **политика ПИН-кода** для просмотра персонального идентификационного номера (ПИН-кода) пользователей, подключающихся к Lync 2013 с IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="cb232-104">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="cb232-105">Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.</span><span class="sxs-lookup"><span data-stu-id="cb232-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="cb232-106">Дополнительные сведения: [изменение параметров конфигурации существующей веб-службы в Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="cb232-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="cb232-107">Чтобы изменить политику ПИН-кода на уровне пользователя или сайта, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="cb232-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a><span data-ttu-id="cb232-108">Просмотр сведений о политике ПИН-кодов в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="cb232-108">To view information about a PIN policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cb232-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb232-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="cb232-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb232-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cb232-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cb232-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cb232-112">На панели навигации слева выберите **Безопасность** и нажмите **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="cb232-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="cb232-113">На странице **Политика ПИН-кода** щелкните политику, выберите **Изменить** и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="cb232-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cb232-114">Просмотр политик ПИН-кода с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb232-114">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cb232-115">Вы также можете просматривать политики ПИН-кодов с помощью Windows PowerShell и командлета Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="cb232-115">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="cb232-116">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb232-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cb232-117">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="cb232-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pin-policies"></a><span data-ttu-id="cb232-118">Просмотр политик ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="cb232-118">To view PIN policies</span></span>

  - <span data-ttu-id="cb232-119">Чтобы просмотреть сведения обо всех политиках ПИН-кодов, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="cb232-119">To view information about all your PIN policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPinPolicy
    
    <span data-ttu-id="cb232-120">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="cb232-120">That will return information similar to this:</span></span>
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

<span data-ttu-id="cb232-121">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="cb232-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb232-122">См. также</span><span class="sxs-lookup"><span data-stu-id="cb232-122">See Also</span></span>


[<span data-ttu-id="cb232-123">Изменение параметров конфигурации существующей веб-службы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb232-123">Modify existing Web Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[<span data-ttu-id="cb232-124">Создание новой политики ПИН-кодов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb232-124">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

