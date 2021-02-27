---
title: Настройка автозавода для Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
- Phone System
description: Узнайте, как настроить и протестировать автоотетаря в Microsoft Teams.
ms.openlocfilehash: deb9bf013136bb8efd9171e5562de5e2ba1b631f
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347870"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="389ca-103">Настройка автозавода</span><span class="sxs-lookup"><span data-stu-id="389ca-103">Set up an auto attendant</span></span>

<span data-ttu-id="389ca-104">Автозаверяющие могут звонить в вашу организацию и переходить в систему меню для связи с нужным отделом, очередью вызовов, человеком или оператором.</span><span class="sxs-lookup"><span data-stu-id="389ca-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="389ca-105">Вы можете создавать автозаводы для своей организации в Центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="389ca-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="389ca-106">Прежде чем выполнять действия, которые вы выполните в [](plan-auto-attendant-call-queue.md#getting-started) этой статье, убедитесь в том, что вы прочитали "План" для автоотетаря [Teams](plan-auto-attendant-call-queue.md) и очередей вызовов, а затем следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="389ca-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="389ca-107">Автоответчики могут перенаправять звонки в одно из следующих мест на основе данных, вводимых вызывающими вызовы: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="389ca-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="389ca-108">**Оператор** — оператор, задавающий для автозавода.</span><span class="sxs-lookup"><span data-stu-id="389ca-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="389ca-109">Определение оператора не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="389ca-109">Defining an operator is optional.</span></span> <span data-ttu-id="389ca-110">Оператор можно определить как любой другой пункт назначения в этом списке.</span><span class="sxs-lookup"><span data-stu-id="389ca-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="389ca-111">**Человек в организации —** это человек в вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="389ca-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="389ca-112">Это может быть пользователь в Сети или пользователь, который использует сервер Skype для бизнеса Server, который является пользователем локальной сети.</span><span class="sxs-lookup"><span data-stu-id="389ca-112">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="389ca-113">**Приложение голосовой** почты — другой автозавод или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="389ca-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="389ca-114">(Выберите учетную запись ресурса, связанную с автостраницой или очередью вызовов, при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="389ca-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="389ca-115">**Голосовая почта** — это почтовый ящик голосовой почты, связанный с группой Microsoft 365, которую вы указали.</span><span class="sxs-lookup"><span data-stu-id="389ca-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="389ca-116">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="389ca-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="389ca-117">(См. [технические сведения о внешнем передаче).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="389ca-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="389ca-118">**Объявление** — воспроизведения звукового файла.</span><span class="sxs-lookup"><span data-stu-id="389ca-118">**Announcement** - Play an audio file.</span></span> <span data-ttu-id="389ca-119">Добавленное вами сообщение с объявлением, сохраненное как звуковое. WAV, . MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="389ca-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="389ca-120">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="389ca-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="389ca-121">Система воспроизводит объявление, а затем возвращается в меню автозапуска.</span><span class="sxs-lookup"><span data-stu-id="389ca-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="389ca-122">**Объявление.** Введите сообщение.</span><span class="sxs-lookup"><span data-stu-id="389ca-122">**Announcement** - Type in a message.</span></span> <span data-ttu-id="389ca-123">Текст, который должна читать система.</span><span class="sxs-lookup"><span data-stu-id="389ca-123">Text you want the system to read.</span></span> <span data-ttu-id="389ca-124">Можно ввести до 1000 символов.</span><span class="sxs-lookup"><span data-stu-id="389ca-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="389ca-125">Система воспроизводит объявление, а затем возвращается в меню автозапуска.</span><span class="sxs-lookup"><span data-stu-id="389ca-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="389ca-126">Вам будет предложено выбрать один из этих параметров на разных этапах настройки автозаказа.</span><span class="sxs-lookup"><span data-stu-id="389ca-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="389ca-127">Чтобы настроить автостраницу, в Центре администрирования Teams развите список **"Голосовая** команда", выберите "Автозапись" и выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="389ca-127">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="389ca-128">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="389ca-128">General info</span></span>

![Снимок экрана: параметры автозавода для имени, оператора, часового пояса, языка и голосового ввода](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="389ca-130">Введите имя автозавода в поле в верхней части окна.</span><span class="sxs-lookup"><span data-stu-id="389ca-130">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="389ca-131">Если вы хотите назначить оператор, укажите место назначения для звонков оператору.</span><span class="sxs-lookup"><span data-stu-id="389ca-131">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="389ca-132">Это необязательно (но рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="389ca-132">This is optional (but recommended).</span></span> <span data-ttu-id="389ca-133">Параметр **"Оператор"** позволяет вызывателям выйти из меню и поговорить с назначенным человеком.</span><span class="sxs-lookup"><span data-stu-id="389ca-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="389ca-134">Укажите часовой пояс для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="389ca-134">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="389ca-135">Часовой пояс используется для расчета рабочих часов, если вы создаете отдельный поток [зовов для нечасов.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="389ca-135">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="389ca-136">Укажите [поддерживаемый язык](create-a-phone-system-auto-attendant-languages.md) для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="389ca-136">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="389ca-137">Этот язык будет использоваться для системных голосовых подсказок.</span><span class="sxs-lookup"><span data-stu-id="389ca-137">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="389ca-138">Выберите, нужно ли включить голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="389ca-138">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="389ca-139">Если этот параметр включен, название каждого параметра меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="389ca-139">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="389ca-140">Например, можно сказать "Один" для выбора параметра меню, назначенного клавише 1, или "Продажи", чтобы выбрать пункт меню "Продажи".</span><span class="sxs-lookup"><span data-stu-id="389ca-140">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="389ca-141">Если на шаге 4 вы выберете язык, который не поддерживает голосовой ввод, этот параметр будет отключен.</span><span class="sxs-lookup"><span data-stu-id="389ca-141">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="389ca-142">Выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="389ca-142">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="389ca-143">Поток вызовов</span><span class="sxs-lookup"><span data-stu-id="389ca-143">Call flow</span></span>

![Снимок экрана: параметры приветствия сообщения](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="389ca-145">Выберите, хотите ли вы воспроизведения приветствия, когда автоответ отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="389ca-145">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="389ca-146">Выбрав **"Воспроизведения звукового** файла",  вы можете добавить записанное приветствие, сохраненное как звуковое сообщение, с помощью кнопки "Отправить файл". WAV, . MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="389ca-146">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="389ca-147">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="389ca-147">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="389ca-148">Если вы **выберете** "Введите приветствие", система прочитает текст, который вы введите (до 1000 символов), когда автостраница отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="389ca-148">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Снимок экрана: параметры маршрутки вызовов](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="389ca-150">Выберите, как вы хотите перена маршрутизовыть звонок.</span><span class="sxs-lookup"><span data-stu-id="389ca-150">Choose how you want to route the call.</span></span>

<span data-ttu-id="389ca-151">Если вы выберете **"Отключить",** автоотетарь повесит звонок.</span><span class="sxs-lookup"><span data-stu-id="389ca-151">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="389ca-152">При выборе пункта **"Перенаправление** звонка" можно выбрать одно из назначений маршрутиации.</span><span class="sxs-lookup"><span data-stu-id="389ca-152">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="389ca-153">Если **выбраны** параметры меню "Воспроизведения", можно  выбрать "Воспроизведения звукового файла" или "Ввести приветствие", а затем выбрать параметры меню и поиск по каталогу. </span><span class="sxs-lookup"><span data-stu-id="389ca-153">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="389ca-154">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="389ca-154">Menu options</span></span>

![Снимок экрана: параметры набора номера](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="389ca-156">Для настройки параметров набора можно назначить 0–9 клавиш на телефонной клавиатуре одному из назначений маршрутки.</span><span class="sxs-lookup"><span data-stu-id="389ca-156">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="389ca-157">(Клавиши \* (Повтор) и (Назад) зарезервированы системой и не \# могут быть перенаписаны.)</span><span class="sxs-lookup"><span data-stu-id="389ca-157">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="389ca-158">Сопоставление ключей не должно быть непрерывным.</span><span class="sxs-lookup"><span data-stu-id="389ca-158">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="389ca-159">Например, можно создать меню с клавишами 0, 1 и 3, относясь к параметрам, хотя они не используются.</span><span class="sxs-lookup"><span data-stu-id="389ca-159">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the two key isn't used.</span></span>

<span data-ttu-id="389ca-160">Если вы его настроили, мы рекомендуем соендуть с оператором ноль.</span><span class="sxs-lookup"><span data-stu-id="389ca-160">We recommend mapping the zero key to the operator if you have configured one.</span></span> <span data-ttu-id="389ca-161">Если оператор не назначен никакой клавише, голосовая команда "Оператор" также отключена.</span><span class="sxs-lookup"><span data-stu-id="389ca-161">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="389ca-162">Для каждого параметра меню укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="389ca-162">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="389ca-163">**Клавиша набора** номера — клавиша на телефонной клавиатуре для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="389ca-163">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="389ca-164">Если голосовой ввод доступен, вызываемая звонок также может говорить на этот номер, чтобы получить доступ к параметру.</span><span class="sxs-lookup"><span data-stu-id="389ca-164">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="389ca-165">**Голосовая** команда — определяет голосовую команду, которую может предоставить вызываемая команда для доступа к этому параметру, если включен голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="389ca-165">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="389ca-166">Оно может содержать несколько слов, например "Обслуживание клиентов" или "Действия и причины".</span><span class="sxs-lookup"><span data-stu-id="389ca-166">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="389ca-167">Например, звонок может нажать 2, сказать "два" или сказать "Продажи", чтобы выбрать параметр, выбранный с двумя клавишами.</span><span class="sxs-lookup"><span data-stu-id="389ca-167">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two key.</span></span> <span data-ttu-id="389ca-168">Этот текст также отрисовывается текстом в речь при запросе на подтверждение службы, например", например "Перена передача звонка в отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="389ca-168">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="389ca-169">**Redirect to** - the call routing destination used when callers choose this option.</span><span class="sxs-lookup"><span data-stu-id="389ca-169">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="389ca-170">Если вы перенаправляете звонок к автоотправлению или очереди вызовов, выберите связанную с ним учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="389ca-170">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="389ca-171">Поиск по каталогу</span><span class="sxs-lookup"><span data-stu-id="389ca-171">Directory search</span></span>

<span data-ttu-id="389ca-172">При назначении клавиш набора номера назначениям рекомендуется выбрать вариант **"Нет"** для поиска **по каталогу.**</span><span class="sxs-lookup"><span data-stu-id="389ca-172">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="389ca-173">Если звоняющий пытается набрать имя или расширение с помощью клавиш, которые назначены определенным назначениям, он может быть неожиданно перенаправлен в назначение до того, как закончит вводить имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="389ca-173">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="389ca-174">Рекомендуется создать отдельный автозавод для поиска по каталогу и создать ссылку на него с помощью клавиши набора номера.</span><span class="sxs-lookup"><span data-stu-id="389ca-174">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="389ca-175">Если вы не назначили наберите клавиши, выберите параметр поиска **по каталогу.**</span><span class="sxs-lookup"><span data-stu-id="389ca-175">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="389ca-176">**Звонок по имени.** Если этот параметр заданной опцией, звоня люди, звонят по имени пользователя или введите его на телефонной клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="389ca-176">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="389ca-177">Любой пользователь в Сети или любой пользователь, использующий локальное приложение Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="389ca-177">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="389ca-178">(На странице "Область набора номера" можно установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="389ca-178">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="389ca-179">**Подключаться по расширению—** если этот параметр не включить, пользователи смогут связываться с пользователями в организации, набрав их расширения для телефона.</span><span class="sxs-lookup"><span data-stu-id="389ca-179">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="389ca-180">Любой пользователь в Сети или любой пользователь, который находится локально с помощью Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью телефонного **набора по расширению.**</span><span class="sxs-lookup"><span data-stu-id="389ca-180">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="389ca-181">(На странице "Область набора номера" можно установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="389ca-181">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="389ca-182">Пользователи, доступ к которые вы хотите сделать доступными для расширения "Набор по", должны иметь расширение, указанное как [](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) часть одного из следующих атрибутов телефонов, определенных в Active Directory или Azure Active Directory (дополнительные сведения см. в дополнительных сведениях о добавлении пользователей по одному или массово).)</span><span class="sxs-lookup"><span data-stu-id="389ca-182">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="389ca-183">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="389ca-183">OfficePhone</span></span>
- <span data-ttu-id="389ca-184">HomePhone</span><span class="sxs-lookup"><span data-stu-id="389ca-184">HomePhone</span></span>
- <span data-ttu-id="389ca-185">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="389ca-185">Mobile/MobilePhone</span></span>
- <span data-ttu-id="389ca-186">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="389ca-186">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="389ca-187">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="389ca-187">OtherTelephone</span></span>

<span data-ttu-id="389ca-188">Необходимый формат для ввода расширения в поле номера телефона пользователя:</span><span class="sxs-lookup"><span data-stu-id="389ca-188">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="389ca-189">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="389ca-189">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="389ca-190">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="389ca-190">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="389ca-191">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="389ca-191">*x\<extension>*</span></span>

- <span data-ttu-id="389ca-192">Пример 1. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="389ca-192">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="389ca-193">Пример 2. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="389ca-193">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="389ca-194">Пример 3. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="389ca-194">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="389ca-195">Расширение можно установить в Центре администрирования [Microsoft 365](https://admin.microsoft.com/) или [Центре администрирования Azure Active Directory.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="389ca-195">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="389ca-196">Для того чтобы изменения были доступны автоотводам и очередям вызовов, может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="389ca-196">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="389ca-197">Если вы хотите использовать  функции  "Набрать по имени" и "Набрать по расширению", назначьте ему клавишу набора для основного автозавода, чтобы связаться с автозаводом, включенным для функции "Набрать по **имени".**</span><span class="sxs-lookup"><span data-stu-id="389ca-197">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="389ca-198">Вы можете назначить клавишу 1 (не связанную с ней буквами), чтобы связаться с автозаводом по набору. </span><span class="sxs-lookup"><span data-stu-id="389ca-198">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="389ca-199">Выбрав параметр поиска по **каталогу, выберите** "Далее". </span><span class="sxs-lookup"><span data-stu-id="389ca-199">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="389ca-200">Поток вызовов в нечасовом времени</span><span class="sxs-lookup"><span data-stu-id="389ca-200">Call flow for after hours</span></span>

![Снимок экрана: параметры дня и времени после окончания дня](media/auto-attendant-business-hours.png)

<span data-ttu-id="389ca-202">Для каждого автозавода можно настроить часы работы.</span><span class="sxs-lookup"><span data-stu-id="389ca-202">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="389ca-203">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="389ca-203">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="389ca-204">Для работы можно установить перерывы в течение дня, а все часы, которые не считаются часами, считаются неавтными.</span><span class="sxs-lookup"><span data-stu-id="389ca-204">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="389ca-205">Вы можете настроить другие параметры обработки входящих параметров обработки параметров и приветствий в течение часа.</span><span class="sxs-lookup"><span data-stu-id="389ca-205">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="389ca-206">В зависимости от настройки автозаполнения и очередей звонков может потребоваться настроить маршрутику звонков только для автозаполнения с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="389ca-206">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="389ca-207">Если вам нужна отдельная маршрутия для вызывающих телефонных вызовов в нечасовом времени, укажите часы работы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="389ca-207">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="389ca-208">Выберите **"Добавить новое время",** чтобы указать несколько часов для заданного дня, например, чтобы указать перерыв на обед.</span><span class="sxs-lookup"><span data-stu-id="389ca-208">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="389ca-209">После того как вы указали часы работы, выберите параметры маршрутизов для неавных часов.</span><span class="sxs-lookup"><span data-stu-id="389ca-209">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="389ca-210">Доступны те же параметры, что и для маршрутизов в часы, которые вы указали выше.</span><span class="sxs-lookup"><span data-stu-id="389ca-210">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="389ca-211">Когда **все будет** готово, выберите "Далее".</span><span class="sxs-lookup"><span data-stu-id="389ca-211">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="389ca-212">Потоки вызовов во время праздников</span><span class="sxs-lookup"><span data-stu-id="389ca-212">Call flows during holidays</span></span>

![Снимок экрана: параметры поздравительных и праздников](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="389ca-214">Для каждого настроенного праздника автозавод может быть настроен поток [звонка.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="389ca-214">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="389ca-215">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="389ca-215">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="389ca-216">На странице параметров звонка "Праздник" выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="389ca-216">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="389ca-217">Введите название этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="389ca-217">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="389ca-218">В **выпадаемом** окнах "Праздники" выберите праздник, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="389ca-218">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="389ca-219">Выберите нужный тип приветствия.</span><span class="sxs-lookup"><span data-stu-id="389ca-219">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры действия по праздничным звонкам](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="389ca-221">Выберите, хотите ли вы **отключить или** **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="389ca-221">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="389ca-222">Если вы перенаправили звонок, выберите пункт назначения маршрутиации для звонка.</span><span class="sxs-lookup"><span data-stu-id="389ca-222">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="389ca-223">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="389ca-223">Select **Save**.</span></span>

![Снимок экрана: параметры праздников со списком праздников](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="389ca-225">Повторите процедуру для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="389ca-225">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="389ca-226">После того как вы добавите все праздники, выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="389ca-226">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="389ca-227">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="389ca-227">Dial scope</span></span>

![Снимок экрана: область набора номера с вариантами "Включить" и "Исключить"](media/auto-attendant-dial-scope.png)

<span data-ttu-id="389ca-229">Область *набора определяет* пользователей, доступных в каталоге, если звоня по имени или по телефону.</span><span class="sxs-lookup"><span data-stu-id="389ca-229">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="389ca-230">По умолчанию **в** число всех сетевых пользователей входят все пользователи в вашей организации, которые являются пользователями Online или находятся на локальном сервере Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="389ca-230">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="389ca-231">Вы можете включить или исключить  определенных  пользователей, выбрав пользовательскую группу в группе "Включить" или **"Исключить"** и выбрав одну или несколько групп Microsoft 365, списки рассылки или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="389ca-231">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="389ca-232">Например, может потребоваться исключить руководителей организации из каталога набора номера.</span><span class="sxs-lookup"><span data-stu-id="389ca-232">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="389ca-233">(Если пользователь есть в обоих списках, он будет исключен из каталога.)</span><span class="sxs-lookup"><span data-stu-id="389ca-233">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="389ca-234">Для того чтобы новый пользователь указал свое имя в каталоге, может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="389ca-234">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="389ca-235">После настройки области набора номера выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="389ca-235">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="389ca-236">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="389ca-236">Resource accounts</span></span>

<span data-ttu-id="389ca-237">У всех автосуммников должна быть связанная учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="389ca-237">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="389ca-238">Автослужбу первого уровня потребуется по крайней мере одна учетная запись ресурса с связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="389ca-238">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="389ca-239">При желании вы можете назначить автозаводу несколько учетных записей ресурсов с отдельным номером службы.</span><span class="sxs-lookup"><span data-stu-id="389ca-239">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Снимок экрана: панель добавления учетных записей для учетной записи ресурса](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="389ca-241">Чтобы добавить учетную  запись ресурса, выберите "Добавить учетную запись" и на выберите учетную запись, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="389ca-241">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="389ca-242">Выберите **"Добавить",** а затем выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="389ca-242">Select **Add**, and then select **Add**.</span></span>

![Снимок экрана: список учетных записей ресурсов с учетной записью ресурса с номером назначенной услуги](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="389ca-244">Завершив добавление учетных записей  службы, выберите "Отправить", чтобы завершить настройку автоотчета.</span><span class="sxs-lookup"><span data-stu-id="389ca-244">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="389ca-245">Передача внешних номеров телефонов — технические сведения</span><span class="sxs-lookup"><span data-stu-id="389ca-245">External phone number transfers - technical details</span></span>

<span data-ttu-id="389ca-246">Чтобы разрешить [автоответам](plan-auto-attendant-call-queue.md#prerequisites) переводить звонки внешним пользователям, обратитесь к необходимым условиям.</span><span class="sxs-lookup"><span data-stu-id="389ca-246">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="389ca-247">В дополнение:</span><span class="sxs-lookup"><span data-stu-id="389ca-247">In addition:</span></span>

- <span data-ttu-id="389ca-248">Для учетной записи ресурса с номером плана звонков номер телефона для внешнего переноса должен быть введен в формате E.164 (+[код страны][код города][номер телефона]). [](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="389ca-248">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="389ca-249">Для учетной записи ресурса с прямым маршрутным номером внешний [](direct-routing-connect-the-sbc.md) формат номера телефона для передачи зависит от параметров граничного контроллера сеанса.</span><span class="sxs-lookup"><span data-stu-id="389ca-249">For a resource account with a Direct Routing number, the external transfer phone number format is dependent on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="389ca-250">Отображаемая исходящие телефонные номера определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="389ca-250">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="389ca-251">Для номеров планов звонков отображается исходный номер телефона звоня.</span><span class="sxs-lookup"><span data-stu-id="389ca-251">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="389ca-252">Для номеров прямой маршрутификации количество отправленных номеров основано на параметре P-Утвердилось-Identity (PAI) на SBC:</span><span class="sxs-lookup"><span data-stu-id="389ca-252">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="389ca-253">Если установлено отключение, отображается исходный номер телефона звоня.</span><span class="sxs-lookup"><span data-stu-id="389ca-253">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="389ca-254">Это значение задается по умолчанию и рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="389ca-254">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="389ca-255">Если установлено "Включено", отображается номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="389ca-255">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="389ca-256">В гибридной среде Skype для бизнеса создайте нового локального пользователя с настроенной для переадстройки звонков номером ПС.</span><span class="sxs-lookup"><span data-stu-id="389ca-256">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="389ca-257">Пользователю должно быть включено Корпоративная голосовая связь и ему назначена голосовая политика.</span><span class="sxs-lookup"><span data-stu-id="389ca-257">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="389ca-258">Дополнительные узнать см. в подзагонке "Перенастройка вызовов [автостраницы на ДНР".](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="389ca-258">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="389ca-259">Создание автозавода с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="389ca-259">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="389ca-260">Вы также можете использовать PowerShell для создания и создания автоотетарей.</span><span class="sxs-lookup"><span data-stu-id="389ca-260">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="389ca-261">Ниже статисты, необходимые для управления автозаправщиком.</span><span class="sxs-lookup"><span data-stu-id="389ca-261">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="389ca-262">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="389ca-262">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="389ca-263">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="389ca-263">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="389ca-264">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="389ca-264">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="389ca-265">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="389ca-265">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="389ca-266">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="389ca-266">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="389ca-267">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="389ca-267">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="389ca-268">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="389ca-268">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="389ca-269">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="389ca-269">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="389ca-270">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="389ca-270">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="389ca-271">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="389ca-271">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="389ca-272">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="389ca-272">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="389ca-273">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="389ca-273">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="389ca-274">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="389ca-274">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="389ca-275">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="389ca-275">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="389ca-276">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="389ca-276">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="389ca-277">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="389ca-277">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="389ca-278">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="389ca-278">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="389ca-279">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="389ca-279">Related topics</span></span>

[<span data-ttu-id="389ca-280">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="389ca-280">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="389ca-281">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="389ca-281">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="389ca-282">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="389ca-282">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="389ca-283">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="389ca-283">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
