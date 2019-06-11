---
title: 'Lync Server 2013: Импорт пакетов управления Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="328ba-102">Импорт пакетов управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="328ba-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="328ba-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="328ba-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="328ba-104">Вы можете расширять возможности System Center Operations Manager, устанавливая пакеты управления (программное обеспечение, которое определяет, какие элементы отслеживается System Center Operations Manager) и как эти элементы должны отслеживаться и как будут запускаться оповещения. отчета.</span><span class="sxs-lookup"><span data-stu-id="328ba-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="328ba-105">Lync Server 2013 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="328ba-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="328ba-106">Пакет управления компонентом и пользовательским интерфейсом (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) отслеживает проблемы Lync Server, записанные счетчиками производительности, которые регистрируются в журналах событий или записываются в записи сведений о звонке (CDR) или в качестве его качества (QoE). баз данных.</span><span class="sxs-lookup"><span data-stu-id="328ba-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="328ba-107">Для критических проблем можно настроить System Center Operations Manager для немедленного уведомления администраторов с помощью электронной почты, обмена мгновенными сообщениями или службы коротких сообщений (SMS).</span><span class="sxs-lookup"><span data-stu-id="328ba-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="328ba-108">SMS — это технология, используемая для отправки текстовых сообщений с одного мобильного устройства на другое.</span><span class="sxs-lookup"><span data-stu-id="328ba-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="328ba-109">Дополнительные сведения о настройке уведомлений Operations Manager можно найти в уведомлении о настройке в библиотеке <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>TechNet по адресу.</span><span class="sxs-lookup"><span data-stu-id="328ba-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="328ba-110">Активный пакет управления мониторингом (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) позволяет заблаговременно протестировать ключевые компоненты сервера Lync, такие как вход в систему, Обмен мгновенными сообщениями и звонки на телефоны, находящиеся на общедоступном коммутаторе. телефонная сеть (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="328ba-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="328ba-111">Эти тесты выполняются с помощью виртуальных командлетов транзакций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="328ba-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="328ba-112">Например, с помощью командлета **Test-Ксим** можно смоделировать беседу между пользователями (мгновенными сообщениями) между парой тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="328ba-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="328ba-113">Если это имитируемый разговор не порождает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="328ba-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="328ba-114">Вам нужно импортировать пакеты управления.</span><span class="sxs-lookup"><span data-stu-id="328ba-114">You need to import the management packs.</span></span> <span data-ttu-id="328ba-115">Если вы не импортируете пакеты управления, нельзя использовать Operations Manager для мониторинга событий сервера Lync Server и выполнения виртуальных транзакций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="328ba-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="328ba-116">Пакет управления компонентом и пользовательским интерфейсом используется только для мониторинга сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="328ba-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="328ba-117">Если у вас есть сценарий сосуществования, на котором установлены оба сервера Lync Server 2013 и Lync Server 2010, вы должны продолжать использовать пакеты управления Lync Server 2010 для компьютеров Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="328ba-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="328ba-118">Пакеты управления для Lync Server 2010 включают пакет управления для мониторинга Lync Server 2010 и пакет управления "Мониторинг группового чата" для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="328ba-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="328ba-119">Для импорта пакетов управления можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="328ba-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="328ba-120">**System Center Operations Manager**   с помощью этого метода вы можете добавить мониторинг для Lync Server с помощью Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="328ba-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="328ba-121">**Оболочка Operations Manager**   вы можете импортировать их напрямую или устранить проблемы, возникающие при импорте пакетов управления с помощью консоли System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="328ba-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="328ba-122">Импорт пакетов управления с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="328ba-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="328ba-123">Скачайте файлы Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="328ba-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="328ba-124">В System Center Operations Manager щелкните элемент **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="328ba-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="328ba-125">В области " **Администрирование** " щелкните правой кнопкой мыши **пакеты управления**и выберите пункт **Импорт пакетов управления**.</span><span class="sxs-lookup"><span data-stu-id="328ba-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="328ba-126">В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Добавить**, затем щелкните **Добавить с диска**.</span><span class="sxs-lookup"><span data-stu-id="328ba-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="328ba-127">В диалоговом окне **Подключение к каталогу в сети** нажмите кнопку **Отмена** , чтобы не допустить подключения Operations Manager к сети, чтобы узнать, существуют ли зависимости для пакетов управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="328ba-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="328ba-128">Если вы используете System Center Operations Manager 2012, нажмите кнопку **нет**.</span><span class="sxs-lookup"><span data-stu-id="328ba-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="328ba-129">В диалоговом окне **Выбор пакетов управления для импорта** найдите и выберите файлы **Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP** и **Microsoft.ls.2013.Monitoring.ComponentAndUser.MP** , а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="328ba-129">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**.</span></span> <span data-ttu-id="328ba-130">Чтобы выбрать несколько файлов в диалоговом окне, щелкните первый файл, удерживая нажатой клавишу CTRL, а затем щелкните второй файл.</span><span class="sxs-lookup"><span data-stu-id="328ba-130">To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="328ba-131">В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="328ba-131">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="328ba-132">Сообщение об ошибке и сбой установки, как правило, указывают на то, что папка, в которой находятся файлы пакетов управления, защищена функцией контроля учетных записей Windows.</span><span class="sxs-lookup"><span data-stu-id="328ba-132">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="328ba-133">Если это случится, скопируйте файлы в другую папку, а затем перезапустите процесс импорта и установки.</span><span class="sxs-lookup"><span data-stu-id="328ba-133">If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="328ba-134">В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="328ba-134">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="328ba-135">Обратите внимание, что для завершения процесса импорта и установки может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="328ba-135">Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="328ba-136">Импорт пакетов управления с помощью оболочки Operations Manager</span><span class="sxs-lookup"><span data-stu-id="328ba-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="328ba-137">Обычно проще импортировать пакеты управления с помощью Operations Manager. Однако если возникает ошибка и импорт завершается сбоем, консоль не всегда предоставляет адекватные отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="328ba-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="328ba-138">По сравнению с оболочкой Operations Manager выводятся подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="328ba-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="328ba-139">Если вы используете Operations Manager и при импорте пакета управления выполняются проблемы, импортируйте пакет с помощью оболочки Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="328ba-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="328ba-140">В командной консоли Operations Manager содержатся дополнительные сведения, которые могут помочь определить причину сбоя импорта.</span><span class="sxs-lookup"><span data-stu-id="328ba-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="328ba-141">Если вы используете System Center Operations Manager 2007 R2, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="328ba-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="328ba-142">Нажмите кнопку **Пуск**, выберите **все программы**, а затем **System Center Operations Manager 2007 R2**и выберите **Shell Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="328ba-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="328ba-143">В командной строке Operations Manager введите указанную ниже команду, используя фактический путь к копии файла Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="328ba-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="328ba-144">После импорта первого пакета управления повторите процесс, указав путь к копии файла Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="328ba-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="328ba-145">Закройте интерпретатор Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="328ba-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="328ba-146">Если вы используете System Center Operations Manager 2012, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="328ba-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="328ba-147">Нажмите кнопку **Пуск** и щелкните **Все программы**, **Microsoft System Center 2012**, **Operations Manager**, затем **Оболочка Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="328ba-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="328ba-148">В командной строке Operations Manager введите указанную ниже команду, используя фактический путь к копии файла Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="328ba-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="328ba-149">После импорта первого пакета управления повторите процесс, указав путь к копии файла Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="328ba-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

