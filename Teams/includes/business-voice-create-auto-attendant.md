#### <a name="video-demonstration"></a><span data-ttu-id="c8d95-101">Демонстрация видео</span><span class="sxs-lookup"><span data-stu-id="c8d95-101">Video demonstration</span></span>

<span data-ttu-id="c8d95-102">В этом видеоролике показан простой пример создания автозавода в Teams.</span><span class="sxs-lookup"><span data-stu-id="c8d95-102">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="c8d95-103">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="c8d95-103">Before you begin</span></span>

<span data-ttu-id="c8d95-104">Получите номера служб (номера служб — это особый тип номеров телефонов, которые используются автослужавами), необходимые для автозаполнения, которые должны быть доступны при прямом наборе номера из-за пределов организации.</span><span class="sxs-lookup"><span data-stu-id="c8d95-104">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="c8d95-105">Это может быть [перенос номеров от другого поставщика](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) или запрос [новых номеров служб.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="c8d95-105">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="c8d95-106">Каждому автозаводщику должна быть назначена лицензия телефонная система — виртуальный пользователь.</span><span class="sxs-lookup"><span data-stu-id="c8d95-106">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="c8d95-107">При приобретении бизнес-голосовой почты вы также телефонная система лицензий виртуальных пользователей, поэтому вам, вероятно, не нужно запрашивать дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="c8d95-107">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="c8d95-108">Однако если в будущем вам потребуется больше, вы можете получить их, следуя инструкциям в телефонная система [— лицензия виртуального пользователя](../teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="c8d95-108">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="c8d95-109">Если вы хотите, чтобы во время праздников [](../set-up-holidays-in-teams.md) звонки автоответы перенаводились по-разному, создайте праздники, которые вы хотите использовать, прежде чем создавать автоответ.</span><span class="sxs-lookup"><span data-stu-id="c8d95-109">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="c8d95-110">Выполните указанные здесь действия, чтобы настроить автозавод</span><span class="sxs-lookup"><span data-stu-id="c8d95-110">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="c8d95-111">Шаг 1 <br> Телефон номера</span><span class="sxs-lookup"><span data-stu-id="c8d95-111">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="c8d95-112">Если вы впервые настроили бизнес-голосовую связи и работаете на этапе **Шаг 6.** Настройка автозавода для основного номера телефона вашей компании, вы уже завершили действия, которые вы сделали на этой вкладке. Переход на следующую вкладку: Общие [сведения автосектора](?tabs=general-info#steps).</span><span class="sxs-lookup"><span data-stu-id="c8d95-112">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="c8d95-113">Для каждого создаваемго автозавода требуется учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="c8d95-113">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="c8d95-114">Эта учетная запись аналогична учетной записи пользователя, за исключением того, что она связана с автозаводом или очередью вызовов, а не с пользователем.</span><span class="sxs-lookup"><span data-stu-id="c8d95-114">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="c8d95-115">На этом шаге мы создадим учетную запись, назначим Microsoft 365 телефонная система *лицензию виртуального* пользователя, а затем назначим номер службы.</span><span class="sxs-lookup"><span data-stu-id="c8d95-115">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="c8d95-116">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="c8d95-116">Create a resource account</span></span>

<span data-ttu-id="c8d95-117">Вы можете создать учетную запись ресурса в Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="c8d95-117">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="c8d95-118">В центре Teams разметка **параметров** для всей организации и нажмите кнопку **Учетные записи ресурсов.**</span><span class="sxs-lookup"><span data-stu-id="c8d95-118">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="c8d95-119">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-119">Click **Add**.</span></span>

3. <span data-ttu-id="c8d95-120">В области Добавление **учетной записи** ресурса введите отображаемого имени **,** **имя пользователя** и выберите автоотчет для типа **учетной записи ресурса.** </span><span class="sxs-lookup"><span data-stu-id="c8d95-120">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Снимок экрана: добавление пользовательского интерфейса учетной записи ресурса](../media/resource-account-add.png)

4. <span data-ttu-id="c8d95-122">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-122">Click **Save**.</span></span>

    <span data-ttu-id="c8d95-123">Новая учетная запись появится в списке учетных записей.</span><span class="sxs-lookup"><span data-stu-id="c8d95-123">The new account will appear in the list of accounts.</span></span>

    ![Снимок экрана: список учетных записей ресурсов](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="c8d95-125">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="c8d95-125">Assign a license</span></span>

<span data-ttu-id="c8d95-126">Учетной записи *ресурса Microsoft 365 телефонная система лицензию виртуальный* пользователь.</span><span class="sxs-lookup"><span data-stu-id="c8d95-126">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="c8d95-127">В центре Microsoft 365 выберите учетную запись ресурса, для которой вы хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="c8d95-127">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="c8d95-128">На **вкладке Лицензии и приложения** в области **Лицензии** выберите Microsoft 365 телефонная система **— виртуальный пользователь**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-128">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="c8d95-129">Нажмите **кнопку Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="c8d95-129">Click **Save changes**.</span></span>

    ![Снимок экрана: пользовательский интерфейс назначения лицензий в центре Microsoft 365 администрирования](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="c8d95-131">Назначение номера службы</span><span class="sxs-lookup"><span data-stu-id="c8d95-131">Assign a service number</span></span>

<span data-ttu-id="c8d95-132">Если вы хотите, чтобы с этим автоотчетом можно было связаться по номеру телефона, назначьте этот номер учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="c8d95-132">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="c8d95-133">В Центре Teams администрирования на  странице Учетные записи ресурсов выберите учетную запись ресурса, для которой нужно назначить номер службы, и нажмите кнопку **Назначить/отозначить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-133">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="c8d95-134">В **Телефон тип номера** выберите нужный тип.</span><span class="sxs-lookup"><span data-stu-id="c8d95-134">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="c8d95-135">В **поле Назначен номер телефона** найдите нужный номер и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="c8d95-135">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Снимок экрана: пользовательский интерфейс назначения номера службы](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="c8d95-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-137">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8d95-138">Шаг 2. Общие сведения для автосектора ></span><span class="sxs-lookup"><span data-stu-id="c8d95-138">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="c8d95-139">Шаг 2 <br> Общие сведения о помощнике</span><span class="sxs-lookup"><span data-stu-id="c8d95-139">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="c8d95-140">Настройка автозавода</span><span class="sxs-lookup"><span data-stu-id="c8d95-140">To set up an auto attendant</span></span>

1. <span data-ttu-id="c8d95-141">В центре Teams разойдите в **центр администрирования, разойдите на кнопку Голосовая** почта , **выберите** автозаметки и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-141">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="c8d95-142">Введите имя автозавода в поле в верхней части окна.</span><span class="sxs-lookup"><span data-stu-id="c8d95-142">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="c8d95-143">Если вы хотите назначить оператора, укажите назначение для звонков на этот оператор.</span><span class="sxs-lookup"><span data-stu-id="c8d95-143">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="c8d95-144">Это необязательно (но рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="c8d95-144">This is optional (but recommended).</span></span> <span data-ttu-id="c8d95-145">Вы можете установить параметр **Оператор,** чтобы разрешить вызывателям выйти из меню и поговорить с назначенным человеком.</span><span class="sxs-lookup"><span data-stu-id="c8d95-145">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="c8d95-146">Укажите часовой пояс для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="c8d95-146">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="c8d95-147">Часовой пояс используется для вычисления рабочих часов, если вы создаете отдельный поток зовов в не часах.</span><span class="sxs-lookup"><span data-stu-id="c8d95-147">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="c8d95-148">Укажите язык для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="c8d95-148">Specify a language for this auto attendant.</span></span> <span data-ttu-id="c8d95-149">Этот язык будет использоваться для системных голосовых подсказок.</span><span class="sxs-lookup"><span data-stu-id="c8d95-149">This is the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="c8d95-150">Выберите, нужно ли включить голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="c8d95-150">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="c8d95-151">Если этот параметр включен, имя каждого параметра меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="c8d95-151">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="c8d95-152">Например, можно сказать "Один" для выбора параметра меню, назначенного клавише 1, или "Продажи", чтобы выбрать пункт меню "Продажи".</span><span class="sxs-lookup"><span data-stu-id="c8d95-152">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Снимок экрана: параметры автозавода для имени, оператора, часового пояса, языка и голосового ввода](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="c8d95-154">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-154">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8d95-155">Шаг 3. Поток ></span><span class="sxs-lookup"><span data-stu-id="c8d95-155">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="c8d95-156">Шаг <br> 3. Поток вызовов</span><span class="sxs-lookup"><span data-stu-id="c8d95-156">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="c8d95-157">Выбор параметров потока зова</span><span class="sxs-lookup"><span data-stu-id="c8d95-157">Choose your call flow options</span></span>

1. <span data-ttu-id="c8d95-158">Выберите, хотите ли вы воспроизведения приветствия, когда автоответ отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="c8d95-158">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="c8d95-159">Если вы **выберете "Звукозапись",** с помощью Upload файла можно добавить записанное приветствие, сохраненное в качестве звукового файла.  WAV, .MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="c8d95-159">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="c8d95-160">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="c8d95-160">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="c8d95-161">Если выбрать **Введите приветствие,** система прочитает текст, который вы введите (до 1000 символов), когда автозавет ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="c8d95-161">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Снимок экрана: параметры приветствия сообщения](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="c8d95-163">Выберите, как вы хотите перена маршрутизовыть звонок.</span><span class="sxs-lookup"><span data-stu-id="c8d95-163">Choose how you want to route the call.</span></span>

    <span data-ttu-id="c8d95-164">Если вы **выберете Отключить,** автозаводщик повесит вызов.</span><span class="sxs-lookup"><span data-stu-id="c8d95-164">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="c8d95-165">Если вы выбрали **Перенаправить** звонок , вы можете выбрать одно из назначений маршрутиации зовов.</span><span class="sxs-lookup"><span data-stu-id="c8d95-165">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="c8d95-166">Если вы выбрали **Параметры меню**  Воспроизведения, вы  можете выбрать вариант Воспроизведения звукового файла или Ввести приветствие, а затем выбрать параметры меню и поиск по каталогу.</span><span class="sxs-lookup"><span data-stu-id="c8d95-166">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Снимок экрана: параметры маршрутизов параметров маршрутизов](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="c8d95-168">Если вы хотите использовать для навигации клавиши набора номера, в области Настройка параметров меню выберите, что должно происходить при нажатии клавиши набора. </span><span class="sxs-lookup"><span data-stu-id="c8d95-168">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="c8d95-169">(Если вы создаете этого автозавода в качестве каталога организации, оставьте параметры набора параметров пустыми.)</span><span class="sxs-lookup"><span data-stu-id="c8d95-169">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="c8d95-170">Вы можете настроить любую из этих клавиш для следующих назначений:</span><span class="sxs-lookup"><span data-stu-id="c8d95-170">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="c8d95-171">**Человек в организации —** это человек в вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="c8d95-171">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="c8d95-172">**Голосовое приложение** — другой автозаводщик или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="c8d95-172">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="c8d95-173">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="c8d95-173">**External phone number** - any phone number.</span></span> <span data-ttu-id="c8d95-174">Используйте такой формат: +[код страны][код города][номер телефона]</span><span class="sxs-lookup"><span data-stu-id="c8d95-174">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="c8d95-175">**Голосовая почта** — почтовый ящик голосовой почты, связанный с Microsoft 365 группой, которую вы указали.</span><span class="sxs-lookup"><span data-stu-id="c8d95-175">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="c8d95-176">**Оператор** — оператор, определенный для автозавода.</span><span class="sxs-lookup"><span data-stu-id="c8d95-176">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="c8d95-177">Определение оператора необязательно.</span><span class="sxs-lookup"><span data-stu-id="c8d95-177">Defining an operator is optional.</span></span> <span data-ttu-id="c8d95-178">Оператор можно определить как любой другой пункт назначения в этом списке.</span><span class="sxs-lookup"><span data-stu-id="c8d95-178">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="c8d95-179">Мы рекомендуем установить для оператора клавишу 0.</span><span class="sxs-lookup"><span data-stu-id="c8d95-179">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="c8d95-180">Для каждого параметра меню укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="c8d95-180">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="c8d95-181">**Клавиша набора** номера — клавиша на телефонной клавиатуре для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="c8d95-181">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="c8d95-182">**Голосовая** команда — определяет голосовую команду, которую может предоставить вызываемая команда для доступа к этому параметру, если включены голосовые данные.</span><span class="sxs-lookup"><span data-stu-id="c8d95-182">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="c8d95-183">Оно может содержать несколько слов, например "Обслуживание клиентов" или "Операции и причины".</span><span class="sxs-lookup"><span data-stu-id="c8d95-183">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="c8d95-184">**Перенаправить в** место, куда нужно перенаправить звонок при выборе этого параметра.</span><span class="sxs-lookup"><span data-stu-id="c8d95-184">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="c8d95-185">Если вы перенаправляете учетную запись к автозаправщику или очереди вызовов, выберите связанную с ней учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="c8d95-185">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Снимок экрана: параметры набора клавиш](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="c8d95-187">Если вы хотите использовать этого автоотображающего в качестве каталога организации, в области Поиск по каталогу **выберите** Набрать **по имени**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-187">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="c8d95-188">Если вы вжмем этот параметр, звоня люди, которые смогут ввести имя пользователя или ввести его на телефонную клавиатуру.</span><span class="sxs-lookup"><span data-stu-id="c8d95-188">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="c8d95-189">Любой пользователь в Интернете с телефонная система лицензией является подходящим пользователем, и его можно найти с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="c8d95-189">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="c8d95-190">(Вы можете выбрать Вариант Набора номера **по расширению,** но расширение необходимо настроить в Azure Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="c8d95-190">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="c8d95-191">Выбрав параметр поиска по каталогу, **нажмите** кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="c8d95-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8d95-192">Шаг 4. Поток вызовов в нечасовом ></span><span class="sxs-lookup"><span data-stu-id="c8d95-192">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="c8d95-193">Шаг <br> 4. Не по часам</span><span class="sxs-lookup"><span data-stu-id="c8d95-193">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="c8d95-194">Для каждого автозавода можно настроить часы работы.</span><span class="sxs-lookup"><span data-stu-id="c8d95-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="c8d95-195">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="c8d95-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="c8d95-196">В течение дня можно настроить часы работы с перерывом, а все часы, которые не считаются неавтными, считаются неавтными.</span><span class="sxs-lookup"><span data-stu-id="c8d95-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="c8d95-197">Вы можете настроить различные параметры обработки входящих параметров обработки параметров звонка и приветствия в течение часа.</span><span class="sxs-lookup"><span data-stu-id="c8d95-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="c8d95-198">В зависимости от настройки автозаполнения и очередей звонков может потребоваться указать маршрутику звонков только для автозаполнения с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="c8d95-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="c8d95-199">Если вам нужна отдельная маршрутия для вызывающих телефонных вызовов в нечасовом времени, укажите часы работы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="c8d95-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="c8d95-200">Нажмите **кнопку Добавить новое** время, чтобы указать несколько наборов часов для заданного дня, например, чтобы указать перерыв на обед.</span><span class="sxs-lookup"><span data-stu-id="c8d95-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Снимок экрана: параметры дня и времени после окончания дня](../media/auto-attendant-business-hours.png)

<span data-ttu-id="c8d95-202">После того как вы указали часы работы, выберите параметры маршрутизов параметров для неавтных часов.</span><span class="sxs-lookup"><span data-stu-id="c8d95-202">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="c8d95-203">Доступны те же параметры, что и для маршрутичности параметров в часы, указанные в шаге **3 —поток зовов.**</span><span class="sxs-lookup"><span data-stu-id="c8d95-203">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="c8d95-204">Когда **все будет готово,** нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="c8d95-204">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8d95-205">Шаг 5. Праздничный поток зовов ></span><span class="sxs-lookup"><span data-stu-id="c8d95-205">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="c8d95-206">Шаг <br> 5. Праздники</span><span class="sxs-lookup"><span data-stu-id="c8d95-206">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="c8d95-207">В праздники звонки автоответам могут перенанастраиться не так, как в другие дни.</span><span class="sxs-lookup"><span data-stu-id="c8d95-207">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="c8d95-208">(Если вы не хотите использовать другой поток звонка для праздников, вы можете пропустить этот шаг.)</span><span class="sxs-lookup"><span data-stu-id="c8d95-208">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="c8d95-209">Для каждого настроенного праздника ваш автозаводщик может использовать поток зовов.</span><span class="sxs-lookup"><span data-stu-id="c8d95-209">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="c8d95-210">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="c8d95-210">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="c8d95-211">На странице параметров звонка Праздник нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-211">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="c8d95-212">Введите название этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="c8d95-212">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="c8d95-213">В области **Праздник** выберите праздник, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="c8d95-213">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="c8d95-214">Выберите нужный тип приветствия.</span><span class="sxs-lookup"><span data-stu-id="c8d95-214">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры поздравительных и праздничных приветствий](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="c8d95-216">Выберите, хотите ли вы **отключить или** **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="c8d95-216">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="c8d95-217">Если вы выбрали перенаправление, выберите пункт назначения маршрутиации для звонка.</span><span class="sxs-lookup"><span data-stu-id="c8d95-217">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Снимок экрана: параметры действий по праздничным звонкам](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="c8d95-219">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-219">Click **Save**.</span></span>

    <span data-ttu-id="c8d95-220">Повторите эти процедуры для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="c8d95-220">Repeat the procedure as needed for each additional holiday.</span></span>

    ![Снимок экрана: параметры праздников со списком праздников](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="c8d95-222">Когда вы добавите все праздники, нажмите кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="c8d95-222">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8d95-223">Шаг 6. Выбор людей из каталога ></span><span class="sxs-lookup"><span data-stu-id="c8d95-223">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="c8d95-224">Участники каталога, шаг 6 <br></span><span class="sxs-lookup"><span data-stu-id="c8d95-224">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="c8d95-225">Область *набора определяет,* какие пользователи доступны в каталоге, если вызываемая звонок использует по имени или по телефону по расширению.</span><span class="sxs-lookup"><span data-stu-id="c8d95-225">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="c8d95-226">По умолчанию **все пользователи в** Сети включают всех пользователей в организации, которые являются пользователями Online с телефонная система лицензией.</span><span class="sxs-lookup"><span data-stu-id="c8d95-226">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="c8d95-227">Вы можете включить или исключить определенных  пользователей,  выбрав настраиваемую группу пользователей в группе Включить или Исключить и выбрав одну или несколько групп Microsoft 365, списков рассылки или групп безопасности. </span><span class="sxs-lookup"><span data-stu-id="c8d95-227">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="c8d95-228">Например, может потребоваться исключить руководителей организации из каталога набора номера.</span><span class="sxs-lookup"><span data-stu-id="c8d95-228">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="c8d95-229">(Если пользователь есть в обоих списках, он будет исключен из каталога.)</span><span class="sxs-lookup"><span data-stu-id="c8d95-229">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Снимок экрана: область набора номера, включаемая и исключаемая](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="c8d95-231">Для того чтобы новый пользователь указал свое имя в каталоге, может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="c8d95-231">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="c8d95-232">После настройки области набора номера нажмите кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="c8d95-232">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8d95-233">Шаг 7. Назначение учетной записи ресурса ></span><span class="sxs-lookup"><span data-stu-id="c8d95-233">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="c8d95-234">Шаг <br> 7. Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="c8d95-234">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="c8d95-235">У всех автозаводников должна быть связанная учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="c8d95-235">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="c8d95-236">Автослужам первого уровня потребуется по крайней мере одна учетная запись ресурса с связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="c8d95-236">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="c8d95-237">При желании вы можете назначить автослужбу несколько учетных записей ресурсов с отдельным номером службы.</span><span class="sxs-lookup"><span data-stu-id="c8d95-237">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="c8d95-238">Добавление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="c8d95-238">To add a resource account</span></span>

1. <span data-ttu-id="c8d95-239">Нажмите **кнопку** Добавить и найдите учетную запись, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="c8d95-239">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="c8d95-240">Нажмите **кнопку** Добавить и выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-240">Click **Add**, and then click **Add**.</span></span>

    ![Снимок экрана: панель добавления учетных записей для учетных записей ресурсов](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="c8d95-242">Завершив добавление учетных записей службы, нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="c8d95-242">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Снимок экрана: список учетных записей ресурсов с учетной записью ресурса с номером назначенной услуги](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="c8d95-244">В этом случае конфигурация автозаполнеющего будет завершена.</span><span class="sxs-lookup"><span data-stu-id="c8d95-244">This completes the auto attendant configuration.</span></span>

---
