---
title: 'Lync Server 2013: Проверка служб Lync Server'
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
ms.openlocfilehash: bdafd84f5a8edd21d6e62433d028ed735e37a37d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="5f3a2-102">Тестирование служб Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f3a2-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f3a2-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5f3a2-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f3a2-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="5f3a2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5f3a2-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="5f3a2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3a2-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="5f3a2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5f3a2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f3a2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3a2-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="5f3a2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5f3a2-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5f3a2-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кскомпутер.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="5f3a2-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5f3a2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5f3a2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5f3a2-112">Description</span></span>

<span data-ttu-id="5f3a2-113">Test-Кскомпутер проверяет состояние всех служб Lync Server 2013, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="5f3a2-114">(Test-Кскомпутер можно выполнять только локально, и его невозможно запустить из удаленного экземпляра Windows PowerShell.) Командлет также проверяет, открыты ли на компьютере соответствующие порты брандмауэра, и определяет, были ли группы Active Directory, созданные при установке сервера Lync Server 2013, добавлены в соответствующие локальные группы.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="5f3a2-115">Например, с помощью теста-Кскомпутер вы увидите, что группа Active Directory Рткуниверсалусерадминс была добавлена в группу "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="5f3a2-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="5f3a2-116">Дополнительные сведения можно найти в справочной документации по командлету [Test-кскомпутер](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="5f3a2-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5f3a2-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="5f3a2-117">Running the test</span></span>

<span data-ttu-id="5f3a2-118">Командлет Test-Кскомпутер можно запускать только на локальном компьютере, но вы не можете вызвать Test-Кскомпутер из удаленного экземпляра Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="5f3a2-119">По умолчанию в режиме Test-Кскомпутер отображается очень мало вывода на экран, а данные, возвращаемые командлетом, записываются в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="5f3a2-120">По этой причине мы рекомендуем включать параметр подробных данных и параметр отчета каждый раз при запуске test-Кскомпутер.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="5f3a2-121">Параметр verbose обеспечивает немного более подробный вывод на экран во время выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="5f3a2-122">Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-Кскомпутер.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="5f3a2-123">Если параметр отчета не указан, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь такое имя, как: ce84964a-c4da-4622-ad34-c54ff3ed361f. HTML.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="5f3a2-124">В следующем образце команды запускается Test-Кскомпутер и сохраняются выходные данные в файле с именем C:\\Logs\\компутертест. HTML.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="5f3a2-125">Дополнительные сведения можно найти в справочной документации по командлету [Test-кскомпутер](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="5f3a2-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5f3a2-126">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="5f3a2-126">Determining success or failure</span></span>

<span data-ttu-id="5f3a2-127">Из-за количества выполняемых проверок тестов и Кскомпутер не сообщается о том, что проверка **выполнена успешно** или **нет, тест завершился сбоем**.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="5f3a2-128">Вместо этого вам нужно будет просмотреть созданный HTML-файл с помощью Internet Explorer, чтобы определить успешность или сбой каждого теста.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5f3a2-129">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="5f3a2-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="5f3a2-130">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кскомпутер:</span><span class="sxs-lookup"><span data-stu-id="5f3a2-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="5f3a2-131">Тестовый компьютер может быть недоступен для использования с сервером Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="5f3a2-132">Это может произойти, если вы изменили серверные службы Lync или серверные роли на компьютере, а командлет Enable-Кскомпутер не был запущен.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="5f3a2-133">Чтобы устранить эту проблему, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5f3a2-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="5f3a2-134">Репликация может быть не актуальна на тестовом компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="5f3a2-135">Вы можете проверить текущее состояние репликации для компьютера, выполнив командлет Get-Ксманажементсторерепликатионстатус:</span><span class="sxs-lookup"><span data-stu-id="5f3a2-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="5f3a2-136">Если состояние репликации не устарело, вы можете вручную выполнить принудительную репликацию с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5f3a2-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="5f3a2-137">Возможно, требуется включить топологию.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-137">The topology might have to be enabled.</span></span> <span data-ttu-id="5f3a2-138">Если вы измените топологию Lync Server (изменения, которые могут повлиять на локальный компьютер), необходимо включить новую топологию.</span><span class="sxs-lookup"><span data-stu-id="5f3a2-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="5f3a2-139">Вы можете включить топологию в любое время, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5f3a2-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

