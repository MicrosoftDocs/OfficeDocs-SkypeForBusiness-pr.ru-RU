---
title: 'Lync Server 2013: тестирование разрешений на активацию служб и групп'
description: 'Lync Server 2013: тестирование разрешений на активацию служб и групп.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116cf939f3110616ce395eb14c7945890bdb89b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556265"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="d801b-103">Тестирование разрешений на активацию служб и групп в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d801b-103">Testing service activation and group permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d801b-104">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d801b-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d801b-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="d801b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d801b-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="d801b-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d801b-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="d801b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d801b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d801b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d801b-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="d801b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d801b-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d801b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d801b-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="d801b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="d801b-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d801b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d801b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d801b-113">Description</span></span>

<span data-ttu-id="d801b-114">Командлет Test-CsTopology позволяет убедиться, что Lync Server 2013 правильно работает в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="d801b-114">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="d801b-115">По умолчанию командлет проверяет всю инфраструктуру Lync Server, проверяя, что необходимые службы запущены и установлены ли соответствующие разрешения для этих служб, а также для универсальных групп безопасности, создаваемых при установке Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d801b-115">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="d801b-116">Кроме проверки допустимости установки Lync Server, Test-CsTopology также позволяет проверить допустимость определенной службы.</span><span class="sxs-lookup"><span data-stu-id="d801b-116">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="d801b-117">Например, эта команда проверяет состояние сервера аудио-и видеоконференций в пуле atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="d801b-117">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d801b-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="d801b-118">Running the test</span></span>

<span data-ttu-id="d801b-119">По умолчанию на экране Test-CsTopology отображаются очень мелкие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d801b-119">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="d801b-120">Вместо этого сведения, возвращаемые командлетом, записываются в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="d801b-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="d801b-121">Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="d801b-121">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="d801b-122">Если не включить параметр отчета, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь имя, аналогичное следующему: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="d801b-122">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="d801b-123">В приведенном ниже примере команда выполняет Test-CsTopology и сохраняет выходные данные в файл с именем C: \\ Logs \\ComputerTest.html:</span><span class="sxs-lookup"><span data-stu-id="d801b-123">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="d801b-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .</span><span class="sxs-lookup"><span data-stu-id="d801b-124">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d801b-125">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="d801b-125">Determining success or failure</span></span>

<span data-ttu-id="d801b-126">В отличие от большинства командлетов тестирования, Test-CsTopology отправляет отчет об успешном выполнении или сбое.</span><span class="sxs-lookup"><span data-stu-id="d801b-126">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="d801b-127">Частично это вызвано большим количеством проверок, которые командлет должен выполнять при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="d801b-127">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="d801b-128">Вместо этого данные сохраняются в HTML-отчете, который можно просмотреть с помощью Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d801b-128">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d801b-129">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="d801b-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="d801b-130">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsTopology:</span><span class="sxs-lookup"><span data-stu-id="d801b-130">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="d801b-131">Репликация может быть неактуальной на тестовом компьютере.</span><span class="sxs-lookup"><span data-stu-id="d801b-131">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="d801b-132">Вы можете проверить текущее состояние репликации для компьютера, выполнив командлет Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="d801b-132">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="d801b-133">Если состояние репликации устарело, можно вручную выполнить репликацию с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="d801b-133">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="d801b-134">Возможно, топология включена.</span><span class="sxs-lookup"><span data-stu-id="d801b-134">The topology might have to be enabled.</span></span> <span data-ttu-id="d801b-135">При изменении топологии Lync Server (изменений, которые могут повлиять на локальный компьютер) необходимо включить новую топологию.</span><span class="sxs-lookup"><span data-stu-id="d801b-135">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="d801b-136">Вы можете включить топологию в любое время, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d801b-136">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

