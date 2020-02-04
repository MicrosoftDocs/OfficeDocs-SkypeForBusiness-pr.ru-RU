---
title: 'Lync Server 2013: Просмотр политики ПИН инфоррматион'
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
ms.openlocfilehash: d5f63b2abcc1278211b70fd575bbead8ae875332
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a><span data-ttu-id="5bedd-102">Просмотр политики ПИН-кода инфоррматион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bedd-102">View PIN policy inforrmation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bedd-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5bedd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5bedd-104">С помощью вкладки " **политика закрепления** " можно просмотреть персональный идентификационный номер (ПИН-код) пользователей, которые подключаются к Lync 2013 с IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="5bedd-104">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="5bedd-105">Чтобы использовать проверку подлинности по ПИН-коду, необходимо установить флажок **Разрешить проверку подлинности на основе ПИН-кода** в настройках веб-службы.</span><span class="sxs-lookup"><span data-stu-id="5bedd-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="5bedd-106">Дополнительные сведения можно найти [в разделе изменение существующих параметров конфигурации веб-службы в Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5bedd-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="5bedd-107">Выполните следующие действия, чтобы изменить политику ПИН-кода на уровне пользователя или узла.</span><span class="sxs-lookup"><span data-stu-id="5bedd-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a><span data-ttu-id="5bedd-108">Просмотр сведений о политике закрепления на панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="5bedd-108">To view information about a PIN policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5bedd-109">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bedd-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5bedd-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5bedd-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5bedd-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5bedd-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5bedd-112">В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="5bedd-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="5bedd-113">На странице **Политика ПИН-кода** выберите политику, нажмите кнопку **Правка**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="5bedd-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5bedd-114">Просмотр политик ПИН-кода с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bedd-114">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5bedd-115">Вы также можете просматривать политики ПИН с помощью Windows PowerShell и командлета Get-Кспинполици.</span><span class="sxs-lookup"><span data-stu-id="5bedd-115">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="5bedd-116">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bedd-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5bedd-117">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bedd-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pin-policies"></a><span data-ttu-id="5bedd-118">Просмотр политик ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="5bedd-118">To view PIN policies</span></span>

  - <span data-ttu-id="5bedd-119">Чтобы просмотреть сведения обо всех политиках для ПИН-кода, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="5bedd-119">To view information about all your PIN policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPinPolicy
    
    <span data-ttu-id="5bedd-120">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="5bedd-120">That will return information similar to this:</span></span>
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

<span data-ttu-id="5bedd-121">Дополнительные сведения можно найти в разделе справки по командлету [Get-кспинполици](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="5bedd-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5bedd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5bedd-122">See Also</span></span>


[<span data-ttu-id="5bedd-123">Изменение существующих параметров конфигурации веб-службы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bedd-123">Modify existing Web Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[<span data-ttu-id="5bedd-124">Создание новой политики ПИН-кода в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bedd-124">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

