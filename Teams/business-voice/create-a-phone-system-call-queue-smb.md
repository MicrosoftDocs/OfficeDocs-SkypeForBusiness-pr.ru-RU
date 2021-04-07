---
title: Создание очереди вызовов в Microsoft Teams — учебник для малого бизнеса
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
description: Узнайте, как настроить очереди вызовов с помощью Microsoft 365 Business Voice.
ms.openlocfilehash: 40018ce331dfe8516e00c6781373d528a71e85c5
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607561"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="e5eb8-103">Создание очереди вызовов — учебник для малого бизнеса</span><span class="sxs-lookup"><span data-stu-id="e5eb8-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="e5eb8-104">Очереди вызовов предоставляют способ маршрутизации вызывающих вызовов для людей в организации, которые могут помочь в решения определенной проблемы или вопроса.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="e5eb8-105">Звонки распределяются по одному людям в очереди (которые называются *агентами).*</span><span class="sxs-lookup"><span data-stu-id="e5eb8-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="e5eb8-106">Очереди вызовов предоставляют:</span><span class="sxs-lookup"><span data-stu-id="e5eb8-106">Call queues provide:</span></span>

- <span data-ttu-id="e5eb8-107">Приветствие.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-107">A greeting message.</span></span>

- <span data-ttu-id="e5eb8-108">Музыка, пока люди находятся в очереди на удержание.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="e5eb8-109">Маршрутка вызовов ( *в порядке first In, First Out* (FIFO) для агентов.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="e5eb8-110">Параметры обработки для переполнения очереди и времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="e5eb8-111">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="e5eb8-111">Before you begin</span></span>

<span data-ttu-id="e5eb8-112">Получите [телефонную систему — лицензии](../teams-add-on-licensing/virtual-user.md) виртуальных пользователей, если у вас их еще нет.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="e5eb8-113">Получите по одному для каждой очереди вызовов и автозавода, которые вы планируете настроить.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="e5eb8-114">Эти лицензии бесплатны, поэтому мы рекомендуем получить дополнительные лицензии на случай, если вы решите внести изменения в настройку в будущем.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="e5eb8-115">Так как агенты из очереди звонков могут звонить и возвращать клиентский звонок, вы можете установить для своих агентов, вызывающего звонок, основной номер телефона или номер соответствующего автосбережа.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="e5eb8-116">Дополнительные сведения см. в сведениях об управлении политиками ИД вызываемой [службы в Microsoft Teams.](../caller-id-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb8-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="e5eb8-117">Выполните эти действия, чтобы настроить очередь вызовов</span><span class="sxs-lookup"><span data-stu-id="e5eb8-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="e5eb8-118">Шаг <br> 1. Создание команды</span><span class="sxs-lookup"><span data-stu-id="e5eb8-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="e5eb8-119">При создании очереди вызовов вы можете добавить отдельных пользователей в очередь или использовать существующую группу безопасности, группу Microsoft 365 или команду Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="e5eb8-120">Мы рекомендуем [использовать канал команды.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="e5eb8-120">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="e5eb8-121">Благодаря этому участники очереди могут общаться друг с другом, обмениваться идеями, создавать документы и другие ресурсы для помощи своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="e5eb8-122">Группа также предоставляет вызывателям голосовой почты почтовый ящик, в который можно отправлять сообщения в не часах или в том случае, если очередь достигает максимальной емкости.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="e5eb8-123">Создание команды</span><span class="sxs-lookup"><span data-stu-id="e5eb8-123">To create a team</span></span>

1. <span data-ttu-id="e5eb8-124">Сначала щелкните **Teams** в левой части приложения, а затем нажмите кнопку **"Присоединиться"** или "Создать команду" в нижней части списка команд.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="e5eb8-125">Затем нажмите **кнопку "Создать команду"** (первая карточка, левый верхний угол).</span><span class="sxs-lookup"><span data-stu-id="e5eb8-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="e5eb8-126">Выберите **"Создать команду с нуля".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="e5eb8-127">Затем выберите, нужна ли вам частная или гостевая команда.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="e5eb8-128">Мы рекомендуем **сделать** очередь личных, чтобы избежать непреднамеренного вхождения людей в очередь путем присоединения к команде.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="e5eb8-129">Привязайте имя команды и добавьте необязательное описание.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="e5eb8-130">Когда все будет готово, нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="e5eb8-131">Введите имена людей, которых вы хотите добавить в очередь вызовов, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="e5eb8-132">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-132">Click **Close**.</span></span> <span data-ttu-id="e5eb8-133">Люди, которых вы добавите в группу, получат по электронной почте сообщение о том, что они теперь являются членами вашей команды, и они будут добавлены в список своих команд.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="e5eb8-134">Затем мы добавим канал для использования с очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-134">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="e5eb8-135">Добавление канала</span><span class="sxs-lookup"><span data-stu-id="e5eb8-135">To add a channel</span></span>

1. <span data-ttu-id="e5eb8-136">В Teams найдите только что созданную команду, щелкните "Дополнительные **параметры"** (...), а затем выберите команду **"Добавить канал".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-136">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="e5eb8-137">Введите название и описание канала, а затем нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-137">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5eb8-138">Шаг 2. Учетные записи ресурсов ></span><span class="sxs-lookup"><span data-stu-id="e5eb8-138">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="e5eb8-139">Шаг <br> 2. Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="e5eb8-139">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="e5eb8-140">Для каждой создаемой очереди вызовов требуется учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-140">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="e5eb8-141">Эта учетная запись аналогична учетной записи пользователя, за исключением того, что она связана с автоотчетом или очередью вызовов, а не с человеком.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-141">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="e5eb8-142">На этом шаге мы создадим учетную запись, назначим ее телефонной системе *Microsoft 365 —* лицензию виртуального пользователя, а затем создадим очередь звонков с ее помощью.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-142">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="e5eb8-143">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="e5eb8-143">Create a resource account</span></span>

<span data-ttu-id="e5eb8-144">Учетную запись ресурса можно создать в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-144">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="e5eb8-145">В Центре администрирования Teams раз щелкните **"Учетные** записи ресурсов", чтобы развернуть параметры для всей **организации.**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-145">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="e5eb8-146">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-146">Click **Add**.</span></span>

3. <span data-ttu-id="e5eb8-147">В области **"Добавление учетной** записи ресурса" введите  отображаемого **имени,** имя пользователя и выберите "Очередь зовов" для типа учетной **записи ресурса.**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-147">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="e5eb8-148">Когда агенты получают входящий звонок из очереди, отображается отображаемая имя.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-148">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![Снимок экрана: добавление учетной записи ресурса в пользовательский интерфейс](../media/resource-account-add-cq.png)

4. <span data-ttu-id="e5eb8-150">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-150">Click **Save**.</span></span>

<span data-ttu-id="e5eb8-151">Новая учетная запись появится в списке учетных записей.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-151">The new account will appear in the list of accounts.</span></span>

![Снимок экрана: список учетных записей ресурсов](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="e5eb8-153">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="e5eb8-153">Assign a license</span></span>

<span data-ttu-id="e5eb8-154">Учетной записи ресурса необходимо назначить *лицензию "Телефонная система Microsoft 365 —* виртуальный пользователь".</span><span class="sxs-lookup"><span data-stu-id="e5eb8-154">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="e5eb8-155">В Центре администрирования Microsoft 365 в списке активных пользователей выберите учетную запись ресурса, для которой хотите назначить лицензию. </span><span class="sxs-lookup"><span data-stu-id="e5eb8-155">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="e5eb8-156">На **вкладке "Лицензии и** приложения" в **области "Лицензии"** выберите **"Телефонная система Microsoft 365 — виртуальный пользователь".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-156">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="e5eb8-157">Нажмите **кнопку "Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-157">Click **Save changes**.</span></span>

    ![Снимок экрана: пользовательский интерфейс назначения лицензий в Центре администрирования Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="e5eb8-159">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="e5eb8-159">Create a call queue</span></span>

<span data-ttu-id="e5eb8-160">Затем мы начнем создавать новую очередь зовов и назначаем учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-160">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="e5eb8-161">В Центре администрирования Teams раззовите **"Голосовая команда",** **выберите**"Очереди зовов" и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-161">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="e5eb8-162">Введите имя очереди звонка.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-162">Type a name for the call queue.</span></span>

2. <span data-ttu-id="e5eb8-163">Нажмите **кнопку "Добавить учетные** записи", найдите учетную запись ресурса, которую вы хотите использовать с этой очередью вызовов, нажмите кнопку "Добавить", а затем нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-163">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="e5eb8-164">Выберите язык.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-164">Choose a language.</span></span> <span data-ttu-id="e5eb8-165">Этот язык будет использоваться для системных голосовых подсказок и транскрибации голосовой почты (если вы их включаете).</span><span class="sxs-lookup"><span data-stu-id="e5eb8-165">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Снимок экрана: учетная запись ресурса и языковые параметры](../media/call-queue-name-language.png)

4. <span data-ttu-id="e5eb8-167">Укажите, хотите ли вы воспроизведения приветствия вызывателям при их поступления в очередь.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-167">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="e5eb8-168">Необходимо отправить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-168">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="e5eb8-169">Teams предоставляет музыку по умолчанию вызывателям, пока они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-169">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="e5eb8-170">Если вы хотите воспроизведения определенного  звукового файла, выберите "Воспроизведения звукового файла" и загрузите файл MP3, WAV или WMA.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-170">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="e5eb8-171">Размер добавленной записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-171">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="e5eb8-172">По умолчанию музыка, которая предоставляется в очередях вызовов Teams, не предоставляется вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-172">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5eb8-173">Шаг 3. Звонок агентам ></span><span class="sxs-lookup"><span data-stu-id="e5eb8-173">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="e5eb8-174">Шаг <br> 3. Агенты по звонкам</span><span class="sxs-lookup"><span data-stu-id="e5eb8-174">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="e5eb8-175">Чтобы добавить агентов в очередь звонка, мы добавим их в команду и канал, которые мы создали ранее.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-175">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="e5eb8-176">Выберите команду **"Выбрать команду"** и нажмите кнопку **"Добавить канал".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-176">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="e5eb8-177">Введите имя группы, которую вы создали, выберите ее и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-177">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="e5eb8-178">Выберите канал, созданный для очереди.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-178">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="e5eb8-179">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-179">Click **Apply**.</span></span>

    ![Снимок экрана: параметры пользователей и групп для очередей вызовов](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="e5eb8-181">При добавлении новых пользователей в команду первый звонок может занять до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-181">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5eb8-182">Шаг 4. Учетные записи ресурсов ></span><span class="sxs-lookup"><span data-stu-id="e5eb8-182">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="e5eb8-183">Шаг <br> 4. Маршрутка вызовов</span><span class="sxs-lookup"><span data-stu-id="e5eb8-183">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="e5eb8-184">Выберите нужный способ маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-184">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="e5eb8-185">Установите режим  **конференции автоматическим.**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-185">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="e5eb8-186">Выберите **нужный способ** маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-186">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="e5eb8-187">Это определяет порядок, в котором агенты получают звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-187">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="e5eb8-188">Мы рекомендуем **серийный маршрут или** **Round роуминг.**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-188">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="e5eb8-189">Выберите один из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e5eb8-189">Choose from these options:</span></span>

    - <span data-ttu-id="e5eb8-190">**Маршрутка с помощником** одновременно звонит всем агентам в очереди.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-190">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="e5eb8-191">Звонок получает первый агент, который звонит.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-191">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="e5eb8-192">**В последовательной маршрутке** все агенты звонят по одному.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-192">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="e5eb8-193">Если агент отклоает или не берет звонок, звонок звонит следующему агенту и будет пытаться все агенты до тех пор, пока он не будет разозвать или невызовется.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-193">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="e5eb8-194">**Round balances** the routing of incoming calls so each call agent gets same number of calls from the queue.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-194">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="e5eb8-195">Это может быть нежелательно в среде входящие продаж, чтобы гарантировать равные возможности для всех агентов по звонкам.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-195">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="e5eb8-196">**Наиболее длинные** неавтомитные маршруты каждый звонок агенту, который простаивает самый длительный срок.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-196">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="e5eb8-197">(Агенты, состояние присутствия которых было "Нет на сети" более 10 минут, не включаются.)</span><span class="sxs-lookup"><span data-stu-id="e5eb8-197">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Снимок экрана: режим конференции и параметры метода маршрутации](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="e5eb8-199">**Включив маршрутную маршрутику на основе присутствия.**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-199">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="e5eb8-200">В этом случае звонки будут маршрутизовы агентам со статусом "В **сети".**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-200">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="e5eb8-201">Выберите, нужно ли разрешить агентам отказаться от звонков.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-201">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="e5eb8-202">Укажите **время оповещения** агента, чтобы указать, как долго телефон агента будет звонить до того, как очередь перенаправит звонок следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-202">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Снимок экрана: параметры времени маршрутинга, отказа от работы и оповещений](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5eb8-204">Шаг 5. Переполнение вызовов ></span><span class="sxs-lookup"><span data-stu-id="e5eb8-204">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="e5eb8-205">Шаг <br> 5. Переполнение звонка</span><span class="sxs-lookup"><span data-stu-id="e5eb8-205">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="e5eb8-206">Выберите, как обрабатывать вызовы, превышают максимальное значение в очереди.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-206">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="e5eb8-207">Установите **максимальное число звонков в очереди.**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-207">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="e5eb8-208">Выберите, что вы хотите сделать, когда достигается максимальное количество звонков.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-208">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="e5eb8-209">Вы можете отключить звонок или перенаправить его.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-209">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="e5eb8-210">Мы рекомендуем перенаправить звонок на одно из следующих назначений:</span><span class="sxs-lookup"><span data-stu-id="e5eb8-210">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="e5eb8-211">**Человек в организации —** человек в организации, который может принимать голосовые звонки</span><span class="sxs-lookup"><span data-stu-id="e5eb8-211">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="e5eb8-212">**Приложение голосовой** почты — автоотекатарь или другая очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-212">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="e5eb8-213">(Выберите учетную запись ресурса, связанную с автостраницой или очередью вызовов, при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="e5eb8-213">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="e5eb8-214">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-214">**External phone number** - any phone number.</span></span> <span data-ttu-id="e5eb8-215">Используйте такой формат: +[код страны][код города][номер телефона]</span><span class="sxs-lookup"><span data-stu-id="e5eb8-215">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="e5eb8-216">**Голосовая** почта — вы можете использовать почтовый ящик созданной вами группы голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-216">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Снимок экрана: параметры переполнения звонка](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="e5eb8-218">Шаг 6. Время ></span><span class="sxs-lookup"><span data-stu-id="e5eb8-218">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="e5eb8-219">Шаг <br> 6. Время вызова</span><span class="sxs-lookup"><span data-stu-id="e5eb8-219">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="e5eb8-220">Выберите, что должно происходить, когда звонки будут ждать в очереди слишком долго.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-220">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="e5eb8-221">Установить **максимальное время ожидания.**</span><span class="sxs-lookup"><span data-stu-id="e5eb8-221">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="e5eb8-222">Выберите, что вы хотите делать, когда разоберется время звонка. Вы можете отключить звонок или перенаправить его.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-222">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="e5eb8-223">Мы рекомендуем перенаправить звонок на одно из следующих назначений:</span><span class="sxs-lookup"><span data-stu-id="e5eb8-223">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="e5eb8-224">**Человек в организации —** человек в организации, который может принимать голосовые звонки</span><span class="sxs-lookup"><span data-stu-id="e5eb8-224">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="e5eb8-225">**Приложение голосовой** почты — автозавод или другая очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-225">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="e5eb8-226">(Выберите учетную запись ресурса, связанную с автостраницой или очередью вызовов, при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="e5eb8-226">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="e5eb8-227">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-227">**External phone number** - any phone number.</span></span> <span data-ttu-id="e5eb8-228">Используйте такой формат: +[код страны][код города][номер телефона]</span><span class="sxs-lookup"><span data-stu-id="e5eb8-228">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="e5eb8-229">**Голосовая** почта — вы можете использовать почтовый ящик созданной вами группы голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-229">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Снимок экрана: параметры времени и времени вызова](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="e5eb8-231">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-231">Click **Save**.</span></span>

<span data-ttu-id="e5eb8-232">В этом случае настройка очереди звонка будет завершена.</span><span class="sxs-lookup"><span data-stu-id="e5eb8-232">This completes the setup of your call queue.</span></span> <span data-ttu-id="e5eb8-233">Далее вам может потребоваться [настроить автоотекатаря.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="e5eb8-233">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

