---
title: 'Lync Server 2013: создание или изменение очереди'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 672752856d7f36e374646782cc36a031c81a9af0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="9fe43-102">Создание или изменение очереди в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe43-102">Create or modify a queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fe43-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9fe43-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9fe43-104">Чтобы создать или изменить очередь, используйте одну из следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="9fe43-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="9fe43-105">Создание или изменение очереди с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="9fe43-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="9fe43-106">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="9fe43-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe43-107">Если вы являетесь одним из делегированных менеджеров группы ответа для управляемого рабочего процесса, вы можете создавать или изменять очереди группы ответа и назначать их рабочим процессам, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="9fe43-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="9fe43-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9fe43-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9fe43-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9fe43-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9fe43-110">В левой панели навигации щелкните **Response Groups** (Группы ответа) и затем щелкните **Queue** (Очередь).</span><span class="sxs-lookup"><span data-stu-id="9fe43-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="9fe43-111">На странице **Очередь** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9fe43-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9fe43-112">Чтобы создать очередь, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9fe43-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="9fe43-113">в окне **Выбор службы** в поле поиска введите имя службы **ApplicationServer**, для которой необходимо добавить очередь, или часть имени.</span><span class="sxs-lookup"><span data-stu-id="9fe43-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="9fe43-114">В полученном списке служб выберите требуемую службу и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9fe43-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="9fe43-p103">Чтобы изменить существующую очередь, введите в поле поиска ее имя или его часть. В полученном списке очередей выберите требуемую очередь, нажмите кнопку **Изменить**, а затем кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9fe43-117">В поле **Имя** введите понятное имя очереди.</span><span class="sxs-lookup"><span data-stu-id="9fe43-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="9fe43-118">В поле **Description** (Описание) введите описание очереди.</span><span class="sxs-lookup"><span data-stu-id="9fe43-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="9fe43-p104">В поле **Группы** укажите группы, которые вы хотите назначить очереди. Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9fe43-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="9fe43-p105">Чтобы добавить группу в очередь, нажмите кнопку **Выбрать**. В поле поиска **Выбор групп** введите имя группы агентов, которую необходимо назначить очереди, или часть имени, выберите требуемую группу агентов и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="9fe43-123">Чтобы удалить группу из очереди, в списке групп агентов выберите требуемую группу и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="9fe43-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="9fe43-124">Чтобы изменить порядок поиска агентов, в списке групп агентов выберите группу и нажмите стрелку вверх или стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="9fe43-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9fe43-p106">При поиске доступного агента в очереди сервер использует порядковый номер группы, т. е. сначала сервер выбирает первую группу в списке, затем вторую и т. д.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="9fe43-127">Чтобы задать максимальный период ожидания ответа агента (период удержания звонящего), установите флажок **Enable queue time-out** (Включить время ожидания очереди) и затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9fe43-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="9fe43-128">В поле **Time-out period (seconds)** (Время ожидания (сек)) укажите максимальное время ожидания ответа агента на звонок.</span><span class="sxs-lookup"><span data-stu-id="9fe43-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="9fe43-129">В **Call Action** (Действие вызова) выберите действие, выполняемое после завершения периода ожидания:</span><span class="sxs-lookup"><span data-stu-id="9fe43-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="9fe43-130">Чтобы по истечении времени ожидания звонок прерывался, выберите пункт **Разъединять**.</span><span class="sxs-lookup"><span data-stu-id="9fe43-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="9fe43-131">Чтобы перенаправить звонок на голосовую почту, щелкните **Переслать на голосовую почту**, а затем в поле **SIP-адрес** введите адрес голосовой почты в формате SIP\<:\>@\<имя_пользователя\> имя_домена (например, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9fe43-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="9fe43-132">Чтобы переадресовать звонок на другой номер телефона, щелкните **Переслать на номер телефона**, а затем в поле **SIP-адрес** введите номер телефона в формате SIP:\<Number\>@\<имя_домена\> (например, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9fe43-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="9fe43-133">Чтобы перенаправить звонок другому пользователю, нажмите кнопку **переадресация на SIP Address (SIP Address**), а затем в поле **SIP Address (адрес SIP** ) введите URI пользователя\<в\>@\<формате\>SIP: имяпользователя имя_домена.</span><span class="sxs-lookup"><span data-stu-id="9fe43-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="9fe43-134">Чтобы переадресовать звонок в другую очередь, установите переключатель **Forward to another queue** (Переадресовать в другую очередь) и затем выберите требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="9fe43-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="9fe43-135">Чтобы указать максимальное число звонков в очереди, установите флажок **Enable queue overflow** (Разрешить переполнение очереди) и затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9fe43-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="9fe43-136">В поле **Maximum number of calls** (Максимальное число звонков) выберите максимальное число звонков, находящихся в очереди.</span><span class="sxs-lookup"><span data-stu-id="9fe43-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="9fe43-137">В поле **Forward the call** (Переадресация звонка) выберите звонок, который будет переадресован при переполнении очереди (**Newest Call** (Последний звонок) или **Oldest Call** (Первый звонок)).</span><span class="sxs-lookup"><span data-stu-id="9fe43-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="9fe43-138">В поле **Действие при звонке** выберите действие, выполняемое при превышении максимального числа звонков:</span><span class="sxs-lookup"><span data-stu-id="9fe43-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="9fe43-139">Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Disconnect** (Разъединить).</span><span class="sxs-lookup"><span data-stu-id="9fe43-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="9fe43-140">Чтобы перенаправить звонок на голосовую почту, щелкните **Переслать на голосовую почту**, а затем в поле **SIP-адрес** введите адрес голосовой почты в формате SIP\<:\>@\<имя_пользователя\> имя_домена (например, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9fe43-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="9fe43-141">Чтобы переадресовать звонок на другой номер телефона, щелкните **Переслать на номер телефона**, а затем в поле **SIP-адрес** введите номер телефона в формате SIP:\<Number\>@\<имя_домена\> (например, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9fe43-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="9fe43-142">Чтобы перенаправить звонок другому пользователю, нажмите кнопку **переадресация на SIP Address (SIP Address**), а затем в поле **SIP Address (адрес SIP** ) введите URI пользователя\<в\>@\<формате\>SIP: имяпользователя имя_домена.</span><span class="sxs-lookup"><span data-stu-id="9fe43-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="9fe43-143">Чтобы переадресовать звонок в другую очередь, установите переключатель **Forward to another queue** (Переадресовать в другую очередь) и затем выберите требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="9fe43-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="9fe43-144">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9fe43-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="9fe43-145">Использование Windows PowerShell для создания или изменения очереди</span><span class="sxs-lookup"><span data-stu-id="9fe43-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="9fe43-146">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="9fe43-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe43-147">Если вы являетесь одним из делегированных диспетчеров группы ответа для управляемого рабочего процесса, вы можете создавать группы агентов и очереди и назначать группы агентов очередям.</span><span class="sxs-lookup"><span data-stu-id="9fe43-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="9fe43-148">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9fe43-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9fe43-p107">Создайте сообщение, которое будет воспроизводиться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="9fe43-151">Например:</span><span class="sxs-lookup"><span data-stu-id="9fe43-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe43-152">Чтобы использовать для сообщения звуковой файл, воспользуйтесь командлетом <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9fe43-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="9fe43-153">Дополнительные сведения см. в статье <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import – CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="9fe43-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="9fe43-p109">Определите действие, которое должно выполняться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe43-156">Дополнительные сведения о возможных действиях и их синтаксисе приведены в статье <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New – CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="9fe43-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="9fe43-157">Например:</span><span class="sxs-lookup"><span data-stu-id="9fe43-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="9fe43-p110">Создайте сообщение, которое будет воспроизводиться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="9fe43-160">Например:</span><span class="sxs-lookup"><span data-stu-id="9fe43-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe43-161">Чтобы использовать для сообщения звуковой файл, воспользуйтесь командлетом <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9fe43-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="9fe43-162">Дополнительные сведения см. в статье <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import – CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="9fe43-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="9fe43-p112">Определите действие, которое должно выполняться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe43-165">Дополнительные сведения о возможных действиях и их синтаксисе приведены в статье <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New – CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="9fe43-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="9fe43-166">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fe43-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="9fe43-167">Извлеките имя службы для службы группы ответа и назначьте его переменной.</span><span class="sxs-lookup"><span data-stu-id="9fe43-167">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="9fe43-168">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9fe43-168">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="9fe43-169">Получите идентификатор группы агентов, которую нужно назначить очереди.</span><span class="sxs-lookup"><span data-stu-id="9fe43-169">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="9fe43-170">В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9fe43-170">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe43-171">Более подробную информацию о создании группы агентов можно узнать в статье <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New/CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="9fe43-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="9fe43-p115">Создайте очередь. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="9fe43-174">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fe43-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="9fe43-p116">Убедитесь в том, что очередь создана. Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9fe43-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9fe43-177">См. также</span><span class="sxs-lookup"><span data-stu-id="9fe43-177">See Also</span></span>


[<span data-ttu-id="9fe43-178">New — CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="9fe43-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="9fe43-179">Set — CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="9fe43-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="9fe43-180">New — CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="9fe43-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="9fe43-181">New — CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="9fe43-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="9fe43-182">Get — CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="9fe43-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="9fe43-183">Import — CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="9fe43-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="9fe43-184">Remove — CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="9fe43-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

