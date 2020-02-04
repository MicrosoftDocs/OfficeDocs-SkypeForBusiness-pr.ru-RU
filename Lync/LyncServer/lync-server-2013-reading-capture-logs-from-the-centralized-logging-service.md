---
title: 'Lync Server 2013: чтение журналов записи из централизованной службы ведения журналов'
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
ms.openlocfilehash: 2713c9a1209aad4a96fcb3a76afaf7c2bc61c0dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="aa0bc-102">Чтение журналов захвата из службы централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa0bc-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa0bc-103">_**Тема последнего изменения:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="aa0bc-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="aa0bc-104">Вы осознаете реальное преимущество централизованной службы ведения журналов после выполнения поиска и наличии файла, который можно использовать для отслеживания обнаруженной проблемы.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="aa0bc-105">There are a number of ways that you can read the file.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="aa0bc-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="aa0bc-107">Для больших файлов и более сложных проблем можно использовать средство, например Снупер. exe, которое предназначено для чтения и анализа результатов ведения журнала из централизованной службы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="aa0bc-108">Снупер входит в состав средств отладки Lync Server 2013, которые можно загрузить отдельно.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="aa0bc-109">Вы можете скачать инструменты для отладки Lync Server 2013 отсюда: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span><span class="sxs-lookup"><span data-stu-id="aa0bc-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="aa0bc-110">При установке средств отладки Lync Server 2013 не создаются короткие команды и элементы меню.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="aa0bc-111">После установки средств отладки Lync Server 2013 откройте проводник Windows, окно командной строки или консоль управления Lync Server Management Shell и перейдите в каталог (расположение по умолчанию) C:\\Program Files\\Microsoft Lync Server 2013\\инструменты отладки.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="aa0bc-112">Дважды щелкните Снупер. exe или введите Снупер. exe, а затем нажмите клавишу ВВОД, если вы используете командную строку или командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aa0bc-113">В цели этого раздела не входит подробное обсуждение методов диагностики.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="aa0bc-114">Диагностика и сопутствующие процессы являются сложной темой.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="aa0bc-115">Подробные сведения об устранении неполадок и устранении неполадок при определенных нагрузках можно найти в книге набор ресурсов Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Lync Server 2010 по адресу.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="aa0bc-116">Процессы и процедуры по-прежнему применяются к Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="aa0bc-117">Lync Server 2013 представляет обновленную версию Снупер, которая включает некоторые новые возможности.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="aa0bc-118">На приведенном ниже снимке экрана показана версия Снупер из Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="aa0bc-119">![Office Communications 2007 версии Снупер.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 версии Снупер.")</span><span class="sxs-lookup"><span data-stu-id="aa0bc-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="aa0bc-120">На приведенном ниже снимке экрана показана новая версия Снупер, которая входит в состав средств отладки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="aa0bc-121">![Версия Снупер для Lync Server 2013.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Версия Снупер для Lync Server 2013.")</span><span class="sxs-lookup"><span data-stu-id="aa0bc-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="aa0bc-122">На приведенном ниже снимке экрана показана панель инструментов с часто используемыми функциями.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="aa0bc-123">![Панель инструментов снупер 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Панель инструментов снупер 2013.")</span><span class="sxs-lookup"><span data-stu-id="aa0bc-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="aa0bc-124">И самой новой функцией, добавляющей значение, является представление схема блок-схемы (поток звонков).</span><span class="sxs-lookup"><span data-stu-id="aa0bc-124">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="aa0bc-125">Вы выбираете поток сообщений на вкладке **сообщение** и нажимайте кнопку **поток звонка** .</span><span class="sxs-lookup"><span data-stu-id="aa0bc-125">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="aa0bc-126">По мере продвижения по сообщениям схема потока звонка обновляется новыми данными.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-126">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="aa0bc-127">![Схема потока вызовов снупер 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Схема потока вызовов снупер 2013.")</span><span class="sxs-lookup"><span data-stu-id="aa0bc-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="aa0bc-128">Вы можете навести указатель мыши на представление схемы и получить подробные сведения о сообщениях и содержимом потоков и сообщений, а также об элементах сервера.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-128">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="aa0bc-129">Щелкните стрелку на любом месте вызова, чтобы перейти к сообщению в представлении сообщения.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-129">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="aa0bc-130">![Сведения о сообщении о схеме потока звонков.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Сведения о сообщении о схеме потока звонков.")</span><span class="sxs-lookup"><span data-stu-id="aa0bc-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="aa0bc-131">Открытие файла журнала в Snooper</span><span class="sxs-lookup"><span data-stu-id="aa0bc-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="aa0bc-p106">Для использования Snooper и открытия файлов журналов требуется доступ на чтение файлов журналов. Чтобы использовать Snooper и получить доступ к файлам журналов, необходимо быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator либо членом настраиваемой роли RBAC, содержащей эти две группы.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-p106">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="aa0bc-134">После установки средств отладки Lync Server (Линкдебугтулс. msi) измените каталог на расположение Снупер. exe с помощью проводника или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="aa0bc-135">По умолчанию инструменты отладки находятся в C:\\Program Files\\Microsoft Lync Server 2013\\средства отладки.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="aa0bc-136">Дважды щелкните файл Snooper.exe или запустите его.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="aa0bc-137">После открытия Snooper щелкните правой кнопкой мыши пункт **File** (Файл), выберите пункт **Open File** (Открыть файл), найдите файлы журнала, выберите нужный файл в диалоговом окне **открытия файла** и нажмите кнопку **Open** (Открыть).</span><span class="sxs-lookup"><span data-stu-id="aa0bc-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="aa0bc-138">Сообщения **трассировки** появятся на вкладке **Trace** (Трассировка). Щелкните вкладку **Messages** (Сообщения), чтобы просмотреть контент сообщений собранных трассировок.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="aa0bc-139">Отображение схемы потока вызовов</span><span class="sxs-lookup"><span data-stu-id="aa0bc-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="aa0bc-p108">Для использования Snooper и открытия файлов журналов требуется доступ на чтение файлов журналов. Чтобы использовать Snooper и получить доступ к файлам журналов, вы должны быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator либо членом настраиваемой роли RBAC, содержащей эти две группы.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-p108">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="aa0bc-142">Откройте файл журнала и перейдите на вкладку **Messages** (Сообщения); выберите беседу в представлении сообщений или выберите компонент трассировки на вкладке **Trace** (Трассировка).</span><span class="sxs-lookup"><span data-stu-id="aa0bc-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="aa0bc-143">Нажмите **Call Flow** (Поток вызовов).</span><span class="sxs-lookup"><span data-stu-id="aa0bc-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa0bc-p109">Если щелкнуть сообщение или трассировку, не являющуюся частью потока вызовов, то схема не появится, и внизу экрана Snooper появится сообщение о состоянии "This message is not eligible for callfow" ("Это сообщение неприемлемо для потока вызовов"). Выберите другое сообщение или трассировку, и если это сообщение или трассировка является частью потока вызовов, то появится поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-p109">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”. Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="aa0bc-146">Пройдите по строкам сообщений или трассировки и обратите внимание, отображают ли обновления или изменения схемы потока вызовов новую схему.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="aa0bc-147">Помещайте указатель мыши поверх элементов, чтобы получить сведения о сообщениях, конечных точках и других компонентах вызовов.</span><span class="sxs-lookup"><span data-stu-id="aa0bc-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

