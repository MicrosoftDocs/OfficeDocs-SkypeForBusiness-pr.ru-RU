---
title: 'Lync Server 2013: Импорт пакетов управления Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2c6dd42056fe665c0d4ec53d28103745ace2c84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="5e6ca-102">Импорт пакетов управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e6ca-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e6ca-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5e6ca-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5e6ca-104">Вы можете расширить возможности System Center Operations Manager, устанавливая пакеты управления — программное обеспечение, которое определяет, какие элементы будут отслеживаться системой System Center Operations Manager и как эти элементы должны отслеживаться и как запускаются оповещения и регистрируют.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="5e6ca-105">Lync Server 2013 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="5e6ca-106">Пакет управления компонентом и пользовательским пакетом (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) отслеживает проблемы Lync Server, записанные в журналах событий, зарегистрированные счетчиками производительности или записанные в записи сведений о вызовах (CDR) или качества взаимодействия (QoE). базы.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="5e6ca-107">Для критических проблем можно настроить System Center Operations Manager для немедленного уведомления администраторов с помощью электронной почты, обмена мгновенными сообщениями или обмена сообщениями в службе коротких сообщений (SMS).</span><span class="sxs-lookup"><span data-stu-id="5e6ca-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="5e6ca-108">SMS — это технология передачи текстовых сообщений с одного мобильного устройства на другое.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5e6ca-109">Подробнее о настройке уведомлений Operations Manager можно узнать в статье Настройка уведомлений в библиотеке TechNet по <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>адресу.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="5e6ca-110">Пакет управления Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) служит для профилактического тестирования ключевых компонентов Lync Server, таких как вход в систему, Обмен мгновенными сообщениями или совершение звонков на телефон, расположенный на общедоступном коммутаторе телефонная сеть (PSTN).</span><span class="sxs-lookup"><span data-stu-id="5e6ca-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="5e6ca-111">Эти тесты выполняются с помощью командлетов искусственной транзакции Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="5e6ca-112">Например, с помощью командлета **Test-CsIM** можно симулировать обмен мгновенными сообщениями между парой тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="5e6ca-113">При возникновении ошибки в этой симулированной беседе создается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="5e6ca-114">Пакеты управления нужно импортировать.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-114">You need to import the management packs.</span></span> <span data-ttu-id="5e6ca-115">Если вы не импортируете пакеты управления, вы не можете использовать Operations Manager для мониторинга событий Lync Server или для запуска искусственных транзакций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="5e6ca-116">Пакет управления компонентом и пользователями используется только для мониторинга Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="5e6ca-117">Если используется сценарий сосуществования, на котором установлены как Lync Server 2013, так и Lync Server 2010, следует по прежнему использовать пакеты управления Lync Server 2010 для компьютеров Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e6ca-118">Пакеты управления для Lync Server 2010 включают пакет управления мониторинга Lync Server 2010 и пакет управления мониторинга группового чата для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="5e6ca-119">Для импорта пакетов управления можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="5e6ca-120">**System Center Operations Manager**   с помощью этого метода можно добавить мониторинг для Lync Server с помощью Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="5e6ca-121">**Командная**   консоль Operations Manager можно использовать командную консоль Operations Manager для непосредственного импорта или устранения неполадок, возникающих при импорте пакетов управления с помощью консоли System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="5e6ca-122">Импорт пакетов управления с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="5e6ca-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="5e6ca-123">Загрузите файлы Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="5e6ca-124">В System Center Operations Manager щелкните **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="5e6ca-125">На панели **Администрирование** щелкните правой кнопкой **Пакеты управления** и выберите команду **Импорт пакетов управления**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="5e6ca-126">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Добавить** и щелкните элемент **Add from disk** (Добавить с диска).</span><span class="sxs-lookup"><span data-stu-id="5e6ca-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="5e6ca-127">В диалоговом окне **Подключение к каталогу в Интернете** нажмите кнопку **Отмена** , чтобы запретить Operations Manager переходить в оперативный режим, чтобы узнать, существуют ли зависимости для пакетов управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="5e6ca-128">Если вы используете System Center Operations Manager 2012, нажмите кнопку **нет**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="5e6ca-p107">В диалоговом окне **Выбор пакетов управления для импорта** найдите и выберите файлы **Microsoft.LS.2013.Monitoring.mp** и **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, а затем нажмите кнопку **Открыть**. Чтобы выбрать в этом диалоговом окне несколько файлов, щелкните первый файл, а затем, удерживая клавишу CTRL, щелкните второй файл.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-p107">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**. To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="5e6ca-p108">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Установить**. Если отображается сообщение об ошибке и установка завершается со сбоем, обычно это указывает на то, что файлы пакетов управления находятся в папке, защищенной функцией контроля учетных записей Windows. В этом случае скопируйте файлы в другую папку и перезапустите процесс импорта и установки.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="5e6ca-p109">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Закрыть**. Обратите внимание на то, что для выполнения процесса импорта и установки может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-p109">In the **Select Management Packs** dialog box, click **Close**. Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="5e6ca-136">Импорт пакетов управления с помощью командной консоли Operations Manager</span><span class="sxs-lookup"><span data-stu-id="5e6ca-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="5e6ca-137">В общем случае проще импортировать пакеты управления с помощью Operations Manager. Однако при возникновении ошибки и неудачном импорте консоль не всегда предоставляет соответствующие отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="5e6ca-138">По сравнению с оболочкой Operations Manager предоставляются подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="5e6ca-139">Если вы используете Operations Manager и при импорте пакета управления возникли проблемы, импортируйте пакет с помощью командной консоли Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="5e6ca-140">В командной консоли Operations Manager содержатся дополнительные сведения, которые могут помочь определить причину сбоя импорта.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="5e6ca-141">Если вы используете System Center Operations Manager 2007 R2, выполните следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="5e6ca-142">В меню **Пуск**выберите пункт **все программы**, затем **System Center Operations Manager 2007 R2**и выберите команду **Shell Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="5e6ca-143">В командной консоли Operations Manager введите в командной строке следующую команду, используя фактический путь к копии файла Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="5e6ca-144">После импорта первого пакета управления повторите процесс, ссылаясь на путь к копии файла Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="5e6ca-145">Закройте командную консоль Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="5e6ca-146">Если вы используете System Center Operations Manager 2012, выполните эту процедуру следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="5e6ca-147">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft System Center 2012**, **Operations Manager**, а затем — **Shell Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="5e6ca-148">В командной консоли Operations Manager введите в командной строке следующую команду, используя фактический путь к копии файла Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="5e6ca-149">После импорта первого пакета управления повторите процесс, ссылаясь на путь к копии файла Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="5e6ca-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

