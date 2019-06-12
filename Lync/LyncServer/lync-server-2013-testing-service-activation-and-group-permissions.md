---
title: 'Lync Server 2013: Проверка разрешений на активацию служб и групп'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6616e1f2835ab55f9e3e8f98e5a8693ef3d2fb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="ce8a3-102">Проверка разрешений на активацию служб и групп в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce8a3-102">Testing service activation and group permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce8a3-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ce8a3-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce8a3-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="ce8a3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ce8a3-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="ce8a3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce8a3-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="ce8a3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ce8a3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce8a3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce8a3-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="ce8a3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ce8a3-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ce8a3-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кстопологи.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="ce8a3-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ce8a3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ce8a3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ce8a3-112">Description</span></span>

<span data-ttu-id="ce8a3-113">Командлет Test-Кстопологи позволяет проверить, правильно ли работает Lync Server 2013 в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="ce8a3-114">По умолчанию командлет проверяет всю инфраструктуру сервера Lync, убедившись в том, что необходимые службы запущены и установлены соответствующие разрешения для этих служб, а также для универсальных групп безопасности, которые создаются при установке Lync Server. .</span><span class="sxs-lookup"><span data-stu-id="ce8a3-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="ce8a3-115">Помимо проверки действительности установки Lync Server, Test-Кстопологи также позволяет проверить правильность определенной службы.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="ce8a3-116">Например, эта команда проверяет состояние сервера конференц-связи A/V в пуле atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ce8a3-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ce8a3-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="ce8a3-117">Running the test</span></span>

<span data-ttu-id="ce8a3-118">По умолчанию в режиме Test-Кстопологи отображается очень мало вывода на экран.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="ce8a3-119">Вместо этого данные, возвращаемые командлетом, записываются в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="ce8a3-120">Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-Кстопологи.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="ce8a3-121">Если параметр отчета не указан, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь такое имя, как: ce84964a-c4da-4622-ad34-c54ff3ed361f. HTML.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="ce8a3-122">В следующем образце команды запускается Test-Кстопологи и сохраняются выходные данные в файле с именем C:\\Logs\\компутертест. HTML.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="ce8a3-123">Дополнительные сведения можно найти в справочной документации по командлету [Test-кстопологи](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .</span><span class="sxs-lookup"><span data-stu-id="ce8a3-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ce8a3-124">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="ce8a3-124">Determining success or failure</span></span>

<span data-ttu-id="ce8a3-125">В отличие от большинства командлетов теста, Test-Кстопологи сообщает об успешном завершении или сбое.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="ce8a3-126">Частично, это связано с большим количеством проверок, которое командлет должен выполнять каждый раз при запуске.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="ce8a3-127">Вместо этого данные сохраняются в отчете в формате HTML, который затем можно просматривать с помощью Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ce8a3-128">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="ce8a3-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="ce8a3-129">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кстопологи:</span><span class="sxs-lookup"><span data-stu-id="ce8a3-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="ce8a3-130">Репликация может быть неактуальной на тестовом компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="ce8a3-131">Вы можете проверить текущее состояние репликации для компьютера, выполнив командлет Get-Ксманажементсторерепликатионстатус:</span><span class="sxs-lookup"><span data-stu-id="ce8a3-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="ce8a3-132">Если состояние репликации не устарело, вы можете вручную выполнить принудительную репликацию с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="ce8a3-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="ce8a3-133">Возможно, требуется включить топологию.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-133">The topology might have to be enabled.</span></span> <span data-ttu-id="ce8a3-134">Если вы измените топологию Lync Server (изменения, которые могут повлиять на локальный компьютер), необходимо включить новую топологию.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="ce8a3-135">Вы можете включить топологию в любое время, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ce8a3-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

