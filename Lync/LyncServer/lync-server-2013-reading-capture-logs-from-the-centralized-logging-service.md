---
title: 'Lync Server 2013: чтение журналов записи из службы централизованного ведения журналов'
description: 'Lync Server 2013: чтение журналов записи из централизованной службы ведения журналов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559165"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="97b91-103">Чтение журналов записи из службы централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97b91-103">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97b91-104">_**Последнее изменение темы:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="97b91-104">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="97b91-105">Вы осознаете реальную пользу централизованной службы ведения журналов после выполнения поиска, и у вас есть файл, который можно использовать для отслеживания обнаруженной проблемы.</span><span class="sxs-lookup"><span data-stu-id="97b91-105">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="97b91-106">Существует несколько способов чтения файла.</span><span class="sxs-lookup"><span data-stu-id="97b91-106">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="97b91-107">Выходной файл находится в стандартном текстовом формате, и вы можете использовать Notepad.exe или другие программы, позволяющие открыть и прочитать текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="97b91-107">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="97b91-108">Для больших файлов и более сложных проблем можно использовать такие средства, как Snooper.exe, предназначенные для чтения и анализа выходных данных журнала из службы централизованного ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="97b91-108">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="97b91-109">Snooper входит в состав средств отладки Lync Server 2013, которые можно загрузить отдельно.</span><span class="sxs-lookup"><span data-stu-id="97b91-109">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="97b91-110">Вы можете скачать инструменты отладки Lync Server 2013 здесь: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) .</span><span class="sxs-lookup"><span data-stu-id="97b91-110">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="97b91-111">При установке средств отладки Lync Server 2013, ярлыки сокращений и пункты меню не создаются.</span><span class="sxs-lookup"><span data-stu-id="97b91-111">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="97b91-112">После установки средств отладки Lync Server 2013 откройте проводник Windows, окно командной строки или командную консоль Lync Server и перейдите к каталогу (расположение по умолчанию) C: \\ Program Files \\ Microsoft Lync Server 2013 \\ средства отладки.</span><span class="sxs-lookup"><span data-stu-id="97b91-112">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="97b91-113">Дважды щелкните Snooper.exe или введите Snooper.exe, а затем нажмите клавишу ВВОД, если используется Командная строка или Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97b91-113">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97b91-114">Цель этого раздела — не подробное описание способов устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="97b91-114">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="97b91-115">Устранение неполадок и процессы, связанные с ней, — сложная тема.</span><span class="sxs-lookup"><span data-stu-id="97b91-115">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="97b91-116">Для получения подробных сведений об устранении неполадок и устранении неполадок в определенных рабочих нагрузках обратитесь к книге Office Lync Server 2010 Resource Kit по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> .</span><span class="sxs-lookup"><span data-stu-id="97b91-116">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="97b91-117">Процессы и процедуры по-прежнему применяются к Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97b91-117">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="97b91-118">Lync Server 2013 содержит обновленную версию Snooper, которая включает некоторые новые функции.</span><span class="sxs-lookup"><span data-stu-id="97b91-118">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="97b91-119">На следующем снимке экрана показана версия Snooper из Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97b91-119">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="97b91-120">![Office Communications 2007 версии Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 версии Snooper.")</span><span class="sxs-lookup"><span data-stu-id="97b91-120">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="97b91-121">На следующем снимке экрана показана новая версия Snooper, включенная в средства отладки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97b91-121">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="97b91-122">![Lync Server 2013 версии Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 версии Snooper.")</span><span class="sxs-lookup"><span data-stu-id="97b91-122">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="97b91-123">На следующем снимке экрана показана панель инструментов с часто используемыми функциями.</span><span class="sxs-lookup"><span data-stu-id="97b91-123">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="97b91-124">![Панель инструментов Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Панель инструментов Snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="97b91-124">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="97b91-125">И последним компонентом, добавляющим значение, является представление диаграммы "блок-схема (звонок)".</span><span class="sxs-lookup"><span data-stu-id="97b91-125">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="97b91-126">Вы выбираете процесс обработки сообщений на вкладке **сообщение** и нажимайте кнопку **подавать запрос** .</span><span class="sxs-lookup"><span data-stu-id="97b91-126">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="97b91-127">По мере продвижения по сообщениям схема "процесс обработки вызовов" обновляет новые данные.</span><span class="sxs-lookup"><span data-stu-id="97b91-127">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="97b91-128">![Схема последовательности вызовов Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Схема последовательности вызовов Snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="97b91-128">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="97b91-129">Вы можете навести указатель мыши на представление схемы и получить сведения о сообщениях и содержимом потоков и сообщений, а также серверных элементов.</span><span class="sxs-lookup"><span data-stu-id="97b91-129">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="97b91-130">Щелкните стрелку на любой из походящих вызовов, чтобы перейти к сообщению в представлении сообщения.</span><span class="sxs-lookup"><span data-stu-id="97b91-130">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="97b91-131">![Сведения о схеме "последовательность вызовов" сообщения.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Сведения о схеме "последовательность вызовов" сообщения.")</span><span class="sxs-lookup"><span data-stu-id="97b91-131">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="97b91-132">Открытие файла журнала в Snooper</span><span class="sxs-lookup"><span data-stu-id="97b91-132">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="97b91-133">Для использования Snooper и открытия файлов журнала необходим доступ для чтения к файлам журнала.</span><span class="sxs-lookup"><span data-stu-id="97b91-133">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="97b91-134">Чтобы использовать Snooper и получать доступ к файлам журнала, необходимо быть участником групп безопасности CsAdministrator или CsServerAdministrator управления доступом на основе ролей (RBAC) или настраиваемой роли RBAC, которая содержит любую из этих групп.</span><span class="sxs-lookup"><span data-stu-id="97b91-134">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="97b91-135">После установки средств отладки Lync Server (LyncDebugTools.msi) измените каталог на расположение Snooper.exe с помощью проводника Windows или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="97b91-135">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="97b91-136">По умолчанию инструменты отладки расположены в C: \\ Program Files \\ Microsoft Lync Server 2013 \\ Tools.</span><span class="sxs-lookup"><span data-stu-id="97b91-136">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="97b91-137">Дважды щелкните или запустите Snooper.exe.</span><span class="sxs-lookup"><span data-stu-id="97b91-137">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="97b91-138">После открытия Snooper щелкните правой кнопкой мыши **файл**, выберите команду **OpenFile**, найдите файлы журнала, выберите нужный файл в диалоговом окне **Открыть** , а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="97b91-138">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="97b91-139">Сообщения **трассировки** файла журнала отображаются на вкладке **Трассировка** . Щелкните вкладку **Messages (сообщения** ), чтобы просмотреть содержимое собранных трассировок.</span><span class="sxs-lookup"><span data-stu-id="97b91-139">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="97b91-140">Отображение схемы последовательности вызовов</span><span class="sxs-lookup"><span data-stu-id="97b91-140">To display a call flow diagram</span></span>

1.  <span data-ttu-id="97b91-141">Для использования Snooper и открытия файлов журнала необходим доступ для чтения к файлам журнала.</span><span class="sxs-lookup"><span data-stu-id="97b91-141">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="97b91-142">Чтобы использовать Snooper и получать доступ к файлам журнала, необходимо быть участником групп безопасности CsAdministrator или CsServerAdministrator управления доступом на основе ролей (RBAC) или настраиваемой роли RBAC, которая содержит любую из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="97b91-142">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="97b91-143">Откройте файл журнала и перейдите на вкладку **сообщения** , выберите беседу в представлении сообщения или выберите компонент трассировки на вкладке **Трассировка** .</span><span class="sxs-lookup"><span data-stu-id="97b91-143">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="97b91-144">Нажмите кнопку **Flow Call (вызов**).</span><span class="sxs-lookup"><span data-stu-id="97b91-144">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97b91-145">Если щелкнуть сообщение или трассировку, которые не входят в последовательность вызовов, схема не будет отображаться, а в нижней части Snooper появляется сообщение о состоянии "это сообщение не подходит для каллфов".</span><span class="sxs-lookup"><span data-stu-id="97b91-145">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="97b91-146">Выберите другое сообщение или трассировку, и он будет отображаться, если сообщение или трассировка входят в последовательность вызовов.</span><span class="sxs-lookup"><span data-stu-id="97b91-146">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="97b91-147">Перемещение по сообщениям или строкам трассировки и обратите внимание на то, что схема "последовательность вызовов" обновляет или изменяет, чтобы отобразить новую схему.</span><span class="sxs-lookup"><span data-stu-id="97b91-147">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="97b91-148">Наведите указатель мыши на элемент, чтобы получить сведения о сообщениях вызовов, конечных точках и других компонентах.</span><span class="sxs-lookup"><span data-stu-id="97b91-148">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

