---
title: Создание или изменение очереди в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Создание или изменение очереди группы ответов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: b355cde0d8a99938538488152276a6c8eb4c6d4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103585"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="ea9ff-103">Создание или изменение очереди в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ea9ff-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="ea9ff-104">Создание или изменение очереди группы ответов в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ea9ff-105">Вызывающие абоненты размещаются в очередях, пока агент не ответит на вызов.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="ea9ff-106">При поиске доступного агента приложение Группы реагирования выполняет поиск групп агентов в порядке их списка.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="ea9ff-107">Можно выбрать группы агентов, назначенные очереди, и указать поведение очереди, такое как ограничение количества вызовов, которое может размещаться в очереди, и время, которое вызов ожидает ответа агента.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="ea9ff-108">Чтобы создать или изменить очередь, используйте одну из следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="ea9ff-109">Использование панели управления Skype для бизнес-серверов для создания или изменения очереди</span><span class="sxs-lookup"><span data-stu-id="ea9ff-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="ea9ff-110">Войдите в группу RTCUniversalServerAdmins или в качестве члена одной из предопределяемой административной роли, поддерживаемой группой реагирования.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ea9ff-111">Если вы являетесь одним из делегированных менеджеров группы ответа для управляемого рабочего процесса, вы можете создавать или изменять очереди группы ответа и назначать их рабочим процессам, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="ea9ff-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ea9ff-113">В левой панели навигации щелкните **Response Groups** (Группы ответа) и затем щелкните **Queue** (Очередь).</span><span class="sxs-lookup"><span data-stu-id="ea9ff-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="ea9ff-114">На странице **Очередь** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="ea9ff-115">Чтобы создать очередь, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="ea9ff-116">в окне **Выбор службы** в поле поиска введите имя службы **ApplicationServer**, для которой необходимо добавить очередь, или часть имени.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="ea9ff-117">В полученном списке служб выберите требуемую службу и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ea9ff-p103">Чтобы изменить существующую очередь, введите в поле поиска ее имя или его часть. В полученном списке очередей выберите требуемую очередь, нажмите кнопку **Изменить**, а затем кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ea9ff-120">В поле **Имя** введите понятное имя очереди.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="ea9ff-121">В поле **Description** (Описание) введите описание очереди.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="ea9ff-p104">В поле **Группы** укажите группы, которые вы хотите назначить очереди. Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="ea9ff-p105">Чтобы добавить группу в очередь, нажмите кнопку **Выбрать**. В поле поиска **Выбор групп** введите имя группы агентов, которую необходимо назначить очереди, или часть имени, выберите требуемую группу агентов и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ea9ff-126">Чтобы удалить группу из очереди, в списке групп агентов выберите требуемую группу и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="ea9ff-127">Чтобы изменить порядок поиска агентов, в списке групп агентов выберите группу и нажмите стрелку вверх или стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ea9ff-p106">При поиске доступного агента в очереди сервер использует порядковый номер группы, т. е. сначала сервер выбирает первую группу в списке, затем вторую и т. д.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="ea9ff-130">Чтобы задать максимальный период ожидания ответа агента (период удержания звонящего), установите флажок **Enable queue time-out** (Включить время ожидания очереди) и затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="ea9ff-131">а)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-131">a.</span></span> <span data-ttu-id="ea9ff-132">В поле **Time-out period (seconds)** (Время ожидания (сек)) укажите максимальное время ожидания ответа агента на звонок.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="ea9ff-133">б)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-133">b.</span></span> <span data-ttu-id="ea9ff-134">В **Call Action** (Действие вызова) выберите действие, выполняемое после завершения периода ожидания:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="ea9ff-135">Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Disconnect** (Разъединить).</span><span class="sxs-lookup"><span data-stu-id="ea9ff-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="ea9ff-136">Чтобы переададовать вызов на голосовую почту, нажмите кнопку Вперед к голосовой **почте,** а затем в поле **адресов SIP** введите адрес голосовой почты в формате SIP: *\<username\>* @  *\<domainname\>* (например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ea9ff-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="ea9ff-137">Чтобы переадлить вызов на другой телефонный номер, нажмите кнопку Вперед к номеру **телефона,** а затем в поле **адресов SIP** введите номер телефона в формате SIP: *\<number\>* @  *\<domainname\>* (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ea9ff-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="ea9ff-138">Чтобы переадлить вызов другому пользователю, нажмите кнопку Вперед к SIP-адресу, а затем в поле **адресов SIP** введите URI для пользователя в формате **SIP:** _\<username\>_ @  _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="ea9ff-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="ea9ff-139">Чтобы переадресовать звонок в другую очередь, установите переключатель **Forward to another queue** (Переадресовать в другую очередь) и затем выберите требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="ea9ff-140">Чтобы указать максимальное число звонков в очереди, установите флажок **Enable queue overflow** (Разрешить переполнение очереди) и затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="ea9ff-141">а)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-141">a.</span></span> <span data-ttu-id="ea9ff-142">В поле **Maximum number of calls** (Максимальное число звонков) выберите максимальное число звонков, находящихся в очереди.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="ea9ff-143">б)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-143">b.</span></span> <span data-ttu-id="ea9ff-144">В поле **Forward the call** (Переадресация звонка) выберите звонок, который будет переадресован при переполнении очереди (**Newest Call** (Последний звонок) или **Oldest Call** (Первый звонок)).</span><span class="sxs-lookup"><span data-stu-id="ea9ff-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="ea9ff-145">в.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-145">c.</span></span> <span data-ttu-id="ea9ff-146">В поле **Действие при звонке** выберите действие, выполняемое при превышении максимального числа звонков:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="ea9ff-147">Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Disconnect** (Разъединить).</span><span class="sxs-lookup"><span data-stu-id="ea9ff-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="ea9ff-148">Чтобы переададовать вызов на голосовую почту, нажмите кнопку Вперед к голосовой **почте,** а затем в поле **адресов SIP** введите адрес голосовой почты в формате SIP: *\<username\>* @  *\<domainname\>* (например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ea9ff-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="ea9ff-149">Чтобы переадлить вызов на другой телефонный номер, нажмите кнопку Вперед к номеру **телефона,** а затем в поле **адресов SIP** введите номер телефона в формате SIP: *\<number\>* @  *\<domainname\>* (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ea9ff-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="ea9ff-150">Чтобы переадлить вызов другому пользователю, нажмите кнопку Вперед к SIP-адресу, а затем в поле **адресов SIP** введите URI для пользователя в формате **SIP:** _\<username\>_ @  _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="ea9ff-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="ea9ff-151">Чтобы переадресовать звонок в другую очередь, установите переключатель **Forward to another queue** (Переадресовать в другую очередь) и затем выберите требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="ea9ff-152">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="ea9ff-153">Использование оболочки управления Skype для бизнес-серверов для создания или изменения очереди</span><span class="sxs-lookup"><span data-stu-id="ea9ff-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="ea9ff-154">Войдите в группу RTCUniversalServerAdmins или в качестве члена одной из предопределяемой административной роли, поддерживаемой группой реагирования.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ea9ff-155">Если вы являетесь одним из делегированных диспетчеров группы ответа для управляемого рабочего процесса, вы можете создавать группы агентов и очереди и назначать группы агентов очередям.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="ea9ff-156">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="ea9ff-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ea9ff-p112">Создайте сообщение, которое будет воспроизводиться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="ea9ff-159">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="ea9ff-160">Чтобы использовать для сообщения звуковой файл, воспользуйтесь командлетом **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="ea9ff-161">Подробные сведения см. [в материале Import-CsRgsAudioFile.](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-161">For details, see [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="ea9ff-p114">Определите действие, которое должно выполняться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="ea9ff-164">Подробные сведения о возможных действиях и синтаксисах см. в [материале New-CsRgsCallAction.](/powershell/module/skype/new-csrgscallaction?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="ea9ff-165">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="ea9ff-p115">Создайте сообщение, которое будет воспроизводиться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="ea9ff-168">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="ea9ff-169">Чтобы использовать для сообщения звуковой файл, воспользуйтесь командлетом **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="ea9ff-170">Подробные сведения см. [в материале Import-CsRgsAudioFile.](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-170">For details, see [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="ea9ff-p117">Определите действие, которое должно выполняться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="ea9ff-173">Подробные сведения о возможных действиях и синтаксисах см. в [материале New-CsRgsCallAction.](/powershell/module/skype/new-csrgscallaction?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="ea9ff-174">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="ea9ff-175">Извлеките имя службы для службы группы ответа и назначьте его переменной.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="ea9ff-176">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-176">At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="ea9ff-177">Получите идентификатор группы агентов, которую нужно назначить очереди.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="ea9ff-178">В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-178">At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="ea9ff-179">Дополнительные сведения о создании группы агентов см. в [материале New-CsRgsAgentGroup.](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ea9ff-179">For details about creating the agent group, see [New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="ea9ff-p120">Создайте очередь. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p120">Create the queue. At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="ea9ff-182">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea9ff-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="ea9ff-p121">Убедитесь в том, что очередь создана. Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ea9ff-p121">Confirm that the queue is created. Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="ea9ff-185">См. также</span><span class="sxs-lookup"><span data-stu-id="ea9ff-185">See also</span></span>

[<span data-ttu-id="ea9ff-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ea9ff-186">New-CsRgsQueue</span></span>](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="ea9ff-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ea9ff-187">Set-CsRgsQueue</span></span>](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="ea9ff-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="ea9ff-188">New-CsRgsPrompt</span></span>](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="ea9ff-189">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="ea9ff-189">New-CsRgsCallAction</span></span>](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="ea9ff-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ea9ff-190">Get-CsRgsQueue</span></span>](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="ea9ff-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="ea9ff-191">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="ea9ff-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ea9ff-192">Remove-CsRgsQueue</span></span>](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)