---
title: 'Lync Server 2013: использование расширенного ведения журнала для искусственных транзакций'
description: 'Lync Server 2013: использование расширенного ведения журнала для искусственных транзакций.'
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
ms.openlocfilehash: 5fd984386985bced64265ebedfd57c56a84a4443
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580305"
---
# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="d23cd-103">Использование расширенного ведения журнала для искусственных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d23cd-103">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d23cd-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d23cd-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d23cd-105">Искусственные транзакции (представленные в Microsoft Lync Server 2010) позволяют администраторам проверить, могут ли пользователи успешно выполнять распространенные задачи, такие как вход в систему, Обмен мгновенными сообщениями и звонки на телефон, находящийся в телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="d23cd-105">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d23cd-106">Эти тесты (которые упаковываются в виде набора командлетов Windows PowerShell для Lync Server) могут выполняться вручную администратором или могут быть автоматически запущены приложением, таким как System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d23cd-106">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="d23cd-107">В Lync Server 2010 искусственные транзакции доказались очень полезной, чтобы помочь администраторам выявить проблемы с системой.</span><span class="sxs-lookup"><span data-stu-id="d23cd-107">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="d23cd-108">Например, командлет **Test-CsRegistration** может оповещать администраторов о том, что некоторые пользователи столкнулись с трудностями при регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d23cd-108">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="d23cd-109">Однако искусственные транзакции были несколько менее эффективными, помогая администраторам определить, почему эти пользователи столкнулись с трудностями при регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d23cd-109">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="d23cd-110">Это вызвано тем, что искусственные транзакции не предоставили подробные сведения о ведении журнала, которые могут помочь администраторам устранять неполадки в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d23cd-110">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="d23cd-111">Как правило, подробный вывод искусственной транзакции предоставляет пошаговые инструкции, которые могут позволить администратору выполнить обоснованное предположение, как в случае возникновения проблемы.</span><span class="sxs-lookup"><span data-stu-id="d23cd-111">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="d23cd-112">В Microsoft Lync Server 2013 искусственные транзакции были изменены для создания расширенного ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="d23cd-112">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="d23cd-113">«Расширенная регистрация» означает, что для каждой операции, выполняемого искусственной транзакцией, регистрируется следующая информация:</span><span class="sxs-lookup"><span data-stu-id="d23cd-113">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="d23cd-114">Время начала операции</span><span class="sxs-lookup"><span data-stu-id="d23cd-114">The time that the activity started</span></span>

  - <span data-ttu-id="d23cd-115">Время завершения операции</span><span class="sxs-lookup"><span data-stu-id="d23cd-115">The time that the activity finished</span></span>

  - <span data-ttu-id="d23cd-116">Выполняемое действие (например, создание, присоединение или выход из конференции; вход в Lync Server; Отправка мгновенного сообщения и т. д.)</span><span class="sxs-lookup"><span data-stu-id="d23cd-116">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="d23cd-117">Информационные, подробные сообщения, предупреждения или сообщения об ошибках, которые были созданы при выполнении операции</span><span class="sxs-lookup"><span data-stu-id="d23cd-117">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="d23cd-118">Сообщения о регистрации SIP</span><span class="sxs-lookup"><span data-stu-id="d23cd-118">SIP registration messages</span></span>

  - <span data-ttu-id="d23cd-119">Записи об исключениях или диагностические коды, созданные при выполнении операции</span><span class="sxs-lookup"><span data-stu-id="d23cd-119">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="d23cd-120">Итоговый результат выполнения операции</span><span class="sxs-lookup"><span data-stu-id="d23cd-120">The net result of running the activity</span></span>

<span data-ttu-id="d23cd-121">Эта информация создается автоматически при каждом запуске искусственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="d23cd-121">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="d23cd-122">Однако автоматическое отображение или сохранение сведений в файл журнала не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d23cd-122">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="d23cd-123">Вместо этого администраторы, выполняющие искусственную транзакцию вручную, могут использовать параметр OutLoggerVariable, чтобы указать переменную Windows PowerShell, в которой будут храниться данные.</span><span class="sxs-lookup"><span data-stu-id="d23cd-123">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="d23cd-124">Затем администраторы смогут применять несколько методов, позволяющих сохранять и/или просматривать полный журнал в формате XML или HTML.</span><span class="sxs-lookup"><span data-stu-id="d23cd-124">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="d23cd-125">Например, в случае Lync Server 2010 администраторы могут запустить командлет **Test-CsRegistration** с помощью команды, аналогичной следующей:</span><span class="sxs-lookup"><span data-stu-id="d23cd-125">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="d23cd-126">Администраторы могут включить параметр OutLoggerVariable с последующим именем переменной по своему выбору:</span><span class="sxs-lookup"><span data-stu-id="d23cd-126">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="d23cd-p105">Имени переменной не должен предшествовать символ $. Например, используйте имя переменной RegistrationTest, а не $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="d23cd-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="d23cd-129">Предыдущая команда выводит содержимое, аналогичное следующему:</span><span class="sxs-lookup"><span data-stu-id="d23cd-129">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="d23cd-p106">Однако для данного сбоя доступна гораздо более подробная информация, а не только сообщение об ошибке, представленное выше. Для получения доступа к этой информации в формате HTML используйте команду, аналогичную этой, чтобы сохранить данные, хранящиеся в переменной RegistrationTest, в файл HTML:</span><span class="sxs-lookup"><span data-stu-id="d23cd-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="d23cd-132">Можно также использовать метод ToXML() для сохранения данных в файл XML:</span><span class="sxs-lookup"><span data-stu-id="d23cd-132">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="d23cd-133">Эти файлы можно просмотреть с помощью Internet Explorer, Visual Studio или любого другого приложения, способного открывать файлы HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="d23cd-133">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="d23cd-134">Искусственные транзакции, выполняемые из System Center Operations Manager, будут автоматически создавать эти файлы журналов для сбоев.</span><span class="sxs-lookup"><span data-stu-id="d23cd-134">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="d23cd-135">Однако эти журналы не будут создаваться в случае сбоя выполнения до того, как Windows PowerShell сможет загрузить и запустить искусственную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="d23cd-135">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="d23cd-136">По умолчанию Lync Server 2013 сохраняет файлы журнала в папку, к которой не предоставлен общий доступ.</span><span class="sxs-lookup"><span data-stu-id="d23cd-136">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="d23cd-137">Чтобы сделать эти журналы общедоступными, необходимо поделиться этой папкой (например, \\ \\ ATL-наблюдатель-001. litwareinc. ком\ватчерноде.</span><span class="sxs-lookup"><span data-stu-id="d23cd-137">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

