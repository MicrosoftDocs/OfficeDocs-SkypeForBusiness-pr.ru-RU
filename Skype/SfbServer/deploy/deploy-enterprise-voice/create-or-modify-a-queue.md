---
title: Создание или изменение очереди в Скайп для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Создание или изменение очереди группы ответа, в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 6af6f9e4bea089f8b6194a06d1890e7d7e1699ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892918"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="3ddd2-103">Создание или изменение очереди в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3ddd2-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="3ddd2-104">Создание или изменение очереди группы ответа, в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3ddd2-105">Queues hold callers until an agent answers the call.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="3ddd2-106">Когда приложение группы ответа выполняет поиск доступного агента, будет выполняться поиск группы агентов в порядке их список.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="3ddd2-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="3ddd2-108">Чтобы создать или изменить очередь, используйте одну из следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="3ddd2-109">Чтобы использовать Скайп для панели управления Business Server для создания или изменения очереди</span><span class="sxs-lookup"><span data-stu-id="3ddd2-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="3ddd2-110">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3ddd2-111">Если вы являетесь одним из делегированных менеджеров группы ответа для управляемого рабочего процесса, вы можете создавать или изменять очереди группы ответа и назначать их рабочим процессам, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="3ddd2-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3ddd2-113">В левой панели навигации щелкните **Группы ответа**, затем щелкните **Очередь**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="3ddd2-114">На странице **Очередь** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="3ddd2-115">Чтобы создать очередь, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="3ddd2-116">В окне **Выбор службы** в поле поиска введите имя службы **ApplicationServer**, для которой необходимо добавить очередь, или часть имени.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="3ddd2-117">В полученном списке служб выберите требуемую службу и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="3ddd2-p103">Чтобы изменить существующую очередь, введите в поле поиска ее имя или его часть. В полученном списке очередей выберите требуемую очередь, нажмите кнопку **Изменить**, а затем кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3ddd2-120">В поле **Имя** введите понятное имя очереди.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="3ddd2-121">В поле **Описание** введите описание очереди.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="3ddd2-p104">В поле **Группы** укажите группы, которые вы хотите назначить очереди. Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="3ddd2-p105">Чтобы добавить группу в очередь, нажмите кнопку **Выбрать**. В поле поиска **Выбор групп** введите имя группы агентов, которую необходимо назначить очереди, или часть имени, выберите требуемую группу агентов и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="3ddd2-126">Чтобы удалить группу из очереди, в списке групп агентов выберите требуемую группу и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="3ddd2-127">Чтобы изменить порядок поиска агентов, в списке групп агентов выберите группу и нажмите стрелку вверх или стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="3ddd2-p106">При поиске доступного агента в очереди сервер использует порядковый номер группы, т. е. сначала сервер выбирает первую группу в списке, затем вторую и т. д.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="3ddd2-130">Чтобы задать максимальный период ожидания ответа агента (период удержания звонящего), установите флажок **Включить время ожидания очереди** и затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="3ddd2-131">a)</span><span class="sxs-lookup"><span data-stu-id="3ddd2-131">a.</span></span> <span data-ttu-id="3ddd2-132">В поле **Время ожидания (сек)** укажите максимальное время ожидания ответа агента на звонок.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="3ddd2-133">б)</span><span class="sxs-lookup"><span data-stu-id="3ddd2-133">b.</span></span> <span data-ttu-id="3ddd2-134">В **Действие вызова** выберите действие, выполняемое после завершения периода ожидания:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="3ddd2-135">Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="3ddd2-136">Переадресация звонков на голосовую почту, нажмите кнопку **переадресация на голосовую почту**и затем в поле **SIP-адрес** введите адрес голосовой почты в формате sip: \* \<username\>\*@ \*\<domainname\> \* (для Например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="3ddd2-137">Переадресация звонков на другой номер телефона, нажмите кнопку **переадресация на номер телефона**и затем в поле **SIP-адрес** введите номер телефона в формате sip: \* \<номер\>\*@ *\<domainname\>* (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="3ddd2-138">Чтобы переадресовать звонок на другого пользователя, нажмите кнопку **переадресация на SIP-адрес**, а затем в поле **SIP-адрес** введите URI для пользователя в формате sip: _ \<username\>_@ _\<domainname\>_.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="3ddd2-139">Чтобы переадресовать звонок в другую очередь, установите переключатель **Переадресовывать в другую очередь**, затем выберите требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="3ddd2-140">Чтобы указать максимальное число звонков в очереди, установите флажок **Разрешить переполнение очереди**, затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="3ddd2-141">a)</span><span class="sxs-lookup"><span data-stu-id="3ddd2-141">a.</span></span> <span data-ttu-id="3ddd2-142">В поле **Максимальное число звонков** выберите максимальное число звонков, находящихся в очереди.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="3ddd2-143">б)</span><span class="sxs-lookup"><span data-stu-id="3ddd2-143">b.</span></span> <span data-ttu-id="3ddd2-144">В поле **Переадресация звонка** выберите звонок, который будет переадресован при переполнении очереди (**Последний звонок** или **Первый звонок**).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="3ddd2-145">в.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-145">c.</span></span> <span data-ttu-id="3ddd2-146">В поле **Действие при звонке** выберите действие, выполняемое при превышении максимального числа звонков:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="3ddd2-147">Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="3ddd2-148">Переадресация звонков на голосовую почту, нажмите кнопку **переадресация на голосовую почту**и затем в поле **SIP-адрес** введите адрес голосовой почты в формате sip: \* \<username\>\*@ \*\<domainname\> \* (для Например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="3ddd2-149">Переадресация звонков на другой номер телефона, нажмите кнопку **переадресация на номер телефона**и затем в поле **SIP-адрес** введите номер телефона в формате sip: \* \<номер\>\*@ *\<domainname\>* (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="3ddd2-150">Чтобы переадресовать звонок на другого пользователя, нажмите кнопку **переадресация на SIP-адрес**, а затем в поле **SIP-адрес** введите URI для пользователя в формате sip: _ \<username\>_@ _\<domainname\>_.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="3ddd2-151">Чтобы переадресовать звонок в другую очередь, установите переключатель **Переадресовывать в другую очередь**, затем выберите требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="3ddd2-152">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="3ddd2-153">Чтобы использовать Скайп для консоли Business Server для создания или изменения очереди</span><span class="sxs-lookup"><span data-stu-id="3ddd2-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="3ddd2-154">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3ddd2-155">Если вы являетесь одним из делегированных диспетчеров группы ответа для управляемого рабочего процесса, вы можете создавать группы агентов и очереди и назначать группы агентов очередям.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="3ddd2-156">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3ddd2-p112">Создайте сообщение, которое будет воспроизводиться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="3ddd2-159">Например:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-159">For example:</span></span>
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="3ddd2-160">Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="3ddd2-161">Дополнительные сведения см [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="3ddd2-p114">Определите действие, которое должно выполняться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="3ddd2-164">Для получения дополнительных сведений о возможных действий и их синтаксисе см [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="3ddd2-165">Например:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-165">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="3ddd2-p115">Создайте сообщение, которое будет воспроизводиться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="3ddd2-168">Например:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-168">For example:</span></span>
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="3ddd2-169">Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="3ddd2-170">Дополнительные сведения см [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="3ddd2-p117">Определите действие, которое должно выполняться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="3ddd2-173">Для получения дополнительных сведений о возможных действий и их синтаксисе см [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3ddd2-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="3ddd2-174">Например:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-174">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="3ddd2-p118">Извлеките имя службы из службы группы ответа и назначьте его переменной. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p118">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="3ddd2-p119">Получите идентификатор группы агентов, которую нужно назначить очереди. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p119">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="3ddd2-179">Сведения о создании группы агентов в разделе [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3ddd2-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="3ddd2-p120">Создайте очередь. В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p120">Create the queue. At the command line, run:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="3ddd2-182">Например:</span><span class="sxs-lookup"><span data-stu-id="3ddd2-182">For example:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="3ddd2-p121">Убедитесь в том, что очередь создана. Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-p121">Confirm that the queue is created. Run:</span></span>
    
    ```
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="3ddd2-185">См. также</span><span class="sxs-lookup"><span data-stu-id="3ddd2-185">See also</span></span>

[<span data-ttu-id="3ddd2-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="3ddd2-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="3ddd2-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="3ddd2-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="3ddd2-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="3ddd2-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="3ddd2-189">Командлет New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="3ddd2-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="3ddd2-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="3ddd2-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="3ddd2-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="3ddd2-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="3ddd2-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="3ddd2-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
