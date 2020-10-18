---
title: 'Lync Server 2013: тестирование служб Lync Server'
description: 'Lync Server 2013: тестирование служб Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f04cf5e0c098c671b6fb126d4607f3cdba107712
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575225"
---
# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="7296a-103">Тестирование служб Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7296a-103">Testing Lync Server services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7296a-104">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7296a-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7296a-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="7296a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7296a-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="7296a-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7296a-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="7296a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7296a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7296a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7296a-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="7296a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7296a-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7296a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7296a-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7296a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="7296a-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7296a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7296a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7296a-113">Description</span></span>

<span data-ttu-id="7296a-114">Test-CsComputer проверяет состояние всех служб Lync Server 2013, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7296a-114">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="7296a-115">(Test-CsComputer можно запускать только локально, его нельзя запустить из удаленного экземпляра Windows PowerShell.) Командлет также проверяет, открыты ли на компьютере соответствующие порты брандмауэра, и определяет, были ли группы Active Directory, созданные при установке Lync Server 2013, добавлены в соответствующие локальные группы.</span><span class="sxs-lookup"><span data-stu-id="7296a-115">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="7296a-116">Например, Test-CsComputer будет проверять, была ли группа Active Directory RTCUniversalUserAdmins добавлена в группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="7296a-116">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="7296a-117">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="7296a-117">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7296a-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="7296a-118">Running the test</span></span>

<span data-ttu-id="7296a-119">Командлет Test-CsComputer можно запускать только на локальном компьютере, вы не можете вызывать Test-CsComputer из удаленного экземпляра Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7296a-119">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="7296a-120">По умолчанию Test-CsComputer отображает очень маленький вывод на экран, а данные, возвращаемые командлетом, записываются в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="7296a-120">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="7296a-121">Из-за этого мы рекомендуем включить параметр Verbose и параметр отчета каждый раз при запуске test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7296a-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="7296a-122">Параметр verbose предоставит немного более подробный вывод на экран при выполнении командлета.</span><span class="sxs-lookup"><span data-stu-id="7296a-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="7296a-123">Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7296a-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="7296a-124">Если не включить параметр отчета, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь имя, аналогичное следующему: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="7296a-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="7296a-125">В приведенном ниже примере команда выполняет Test-CsComputer и сохраняет выходные данные в файл с именем C: \\ Logs \\ComputerTest.html:</span><span class="sxs-lookup"><span data-stu-id="7296a-125">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="7296a-126">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="7296a-126">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7296a-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="7296a-127">Determining success or failure</span></span>

<span data-ttu-id="7296a-128">Из-за количества проверок, выполняемых для проверки, Test-CsComputer не сообщает о простом **Да, тест успешно выполнен** или **нет, тест завершился ошибкой**.</span><span class="sxs-lookup"><span data-stu-id="7296a-128">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="7296a-129">Вместо этого необходимо просмотреть созданный HTML-файл с помощью Internet Explorer, чтобы определить успешность или неудачу каждого теста.</span><span class="sxs-lookup"><span data-stu-id="7296a-129">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7296a-130">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="7296a-130">Reasons why the test might have failed</span></span>

<span data-ttu-id="7296a-131">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsComputer:</span><span class="sxs-lookup"><span data-stu-id="7296a-131">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="7296a-132">Тестовый компьютер не может быть включен для использования с сервером Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7296a-132">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="7296a-133">Это может произойти, если на компьютере были изменены серверные службы или роли сервера Lync, а командлет Enable-CsComputer не был запущен.</span><span class="sxs-lookup"><span data-stu-id="7296a-133">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="7296a-134">Для устранения этой неполадки выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7296a-134">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="7296a-135">Репликация может быть не актуальна на тестовом компьютере.</span><span class="sxs-lookup"><span data-stu-id="7296a-135">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="7296a-136">Вы можете проверить текущее состояние репликации для компьютера, выполнив командлет Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="7296a-136">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="7296a-137">Если состояние репликации устарело, можно вручную выполнить репликацию с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="7296a-137">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="7296a-138">Возможно, топология включена.</span><span class="sxs-lookup"><span data-stu-id="7296a-138">The topology might have to be enabled.</span></span> <span data-ttu-id="7296a-139">При изменении топологии Lync Server (изменений, которые могут повлиять на локальный компьютер) необходимо включить новую топологию.</span><span class="sxs-lookup"><span data-stu-id="7296a-139">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="7296a-140">Вы можете включить топологию в любое время, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7296a-140">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

