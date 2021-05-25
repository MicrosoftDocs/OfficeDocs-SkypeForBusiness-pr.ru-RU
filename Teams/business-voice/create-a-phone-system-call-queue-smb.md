---
title: Создание очереди вызовов в Microsoft Teams учебнике для малого бизнеса
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Узнайте, как настроить очереди вызовов для малого бизнеса в Голосовая связь Microsoft 365 бизнес.
ms.openlocfilehash: 755c4914271c96cdd668bb2933872ebf1fa21b94
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629058"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="d9b1b-103">Создание очереди вызовов — учебник по малому бизнесу</span><span class="sxs-lookup"><span data-stu-id="d9b1b-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="d9b1b-104">Очереди вызовов предоставляют способ маршрутизации вызывающих людей в организации, которые могут помочь с определенной проблемой или вопросом.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="d9b1b-105">Звонки распределяются по одному для людей, которые находятся в очереди (которые называются *агентами).*</span><span class="sxs-lookup"><span data-stu-id="d9b1b-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="d9b1b-106">Очереди вызовов предоставляют:</span><span class="sxs-lookup"><span data-stu-id="d9b1b-106">Call queues provide:</span></span>

- <span data-ttu-id="d9b1b-107">Приветствие.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-107">A greeting message.</span></span>

- <span data-ttu-id="d9b1b-108">Музыка, пока люди находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="d9b1b-109">Маршрутия вызовов — в порядке first *In, First Out* (FIFO) — агентам.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="d9b1b-110">Параметры обработки для переполнения и времени ожидания в очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="video-demonstration"></a><span data-ttu-id="d9b1b-111">Демонстрация видео</span><span class="sxs-lookup"><span data-stu-id="d9b1b-111">Video demonstration</span></span>

<span data-ttu-id="d9b1b-112">В этом видео показано, как создать очередь вызовов в Teams.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-112">This video demonstrates how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="d9b1b-113">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="d9b1b-113">Before you begin</span></span>

<span data-ttu-id="d9b1b-114">Получите [лицензии телефонная система виртуальных](../teams-add-on-licensing/virtual-user.md) пользователей, если у вас их еще нет.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-114">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="d9b1b-115">Получите по одному для каждой очереди вызовов и автосбережающего, которые вы планируете настроить.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-115">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="d9b1b-116">Эти лицензии бесплатны, поэтому мы рекомендуем получить дополнительные лицензии на случай, если вы решите внести изменения в настройку в будущем.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-116">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="d9b1b-117">Так как агенты в очереди звонков могут звонить, чтобы вернуть звонок клиента, вы можете установить для агентов вызова основной номер телефона или номер соответствующего автосбережающего.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-117">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="d9b1b-118">Дополнительные [сведения см.](../caller-id-policies.md) в Microsoft Teams управление политиками ИД звоня.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-118">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="d9b1b-119">Чтобы настроить очередь вызовов, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-119">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="d9b1b-120">Шаг <br> 1. Создание команды</span><span class="sxs-lookup"><span data-stu-id="d9b1b-120">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="d9b1b-121">При создании очереди вызовов вы можете добавить отдельных пользователей в очередь или использовать существующую группу безопасности, группу Microsoft 365 или Microsoft Teams группу.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-121">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="d9b1b-122">Мы рекомендуем [использовать канал команды](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span><span class="sxs-lookup"><span data-stu-id="d9b1b-122">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="d9b1b-123">Это позволяет участникам очереди общаться друг с другом, обмениваться идеями, а также создавать документы и другие ресурсы, чтобы помочь клиентам.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-123">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="d9b1b-124">Группа также предоставляет голосовой почтовый ящик, в который звонящие могут оставлять сообщения в неподходящих часах или в случае максимальной емкости очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-124">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="d9b1b-125">Создание команды</span><span class="sxs-lookup"><span data-stu-id="d9b1b-125">To create a team</span></span>

1. <span data-ttu-id="d9b1b-126">Сначала щелкните **Teams** в левой части приложения,  а затем щелкните Присоединиться или создать команду в нижней части списка команд.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-126">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="d9b1b-127">Затем нажмите **кнопку Создать команду** (первая карточка, левый верхний угол).</span><span class="sxs-lookup"><span data-stu-id="d9b1b-127">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="d9b1b-128">Выберите **Создать команду с нуля**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-128">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="d9b1b-129">Затем выберите, хотите ли вы сделать команду открытой или закрытой.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-129">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="d9b1b-130">Мы рекомендуем **использовать private** для очереди присоединения к звонку, чтобы избежать непреднамеренного вхождения людей в очередь путем присоединения к команде.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-130">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="d9b1b-131">Привязайте имя своей команды и при желании добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-131">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="d9b1b-132">Когда все будет готово, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-132">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="d9b1b-133">Введите имена нужных людей в очереди вызовов и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-133">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="d9b1b-134">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-134">Click **Close**.</span></span> <span data-ttu-id="d9b1b-135">Люди, которых вы добавляете в команду, получат по электронной почте сообщение о том, что они теперь являются членами вашей команды, и группа будет от них отовсю демонстрироваться в списке команд.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-135">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="d9b1b-136">Затем мы добавим канал для использования с очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-136">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="d9b1b-137">Добавление канала</span><span class="sxs-lookup"><span data-stu-id="d9b1b-137">To add a channel</span></span>

1. <span data-ttu-id="d9b1b-138">В Teams найдите только что созданную команду, щелкните Дополнительные **параметры** (...), а затем — **Добавить канал**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-138">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="d9b1b-139">Введите название и описание канала, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-139">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d9b1b-140">Шаг 2. Учетные записи ресурсов ></span><span class="sxs-lookup"><span data-stu-id="d9b1b-140">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="d9b1b-141">Шаг <br> 2. Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="d9b1b-141">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="d9b1b-142">Для каждой создаемой очереди вызовов требуется учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-142">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="d9b1b-143">Эта учетная запись аналогична учетной записи пользователя, за исключением того, что она связана с автосчетом или очередью вызовов, а не с пользователем.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-143">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="d9b1b-144">На этом этапе мы создадим учетную запись, назначим Microsoft 365 телефонная система *лицензию виртуальный* пользователь, а затем создадим очередь вызовов с ее помощью.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-144">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="d9b1b-145">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="d9b1b-145">Create a resource account</span></span>

<span data-ttu-id="d9b1b-146">Вы можете создать учетную запись ресурса в Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-146">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="d9b1b-147">В центре Teams разметка **параметров** для всей организации и нажмите кнопку **Учетные записи ресурсов.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-147">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="d9b1b-148">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-148">Click **Add**.</span></span>

3. <span data-ttu-id="d9b1b-149">В области Добавление **учетной записи** ресурса введите отображаемого имени **,** **имя пользователя** и выберите очередь зовов для типа **учетной записи Ресурса.** </span><span class="sxs-lookup"><span data-stu-id="d9b1b-149">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="d9b1b-150">Агенты увидят отображаемую фамилию, когда получат входящий звонок из очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-150">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![Снимок экрана: добавление пользовательского интерфейса учетной записи ресурса](../media/resource-account-add-cq.png)

4. <span data-ttu-id="d9b1b-152">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-152">Click **Save**.</span></span>

   <span data-ttu-id="d9b1b-153">Новая учетная запись появится в списке учетных записей.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-153">The new account will appear in the list of accounts.</span></span>

   ![Снимок экрана: список учетных записей ресурсов](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="d9b1b-155">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="d9b1b-155">Assign a license</span></span>

<span data-ttu-id="d9b1b-156">Учетной записи *ресурса Microsoft 365 телефонная система лицензию виртуальный* пользователь.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-156">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="d9b1b-157">В Microsoft 365 администрирования в списке **Активные** пользователи выберите учетную запись ресурса, для которой вы хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-157">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="d9b1b-158">На **вкладке Лицензии и приложения** в области **Лицензии** выберите Microsoft 365 телефонная система **— виртуальный пользователь**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="d9b1b-159">Нажмите **кнопку Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-159">Click **Save changes**.</span></span>

    ![Снимок экрана: пользовательский интерфейс назначения лицензий в центре Microsoft 365 администрирования](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="d9b1b-161">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="d9b1b-161">Create a call queue</span></span>

<span data-ttu-id="d9b1b-162">Далее мы начнем создавать новую очередь вызовов и назначать учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-162">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="d9b1b-163">В Центре администрирования Teams **Разойдите в центр администрирования Голосовая** почта , выберите очереди зовов **и** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-163">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="d9b1b-164">Введите имя очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-164">Type a name for the call queue.</span></span>

2. <span data-ttu-id="d9b1b-165">Нажмите **кнопку Добавить учетные** записи , найдите учетную запись ресурса, которую вы хотите использовать с этой очередью вызовов, нажмите кнопку **Добавить,** а затем нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-165">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="d9b1b-166">Выберите язык.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-166">Choose a language.</span></span> <span data-ttu-id="d9b1b-167">Этот язык будет использоваться для системных голосовых подсказок и транскрибации голосовой почты (если вы их включаете).</span><span class="sxs-lookup"><span data-stu-id="d9b1b-167">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Снимок экрана: учетная запись ресурса и языковые параметры](../media/call-queue-name-language.png)

4. <span data-ttu-id="d9b1b-169">Укажите, хотите ли вы, чтобы вызыватели могли разозвать приветствие при их поступления в очередь.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-169">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="d9b1b-170">Необходимо отправить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-170">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="d9b1b-171">Teams предоставляет вызывателям музыку по умолчанию, когда они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-171">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="d9b1b-172">Если вы хотите воспроизведения определенного  звукового файла, выберите Вариант воспроизведения звукового файла и загрузите файл MP3, WAV или WMA.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-172">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d9b1b-173">Размер загруженной записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-173">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="d9b1b-174">По умолчанию музыка, которая поставляется Teams очередях вызовов, не предоставляется вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-174">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="d9b1b-175">Шаг 3. Вызовы агентов ></span><span class="sxs-lookup"><span data-stu-id="d9b1b-175">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="d9b1b-176">Шаг <br> 3. Агенты вызовов</span><span class="sxs-lookup"><span data-stu-id="d9b1b-176">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="d9b1b-177">Чтобы добавить агентов в очередь вызовов, мы добавим их в ранее созданную команду и канал.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-177">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="d9b1b-178">Выберите команду **Выберите команду** и нажмите **кнопку Добавить канал**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-178">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="d9b1b-179">Введите имя созданной команды, выберите ее и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-179">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="d9b1b-180">Выберите канал, созданный для очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-180">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="d9b1b-181">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-181">Click **Apply**.</span></span>

    ![Снимок экрана: параметры пользователей и групп для очередей вызовов](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="d9b1b-183">При добавлении новых пользователей в команду для первого звонка может быть до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-183">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d9b1b-184">Шаг 4. Учетные записи ресурсов ></span><span class="sxs-lookup"><span data-stu-id="d9b1b-184">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="d9b1b-185">Шаг <br> 4. Маршрутия вызовов</span><span class="sxs-lookup"><span data-stu-id="d9b1b-185">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="d9b1b-186">Выберите нужный способ маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-186">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="d9b1b-187">Установите **для режима конференции** **авто.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-187">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="d9b1b-188">Выберите **нужный** способ маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-188">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="d9b1b-189">Это определяет порядок, в котором агенты будут принимать звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-189">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="d9b1b-190">Рекомендуем использовать **порядковую маршрутику** или **округлую маршрутику.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-190">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="d9b1b-191">Выберите один из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d9b1b-191">Choose from these options:</span></span>

    - <span data-ttu-id="d9b1b-192">**Маршруты помощника одновременно** звонят всем агентам в очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-192">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="d9b1b-193">Звонок получит первый агент звонка.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-193">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="d9b1b-194">**Порядковая маршрутия** звонит всем агентам по одному.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-194">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="d9b1b-195">Если агент отклоает звонок или не звонит, звонок звонит следующему агенту и пробует всех агентов до тех пор, пока он не будет отклонен или не будет разозваться.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-195">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="d9b1b-196">**Round balances** the routing of incoming calls so each call agent gets the same number of calls from the queue.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-196">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="d9b1b-197">Это может быть нежелательно в среде входящие продаж, чтобы обеспечить равные возможности для всех агентов звонка.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-197">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="d9b1b-198">**Наиболее длинные** неавтоматные маршруты каждый звонок передается агенту, который простаивает в течение долгого времени.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-198">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="d9b1b-199">(Агенты, состояние присутствия которых было нет на сети более 10 минут, не включаются.)</span><span class="sxs-lookup"><span data-stu-id="d9b1b-199">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Снимок экрана: режим конференции и параметры метода маршрутации](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="d9b1b-201">**Включите маршрутику на основе присутствия.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-201">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="d9b1b-202">В этом случае звонки будут маршрутизовы на агентов, состояние **присутствия** которых доступно.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-202">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="d9b1b-203">Выберите, хотите ли вы разрешить агентам отказаться от звонков.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-203">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="d9b1b-204">Укажите **время оповещения агента,** чтобы указать, как долго телефон агента будет звонить, прежде чем очередь перенаправит звонок следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-204">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Снимок экрана: параметры времени маршрутки, отказа и оповещений](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="d9b1b-206">Шаг 5. Переполнение вызовов ></span><span class="sxs-lookup"><span data-stu-id="d9b1b-206">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="d9b1b-207">Шаг <br> 5. Переполнение звонка</span><span class="sxs-lookup"><span data-stu-id="d9b1b-207">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="d9b1b-208">Выберите, как вы хотите обрабатывать звонки, превышают максимальное значение в очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-208">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="d9b1b-209">Установите **максимальное число звонков в очереди.**</span><span class="sxs-lookup"><span data-stu-id="d9b1b-209">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="d9b1b-210">Выберите, что вы хотите сделать, когда достигается максимальное количество звонков.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-210">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="d9b1b-211">Вы можете отключить звонок или перенаправить его.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-211">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="d9b1b-212">Мы рекомендуем перенаправить звонок на одно из следующих мест:</span><span class="sxs-lookup"><span data-stu-id="d9b1b-212">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="d9b1b-213">**Человек в организации —** человек в вашей организации, который может принимать голосовые звонки</span><span class="sxs-lookup"><span data-stu-id="d9b1b-213">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="d9b1b-214">**Приложение голосовой** почты — автозаводка или другая очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-214">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="d9b1b-215">(Выберите учетную запись ресурса, связанную с автозаправлением или очередью вызовов при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="d9b1b-215">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="d9b1b-216">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-216">**External phone number** - any phone number.</span></span> <span data-ttu-id="d9b1b-217">Используйте такой формат: +[код страны][код города][номер телефона]</span><span class="sxs-lookup"><span data-stu-id="d9b1b-217">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="d9b1b-218">**Голосовая** почта: вы можете использовать почтовый ящик созданной вами команды.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-218">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Снимок экрана: параметры переполнения звонка](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="d9b1b-220">Шаг 6. Время ></span><span class="sxs-lookup"><span data-stu-id="d9b1b-220">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="d9b1b-221">Шаг <br> 6. Время вызова</span><span class="sxs-lookup"><span data-stu-id="d9b1b-221">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="d9b1b-222">Выберите, что должно происходить, если звонки уже слишком долго ожидаются в очереди.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-222">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="d9b1b-223">Установите **максимальное время ожидания**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-223">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="d9b1b-224">Выберите, что вы хотите сделать, когда время звонка разозвать. Вы можете отключить звонок или перенаправить его.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-224">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="d9b1b-225">Мы рекомендуем перенаправить звонок на одно из следующих мест:</span><span class="sxs-lookup"><span data-stu-id="d9b1b-225">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="d9b1b-226">**Человек в организации —** человек в вашей организации, который может принимать голосовые звонки</span><span class="sxs-lookup"><span data-stu-id="d9b1b-226">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="d9b1b-227">**Приложение голосовой** почты — автозаводка или другая очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-227">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="d9b1b-228">(Выберите учетную запись ресурса, связанную с автозаправлением или очередью вызовов при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="d9b1b-228">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="d9b1b-229">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-229">**External phone number** - any phone number.</span></span> <span data-ttu-id="d9b1b-230">Используйте такой формат: +[код страны][код города][номер телефона]</span><span class="sxs-lookup"><span data-stu-id="d9b1b-230">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="d9b1b-231">**Голосовая** почта: вы можете использовать почтовый ящик созданной вами команды.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-231">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Снимок экрана: параметры времени и времени вызова](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="d9b1b-233">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-233">Click **Save**.</span></span>

<span data-ttu-id="d9b1b-234">В этом случае настройка очереди вызовов будет завершена.</span><span class="sxs-lookup"><span data-stu-id="d9b1b-234">This completes the setup of your call queue.</span></span> <span data-ttu-id="d9b1b-235">Затем вам может потребоваться [настроить автоотекатаря.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="d9b1b-235">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

