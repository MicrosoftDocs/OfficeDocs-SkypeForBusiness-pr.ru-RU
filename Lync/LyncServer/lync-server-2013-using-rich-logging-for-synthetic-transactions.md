---
title: 'Lync Server 2013: использование расширенного ведения журнала для искусственных транзакций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48efc99a49fd41678d07eef8685bc7f045397aa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="19bfc-102">Использование расширенного ведения журнала для виртуальных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19bfc-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19bfc-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="19bfc-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="19bfc-104">Синтетические транзакции (введенные в Microsoft Lync Server 2010) предоставляют администраторам способ проверки того, что пользователи могут успешно выполнять типичные задачи, такие как вход в систему, Обмен мгновенными сообщениями и звонки на телефоны, находящиеся в сети в коммутируемой телефонной сети общего пользования (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="19bfc-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="19bfc-105">Эти тесты (которые упаковываются в набор командлетов Windows PowerShell для Lync Server) могут быть проведены вручную администратором или автоматически запускаться приложением, таким как System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="19bfc-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="19bfc-106">В Lync Server 2010 искусственные транзакции доносятся чрезвычайно полезными для облегчения администраторам выявления проблем системы.</span><span class="sxs-lookup"><span data-stu-id="19bfc-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="19bfc-107">Например, командлет **Test-ксрегистратион** может оповещать администраторов о том, что некоторые пользователи столкнулись с проблемами при регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19bfc-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="19bfc-108">Тем не менее, эти искусственные транзакции не помогают администраторам определить, почему пользователи столкнулись с проблемами при регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19bfc-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="19bfc-109">Это произошло из-за того, что искусственные транзакции не предоставили подробные сведения для ведения журнала, которые могут помочь администраторам устранить проблемы с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19bfc-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="19bfc-110">Лучше всего получить подробный вывод из искусственной транзакции с пошаговыми инструкциями, которые могут позволить администратору создать обоснованное предположение, в котором может возникнуть проблема.</span><span class="sxs-lookup"><span data-stu-id="19bfc-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="19bfc-111">В Microsoft Lync Server 2013 искусственные транзакции, созданные с богатым протоколированием, сконструированы заново.</span><span class="sxs-lookup"><span data-stu-id="19bfc-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="19bfc-112">"Ведение подробного протоколирования" означает, что для каждого действия, которое занимает виртуальная транзакция, такие данные будут записаны следующим образом:</span><span class="sxs-lookup"><span data-stu-id="19bfc-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="19bfc-113">Время начала действия</span><span class="sxs-lookup"><span data-stu-id="19bfc-113">The time that the activity started</span></span>

  - <span data-ttu-id="19bfc-114">Время завершения действия</span><span class="sxs-lookup"><span data-stu-id="19bfc-114">The time that the activity finished</span></span>

  - <span data-ttu-id="19bfc-115">Выполняемое действие (например, создание, присоединение или выход из конференции; вход на сервер Lync Server; Отправка мгновенного сообщения и т. д.)</span><span class="sxs-lookup"><span data-stu-id="19bfc-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="19bfc-116">Информационные, подробные сообщения, предупреждения или сообщения об ошибках, которые были созданы при выполнении операции</span><span class="sxs-lookup"><span data-stu-id="19bfc-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="19bfc-117">Сообщения регистрации SIP</span><span class="sxs-lookup"><span data-stu-id="19bfc-117">SIP registration messages</span></span>

  - <span data-ttu-id="19bfc-118">Записи исключений или коды диагностики, созданные при выполнении действия</span><span class="sxs-lookup"><span data-stu-id="19bfc-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="19bfc-119">Итоговый результат выполнения действия</span><span class="sxs-lookup"><span data-stu-id="19bfc-119">The net result of running the activity</span></span>

<span data-ttu-id="19bfc-120">Эта информация создается автоматически каждый раз при выполнении искусственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="19bfc-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="19bfc-121">Однако эти сведения не отображаются и не сохраняются в файле журнала автоматически.</span><span class="sxs-lookup"><span data-stu-id="19bfc-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="19bfc-122">Вместо этого администраторы, которые вручную загружают искусственную транзакцию, могут использовать параметр Аутлогжервариабле для указания переменной Windows PowerShell, в которой будут храниться данные.</span><span class="sxs-lookup"><span data-stu-id="19bfc-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="19bfc-123">После этого администраторы могут использовать пару методов, которые позволяют им сохранять и (или) просматривать расширенный журнал в формате XML или HTML.</span><span class="sxs-lookup"><span data-stu-id="19bfc-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="19bfc-124">Например, для Lync Server 2010 администраторы могут выполнить командлет **Test-ксрегистратион** , выполнив команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="19bfc-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="19bfc-125">Администраторы могут включить параметр Аутлогжервариабле, за которым следует имя переменной, выбирая указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="19bfc-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="19bfc-126">Не дополняйте перед именем переменной символа $.</span><span class="sxs-lookup"><span data-stu-id="19bfc-126">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="19bfc-127">Используйте имя переменной, например Регистратионтест, а не $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="19bfc-127">Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="19bfc-128">Предыдущая команда выводит содержимое, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="19bfc-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="19bfc-129">Тем не менее, в этой ошибке есть больше подробных сведений, чем просто сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="19bfc-129">However, much more detailed information is available for this failure than just the error message shown above.</span></span> <span data-ttu-id="19bfc-130">Чтобы получить доступ к этим сведениям в формате HTML, используйте следующую команду для сохранения данных, сохраненных в переменной Регистратионтест, в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="19bfc-130">To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="19bfc-131">Можно также использовать метод ToXML() для сохранения данных в файл XML:</span><span class="sxs-lookup"><span data-stu-id="19bfc-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="19bfc-132">Эти файлы можно будет просматривать с помощью Internet Explorer, Visual Studio или других приложений, которые могут открывать HTML-и XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="19bfc-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="19bfc-133">Синтетические транзакции, выполненные из системы System Center Operations Manager, будут автоматически создавать эти файлы журнала для сбоев.</span><span class="sxs-lookup"><span data-stu-id="19bfc-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="19bfc-134">Однако эти журналы не будут создаваться, если выполнение завершается сбоем до того, как Windows PowerShell сможет загрузить и выполнить виртуальную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="19bfc-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="19bfc-135">По умолчанию Lync Server 2013 сохраняет файлы журнала в папке, к которой не предоставлен общий доступ.</span><span class="sxs-lookup"><span data-stu-id="19bfc-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="19bfc-136">Чтобы сделать эти журналы общедоступными, нужно поделиться этой папкой (например, \\ \\ATL-наблюдатель-001. плана litwareinc. ком\ватчерноде.</span><span class="sxs-lookup"><span data-stu-id="19bfc-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

