---
title: Создание очереди вызовов в Microsoft Teams — учебник для малого бизнеса
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
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
description: Узнайте, как настроить очереди звонка с помощью Microsoft 365 Business Voice.
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909662"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="d1072-103">Создание очереди вызовов — учебник для малого бизнеса</span><span class="sxs-lookup"><span data-stu-id="d1072-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="d1072-104">Очереди вызовов предоставляют способ маршрутизации вызывающих вызовов для людей в организации, которые могут помочь с определенной проблемой или вопросом.</span><span class="sxs-lookup"><span data-stu-id="d1072-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="d1072-105">Звонки распределяются по одному людям в очереди (которые называются *агентами).*</span><span class="sxs-lookup"><span data-stu-id="d1072-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="d1072-106">Очереди вызовов предоставляют:</span><span class="sxs-lookup"><span data-stu-id="d1072-106">Call queues provide:</span></span>

- <span data-ttu-id="d1072-107">Приветствие.</span><span class="sxs-lookup"><span data-stu-id="d1072-107">A greeting message.</span></span>

- <span data-ttu-id="d1072-108">Музыка, пока люди находятся в очереди на удержание.</span><span class="sxs-lookup"><span data-stu-id="d1072-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="d1072-109">Маршрутка вызовов ( *в порядке first In, First Out* (FIFO) для агентов.</span><span class="sxs-lookup"><span data-stu-id="d1072-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="d1072-110">Параметры обработки для переполнения очереди и времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="d1072-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="d1072-111">До начала работы</span><span class="sxs-lookup"><span data-stu-id="d1072-111">Before you begin</span></span>

<span data-ttu-id="d1072-112">Получите [телефонную систему — лицензии](../teams-add-on-licensing/virtual-user.md) виртуальных пользователей, если у вас их еще нет.</span><span class="sxs-lookup"><span data-stu-id="d1072-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="d1072-113">Получите по одному для каждой очереди вызовов и автозавода, которые вы планируете настроить.</span><span class="sxs-lookup"><span data-stu-id="d1072-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="d1072-114">Эти лицензии бесплатны, поэтому мы рекомендуем получить дополнительные лицензии на случай, если вы решите внести изменения в настройку в будущем.</span><span class="sxs-lookup"><span data-stu-id="d1072-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="d1072-115">Так как агенты из очереди звонков могут звонить и возвращать клиентский звонок, вы можете установить для своих агентов, вызывающего звонок, основной номер телефона или номер соответствующего автосбережа.</span><span class="sxs-lookup"><span data-stu-id="d1072-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="d1072-116">Дополнительные сведения см. в сведениях об управлении политиками ИД вызываемой [службы в Microsoft Teams.](../caller-id-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d1072-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="d1072-117">Выполните эти действия, чтобы настроить очередь вызовов</span><span class="sxs-lookup"><span data-stu-id="d1072-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="d1072-118">Шаг <br> 1. Создание команды</span><span class="sxs-lookup"><span data-stu-id="d1072-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="d1072-119">При создании очереди вызовов вы можете добавить отдельных пользователей в очередь или использовать существующую группу безопасности, группу Microsoft 365 или команду Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1072-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="d1072-120">Рекомендуем использовать команду.</span><span class="sxs-lookup"><span data-stu-id="d1072-120">We recommend using a team.</span></span> <span data-ttu-id="d1072-121">Благодаря этому участники очереди могут общаться друг с другом, обмениваться идеями, создавать документы и другие ресурсы для помощи своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="d1072-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="d1072-122">Группа также предоставляет вызывателям голосовой почты почтовый ящик, в который можно отправлять сообщения в не часах или в том случае, если очередь достигает максимальной емкости.</span><span class="sxs-lookup"><span data-stu-id="d1072-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="d1072-123">Создание команды</span><span class="sxs-lookup"><span data-stu-id="d1072-123">To create a team</span></span>

1. <span data-ttu-id="d1072-124">Сначала щелкните **Teams** в левой части приложения, а затем нажмите кнопку **"Присоединиться"** или "Создать команду" в нижней части списка команд.</span><span class="sxs-lookup"><span data-stu-id="d1072-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="d1072-125">Затем нажмите **кнопку "Создать команду"** (первая карточка, левый верхний угол).</span><span class="sxs-lookup"><span data-stu-id="d1072-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="d1072-126">Выберите **"Создать команду с нуля".**</span><span class="sxs-lookup"><span data-stu-id="d1072-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="d1072-127">Затем выберите, нужна ли вам частная или гостевая команда.</span><span class="sxs-lookup"><span data-stu-id="d1072-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="d1072-128">Мы рекомендуем **сделать** очередь личных, чтобы избежать непреднамеренного вхождения людей в очередь путем присоединения к команде.</span><span class="sxs-lookup"><span data-stu-id="d1072-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="d1072-129">Привязайте имя команды и добавьте необязательное описание.</span><span class="sxs-lookup"><span data-stu-id="d1072-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="d1072-130">Когда все будет готово, нажмите кнопку **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="d1072-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="d1072-131">Введите имена людей, которых вы хотите добавить в очередь вызовов, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="d1072-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="d1072-132">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d1072-132">Click **Close**.</span></span> <span data-ttu-id="d1072-133">Люди, которых вы добавите в команду, получат по электронной почте сообщение с сообщением о том, что они теперь являются членами вашей команды, и группа от пока не будет добавлена в их список команд.</span><span class="sxs-lookup"><span data-stu-id="d1072-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1072-134">Шаг 2. Учетные записи ресурсов ></span><span class="sxs-lookup"><span data-stu-id="d1072-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="d1072-135">Шаг <br> 2. Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="d1072-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="d1072-136">Для каждой создаемой очереди вызовов требуется учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d1072-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="d1072-137">Эта учетная запись аналогична учетной записи пользователя, за исключением того, что она связана с автоотчетом или очередью вызовов, а не с человеком.</span><span class="sxs-lookup"><span data-stu-id="d1072-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="d1072-138">На этом шаге мы создадим учетную запись, назначим ее телефонной системе *Microsoft 365 —* лицензию виртуального пользователя, а затем создадим очередь звонков с ее помощью.</span><span class="sxs-lookup"><span data-stu-id="d1072-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="d1072-139">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="d1072-139">Create a resource account</span></span>

<span data-ttu-id="d1072-140">Учетную запись ресурса можно создать в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="d1072-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="d1072-141">В Центре администрирования Teams раз щелкните **"Учетные** записи ресурсов", чтобы развернуть параметры для всей **организации.**</span><span class="sxs-lookup"><span data-stu-id="d1072-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="d1072-142">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d1072-142">Click **Add**.</span></span>

3. <span data-ttu-id="d1072-143">В области **"Добавление учетной** записи ресурса" введите  отображаемого **имени,** имя пользователя и выберите "Очередь зовов" для типа учетной **записи ресурса.**</span><span class="sxs-lookup"><span data-stu-id="d1072-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![Снимок экрана: добавление учетной записи ресурса в пользовательский интерфейс](../media/resource-account-add-cq.png)

4. <span data-ttu-id="d1072-145">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d1072-145">Click **Save**.</span></span>

<span data-ttu-id="d1072-146">Новая учетная запись появится в списке учетных записей.</span><span class="sxs-lookup"><span data-stu-id="d1072-146">The new account will appear in the list of accounts.</span></span>

![Снимок экрана: список учетных записей ресурсов](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="d1072-148">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="d1072-148">Assign a license</span></span>

<span data-ttu-id="d1072-149">Учетной записи ресурса необходимо назначить *лицензию "Телефонная система Microsoft 365 —* виртуальный пользователь".</span><span class="sxs-lookup"><span data-stu-id="d1072-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="d1072-150">В Центре администрирования Microsoft 365 выберите учетную запись ресурса, для которой вы хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="d1072-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="d1072-151">На **вкладке "Лицензии и** приложения" в **области "Лицензии"** выберите **"Телефонная система Microsoft 365 — виртуальный пользователь".**</span><span class="sxs-lookup"><span data-stu-id="d1072-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="d1072-152">Нажмите **кнопку "Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="d1072-152">Click **Save changes**.</span></span>

    ![Снимок экрана: пользовательский интерфейс назначения лицензий в Центре администрирования Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="d1072-154">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="d1072-154">Create a call queue</span></span>

<span data-ttu-id="d1072-155">Затем мы начнем создавать новую очередь зовов и назначаем учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="d1072-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="d1072-156">В Центре администрирования Teams раззовите **"Голосовая команда",** **выберите**"Очереди зовов" и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="d1072-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="d1072-157">Введите имя очереди звонка.</span><span class="sxs-lookup"><span data-stu-id="d1072-157">Type a name for the call queue.</span></span> <span data-ttu-id="d1072-158">Это имя будет видно агентам при входящих вызовах из очереди.</span><span class="sxs-lookup"><span data-stu-id="d1072-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="d1072-159">Нажмите **кнопку "Добавить учетные** записи", найдите учетную запись ресурса, которую вы хотите использовать с этой очередью вызовов, нажмите кнопку "Добавить", а затем нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="d1072-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="d1072-160">Выберите язык.</span><span class="sxs-lookup"><span data-stu-id="d1072-160">Choose a language.</span></span> <span data-ttu-id="d1072-161">Этот язык будет использоваться для системных голосовых подсказок и транскрибации голосовой почты (если вы их включаете).</span><span class="sxs-lookup"><span data-stu-id="d1072-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Снимок экрана: учетная запись ресурса и языковые параметры](../media/call-queue-name-language.png)

4. <span data-ttu-id="d1072-163">Укажите, хотите ли вы воспроизведения приветствия вызывателям при их поступления в очередь.</span><span class="sxs-lookup"><span data-stu-id="d1072-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="d1072-164">Необходимо отправить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="d1072-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="d1072-165">Teams предоставляет музыку по умолчанию вызывателям, пока они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="d1072-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="d1072-166">Если вы хотите воспроизведения определенного  звукового файла, выберите "Воспроизведения звукового файла" и загрузите файл MP3, WAV или WMA.</span><span class="sxs-lookup"><span data-stu-id="d1072-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="d1072-167">Размер добавленной записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="d1072-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="d1072-168">По умолчанию музыка, которая предоставляется в очередях вызовов Teams, не предоставляется вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="d1072-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1072-169">Шаг 3. Звонок агентам ></span><span class="sxs-lookup"><span data-stu-id="d1072-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="d1072-170">Шаг <br> 3. Агенты по звонкам</span><span class="sxs-lookup"><span data-stu-id="d1072-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="d1072-171">Чтобы добавить агентов в очередь вызовов, мы добавим ранее созданную команду.</span><span class="sxs-lookup"><span data-stu-id="d1072-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="d1072-172">Нажмите **кнопку "Добавить группы".**</span><span class="sxs-lookup"><span data-stu-id="d1072-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="d1072-173">Введите имя группы, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="d1072-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="d1072-174">Нажмите **кнопку "Добавить"** и выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="d1072-174">Click **Add**, and then click **Add**.</span></span>

    ![Снимок экрана: параметры пользователей и групп для очередей вызовов](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="d1072-176">Вы можете добавить до 20 агентов по отдельности и до 200 агентов с помощью групп или команд.</span><span class="sxs-lookup"><span data-stu-id="d1072-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="d1072-177">При добавлении новых пользователей в команду первый звонок может занять до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="d1072-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1072-178">Шаг 4. Учетные записи ресурсов ></span><span class="sxs-lookup"><span data-stu-id="d1072-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="d1072-179">Шаг <br> 4. Маршрутка вызовов</span><span class="sxs-lookup"><span data-stu-id="d1072-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="d1072-180">Выберите нужный способ маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="d1072-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="d1072-181">Установите режим  **конференции автоматическим.**</span><span class="sxs-lookup"><span data-stu-id="d1072-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="d1072-182">Выберите **нужный способ** маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="d1072-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="d1072-183">Это определяет порядок, в котором агенты получают звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="d1072-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="d1072-184">Рекомендуем **серийный маршрут или Округлевую** **юлеву.**</span><span class="sxs-lookup"><span data-stu-id="d1072-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="d1072-185">Выберите один из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d1072-185">Choose from these options:</span></span>

    - <span data-ttu-id="d1072-186">**Маршрутка с помощником** одновременно звонит всем агентам в очереди.</span><span class="sxs-lookup"><span data-stu-id="d1072-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="d1072-187">Звонок получает первый агент, который звонит.</span><span class="sxs-lookup"><span data-stu-id="d1072-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="d1072-188">**В последовательной маршрутке** все агенты звонят по одному.</span><span class="sxs-lookup"><span data-stu-id="d1072-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="d1072-189">Если агент отклоает или не берет звонок, звонок будет звонить следующему агенту и будет пытаться все агенты до тех пор, пока он не будет разозвать или невызовется.</span><span class="sxs-lookup"><span data-stu-id="d1072-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="d1072-190">**Round balances** the routing of incoming calls so each call agent gets the same number of calls from the queue.</span><span class="sxs-lookup"><span data-stu-id="d1072-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="d1072-191">Это может быть нежелательно в среде входящие продаж, чтобы гарантировать равные возможности для всех агентов по звонкам.</span><span class="sxs-lookup"><span data-stu-id="d1072-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="d1072-192">**Наиболее длинные** неавтомитные маршруты каждый звонок агенту, который простаивает самый длительный срок.</span><span class="sxs-lookup"><span data-stu-id="d1072-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="d1072-193">(Агенты, состояние присутствия которых было "Нет на сети" более 10 минут, не включаются.)</span><span class="sxs-lookup"><span data-stu-id="d1072-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Снимок экрана: параметры режима конференции и способа маршрутации](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="d1072-195">**Включив маршрутную маршрутику на основе присутствия.**</span><span class="sxs-lookup"><span data-stu-id="d1072-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="d1072-196">В этом случае звонки будут маршрутизовы агентам со статусом "В **сети".**</span><span class="sxs-lookup"><span data-stu-id="d1072-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="d1072-197">Выберите, нужно ли разрешить агентам отказаться от звонков.</span><span class="sxs-lookup"><span data-stu-id="d1072-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="d1072-198">Укажите **время оповещения** агента, чтобы указать, как долго телефон агента будет звонить до того, как очередь перенаправит звонок следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="d1072-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Снимок экрана: параметры времени маршрутинга, отказа от работы и оповещений](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1072-200">Шаг 5. Переполнение вызовов ></span><span class="sxs-lookup"><span data-stu-id="d1072-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="d1072-201">Шаг <br> 5. Переполнение звонка</span><span class="sxs-lookup"><span data-stu-id="d1072-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="d1072-202">Выберите, как обрабатывать вызовы, превышают максимальное значение в очереди.</span><span class="sxs-lookup"><span data-stu-id="d1072-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="d1072-203">Установите **максимальное число звонков в очереди.**</span><span class="sxs-lookup"><span data-stu-id="d1072-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="d1072-204">Выберите, что вы хотите сделать, когда достигается максимальное количество звонков.</span><span class="sxs-lookup"><span data-stu-id="d1072-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="d1072-205">Вы можете отключить звонок или перенаправить его.</span><span class="sxs-lookup"><span data-stu-id="d1072-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="d1072-206">Мы рекомендуем перенаправить звонок на одно из следующих назначений:</span><span class="sxs-lookup"><span data-stu-id="d1072-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="d1072-207">**Человек в организации —** человек в организации, который может принимать голосовые звонки</span><span class="sxs-lookup"><span data-stu-id="d1072-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="d1072-208">**Приложение голосовой** почты — автозавод или другая очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="d1072-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="d1072-209">(Выберите учетную запись ресурса, связанную с автостраницой или очередью вызовов, при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="d1072-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="d1072-210">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="d1072-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="d1072-211">Используйте такой формат: +[код страны][код города][номер телефона]</span><span class="sxs-lookup"><span data-stu-id="d1072-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="d1072-212">**Голосовая** почта — вы можете использовать почтовый ящик созданной вами группы голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="d1072-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Снимок экрана: параметры переполнения звонка](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1072-214">Шаг 6. Время ></span><span class="sxs-lookup"><span data-stu-id="d1072-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="d1072-215">Шаг <br> 6. Время вызова</span><span class="sxs-lookup"><span data-stu-id="d1072-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="d1072-216">Выберите, что должно происходить, когда звонки будут ждать в очереди слишком долго.</span><span class="sxs-lookup"><span data-stu-id="d1072-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="d1072-217">Настройка времени **ожидания звонка: максимальное время ожидания.**</span><span class="sxs-lookup"><span data-stu-id="d1072-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="d1072-218">Выберите, что вы хотите делать, когда разоберется время звонка. Вы можете отключить звонок или перенаправить его.</span><span class="sxs-lookup"><span data-stu-id="d1072-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="d1072-219">Мы рекомендуем перенаправить звонок на одно из следующих назначений:</span><span class="sxs-lookup"><span data-stu-id="d1072-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="d1072-220">**Человек в организации —** человек в организации, который может принимать голосовые звонки</span><span class="sxs-lookup"><span data-stu-id="d1072-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="d1072-221">**Приложение голосовой** почты — автозавод или другая очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="d1072-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="d1072-222">(Выберите учетную запись ресурса, связанную с автостраницой или очередью вызовов, при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="d1072-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="d1072-223">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="d1072-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="d1072-224">Используйте такой формат: +[код страны][код города][номер телефона]</span><span class="sxs-lookup"><span data-stu-id="d1072-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="d1072-225">**Голосовая** почта — вы можете использовать почтовый ящик созданной вами группы голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="d1072-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Снимок экрана: параметры времени и времени вызова](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="d1072-227">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d1072-227">Click **Save**.</span></span>

<span data-ttu-id="d1072-228">В этом случае настройка очереди звонка будет завершена.</span><span class="sxs-lookup"><span data-stu-id="d1072-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="d1072-229">Затем может потребоваться настроить [автозаполнеть.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="d1072-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

