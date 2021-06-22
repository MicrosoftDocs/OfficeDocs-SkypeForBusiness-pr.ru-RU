---
title: Настройка автосекретаря для Microsoft Teams
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
description: Узнайте, как настраивать и тестировать автосекретарей для крупных организаций в Microsoft Teams.
ms.openlocfilehash: cc4d0de8fd1d6c643f23b6e8215f0f7a343b2a8f
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777809"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="4f31f-103">Настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="4f31f-103">Set up an auto attendant</span></span>

<span data-ttu-id="4f31f-104">Автосекретари позволяют людям звонить в вашу организацию и перемещаться в системе меню для связи с нужным отделом, очередью вызовов, сотрудником или оператором.</span><span class="sxs-lookup"><span data-stu-id="4f31f-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="4f31f-105">Вы можете создавать автосекретарей для своей организации в Центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f31f-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

> [!TIP]
> <span data-ttu-id="4f31f-106">Эта статья предназначена для крупных организаций.</span><span class="sxs-lookup"><span data-stu-id="4f31f-106">This article is for large organizations.</span></span> <span data-ttu-id="4f31f-107">Если вы относитесь к малому бизнесу, см. [руководство по настройке автосекретаря для малого бизнеса](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb).</span><span class="sxs-lookup"><span data-stu-id="4f31f-107">If your organization is a small business, read [Set up an auto attendant - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) instead.</span></span>

<span data-ttu-id="4f31f-108">См. статью [Планирование автосекретарей и очередей вызовов в Teams](plan-auto-attendant-call-queue.md), а затем [инструкции по началу работы](plan-auto-attendant-call-queue.md#getting-started) до выполнения процедур, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4f31f-108">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="4f31f-109">Автосекретари могут направлять вызовы на основе ввода вызывающих абонентов в один из следующих целевых объектов: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="4f31f-109">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="4f31f-110">**Оператор** — оператор, определенный для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4f31f-110">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="4f31f-111">Определение оператора является необязательным.</span><span class="sxs-lookup"><span data-stu-id="4f31f-111">Defining an operator is optional.</span></span> <span data-ttu-id="4f31f-112">Оператора можно определить как любой из других целевых объектов в этом списке.</span><span class="sxs-lookup"><span data-stu-id="4f31f-112">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="4f31f-113">**Человек в организации** — сотрудник в вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="4f31f-113">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="4f31f-114">Этот сотрудник может быть онлайн-пользователем или локальным пользователем, применяющим Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f31f-114">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="4f31f-115">**Голосовое приложение** — другой автосекретарь или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="4f31f-115">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="4f31f-116">(При выборе этого целевого объекта выберите учетную запись ресурса, связанную с автосекретарем или очередью вызовов.)</span><span class="sxs-lookup"><span data-stu-id="4f31f-116">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="4f31f-117">**Голосовая почта** — почтовый ящик голосовой почты, связанный с группой Microsoft 365, которую вы указали.</span><span class="sxs-lookup"><span data-stu-id="4f31f-117">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span> <span data-ttu-id="4f31f-118">Вы можете выбрать, требуются ли расшифровки голосовой почты и системное приглашение "Оставьте сообщение после сигнала"</span><span class="sxs-lookup"><span data-stu-id="4f31f-118">You can choose if you want voicemail transcriptions and the "Please leave a message after the tone."</span></span> <span data-ttu-id="4f31f-119">.</span><span class="sxs-lookup"><span data-stu-id="4f31f-119">system prompt.</span></span>
- <span data-ttu-id="4f31f-120">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="4f31f-120">**External phone number** - any phone number.</span></span> <span data-ttu-id="4f31f-121">(См. [технические сведения о внешней передаче](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details).)</span><span class="sxs-lookup"><span data-stu-id="4f31f-121">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="4f31f-122">**Объявление (звуковой файл)** — воспроизведение звукового файла.</span><span class="sxs-lookup"><span data-stu-id="4f31f-122">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="4f31f-123">Отправленное записанное объявление, сохраненное как звук в формате WAV, MP3 или WMA.</span><span class="sxs-lookup"><span data-stu-id="4f31f-123">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="4f31f-124">Размер записи не должен превышать 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="4f31f-124">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="4f31f-125">Система воспроизводит объявление, а затем возвращается в меню автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4f31f-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="4f31f-126">**Объявление (введенное)** — введите сообщение.</span><span class="sxs-lookup"><span data-stu-id="4f31f-126">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="4f31f-127">Текст, который должна прочитать система.</span><span class="sxs-lookup"><span data-stu-id="4f31f-127">Text you want the system to read.</span></span> <span data-ttu-id="4f31f-128">Вы можете ввести не более 1000 символов.</span><span class="sxs-lookup"><span data-stu-id="4f31f-128">You can enter up to 1000 characters.</span></span> <span data-ttu-id="4f31f-129">Система воспроизводит объявление, а затем возвращается в меню автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4f31f-129">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="4f31f-130">Вам будет предложено выбрать один из этих вариантов на разных этапах настройки автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4f31f-130">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="4f31f-131">Чтобы настроить автосекретаря в Центре администрирования Teams разверните **Голосовая связь**, выберите **Автосекретари** и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-131">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="4f31f-132">Видеодемонстрация</span><span class="sxs-lookup"><span data-stu-id="4f31f-132">Video demonstration</span></span>

<span data-ttu-id="4f31f-133">В этом видео показан базовый пример создания автосекретаря в Teams.</span><span class="sxs-lookup"><span data-stu-id="4f31f-133">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a><span data-ttu-id="4f31f-134">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="4f31f-134">General info</span></span>

![Снимок экрана: параметры автосекретаря для названия, оператора, часового пояса, языка и речевого ввода](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="4f31f-136">Введите название автосекретаря в поле в верхней части окна.</span><span class="sxs-lookup"><span data-stu-id="4f31f-136">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="4f31f-137">Чтобы назначить оператора, укажите оператора в качестве целевого объекта для звонков.</span><span class="sxs-lookup"><span data-stu-id="4f31f-137">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="4f31f-138">Это назначение необязательно (но рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="4f31f-138">This designation is optional (but recommended).</span></span> <span data-ttu-id="4f31f-139">Установите параметр **Оператор**, чтобы разрешить вызывающим выходить из меню и общаться с назначенным человеком.</span><span class="sxs-lookup"><span data-stu-id="4f31f-139">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="4f31f-140">Укажите часовой пояс для этого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4f31f-140">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="4f31f-141">Часовой пояс используется для вычисления рабочего времени, если вы [создаете отдельный поток звонков для нерабочего времени](#call-flow-for-after-hours).</span><span class="sxs-lookup"><span data-stu-id="4f31f-141">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="4f31f-142">Укажите [поддерживаемый язык](create-a-phone-system-auto-attendant-languages.md) для этого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4f31f-142">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="4f31f-143">Это язык, который будет использоваться для системных голосовых подсказок.</span><span class="sxs-lookup"><span data-stu-id="4f31f-143">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="4f31f-144">Выберите, нужно ли включить речевой ввод.</span><span class="sxs-lookup"><span data-stu-id="4f31f-144">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="4f31f-145">Если этот параметр включен, название каждого параметра меню становится ключевым словом для распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="4f31f-145">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="4f31f-146">Например, вызывающий абонент может произнести "Один" для выбора параметра меню, назначенного клавише 1, или "Отдел продаж" для перехода к одноименному параметру меню.</span><span class="sxs-lookup"><span data-stu-id="4f31f-146">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

   > [!NOTE]
   > <span data-ttu-id="4f31f-147">Если на шаге 4 выбран язык, не поддерживающий речевой ввод, этот параметр будет отключен.</span><span class="sxs-lookup"><span data-stu-id="4f31f-147">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="4f31f-148">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-148">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="4f31f-149">Поток звонков</span><span class="sxs-lookup"><span data-stu-id="4f31f-149">Call flow</span></span>

![Снимок экрана: параметры приветственного сообщения](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="4f31f-151">Выберите, нужно ли воспроизводить приветственное сообщение, когда автосекретарь отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="4f31f-151">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="4f31f-152">Если вы выберите **Воспроизводить звуковой файл**, вы сможете использовать кнопку **Загрузить файл** для отправки записанного приветственного сообщения, сохраненного как звуковой файл в формате WAV, MP3 или WMA.</span><span class="sxs-lookup"><span data-stu-id="4f31f-152">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="4f31f-153">Размер записи не должен превышать 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="4f31f-153">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="4f31f-154">Если вы выберите **Введите приветствие**, система будет читать текст, который вы ввели (до 1000 символов), когда автосекретарь отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="4f31f-154">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Снимок экрана: параметры маршрутизации звонков](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="4f31f-156">Выберите способ маршрутизации звонка.</span><span class="sxs-lookup"><span data-stu-id="4f31f-156">Choose how you want to route the call.</span></span>

<span data-ttu-id="4f31f-157">Если вы выберите **Отключить**, автосекретарь завершит звонок.</span><span class="sxs-lookup"><span data-stu-id="4f31f-157">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="4f31f-158">Если выбрать **Перенаправить звонок**, вы сможете выбрать один из целевых объектов для маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="4f31f-158">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="4f31f-159">Если выбрать **Прослушать пункты меню**, вы сможете выбрать вариант **Воспроизводить звуковой файл** или **Введите приветствие**, а затем указать один из параметров меню и поиск в каталоге.</span><span class="sxs-lookup"><span data-stu-id="4f31f-159">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="4f31f-160">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="4f31f-160">Menu options</span></span>

![Снимок экрана: параметры клавиш набора](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="4f31f-162">В качестве параметров набора назначьте клавиши 0–9 на клавиатуре телефона одному из целевых объектов маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="4f31f-162">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="4f31f-163">(Клавиши \* (повтор) и \# (назад) зарезервированы системой и не могут быть переназначены.)</span><span class="sxs-lookup"><span data-stu-id="4f31f-163">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="4f31f-164">Сопоставления клавиш не должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="4f31f-164">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="4f31f-165">Можно создать меню с клавишами 0, 1 и 3, соответствующими определенным вариантам, при этом клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="4f31f-165">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="4f31f-166">Рекомендуется сопоставить клавишу "ноль" с оператором, если он настроен.</span><span class="sxs-lookup"><span data-stu-id="4f31f-166">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="4f31f-167">Если оператору не присвоена какая-либо клавиша, голосовая команда "Оператор" также отключена.</span><span class="sxs-lookup"><span data-stu-id="4f31f-167">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="4f31f-168">Для каждого параметра меню укажите следующие настройки.</span><span class="sxs-lookup"><span data-stu-id="4f31f-168">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="4f31f-169">**Клавиша набора** — клавиша на клавиатуре телефона для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="4f31f-169">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="4f31f-170">Если доступен речевой ввод, вызывающие абоненты также могут произнести этот номер для доступа к параметру.</span><span class="sxs-lookup"><span data-stu-id="4f31f-170">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="4f31f-171">**Голосовая команда** — определяет голосовую команду, которую вызывающий может произнести, чтобы получить доступ к этому параметру, если включен речевой ввод.</span><span class="sxs-lookup"><span data-stu-id="4f31f-171">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="4f31f-172">Она может содержать несколько слов, например "Служба поддержки клиентов" или "Отдел эксплуатации".</span><span class="sxs-lookup"><span data-stu-id="4f31f-172">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="4f31f-173">Например, вызывающий может нажать 2, сказать "два" или произнести "Отдел продаж", чтобы выбрать параметр, сопоставленный с клавишей "два".</span><span class="sxs-lookup"><span data-stu-id="4f31f-173">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="4f31f-174">Этот текст также воспроизводится функцией преобразования текста в речь для запроса подтверждения службы. Например, "Перенаправление вашего звонка в отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="4f31f-174">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="4f31f-175">**Кому перенаправить** — целевой объект маршрутизации звонков, используемый при выборе этого параметра вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f31f-175">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="4f31f-176">Если вы используете перенаправление к автосекретарю или в очередь вызовов, выберите соответствующую связанную учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="4f31f-176">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="4f31f-177">Поиск в каталоге</span><span class="sxs-lookup"><span data-stu-id="4f31f-177">Directory search</span></span>

<span data-ttu-id="4f31f-178">Если вы назначаете клавиши набора целевым объектам, рекомендуется выбрать **Нет** для параметра **Поиск в каталоге**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-178">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="4f31f-179">Если вызывающий пытается набрать имя или дополнительный номер с помощью клавиш, которые назначены определенным целевым объектам, он может быть неожиданно перенаправлен в целевой объект до завершения ввода имени или расширения.</span><span class="sxs-lookup"><span data-stu-id="4f31f-179">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="4f31f-180">Рекомендуется создать отдельного автосекретаря для поиска в каталоге и связать с ним основного автосекретаря с помощью клавиши набора.</span><span class="sxs-lookup"><span data-stu-id="4f31f-180">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="4f31f-181">Если вы не назначили клавиши набора, выберите параметр для настройки **Поиск в каталоге**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-181">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="4f31f-182">**Набор номера по имени**. Если включить этот параметр, вызывающие смогут произнести имя пользователя или ввести его на клавиатуре телефона.</span><span class="sxs-lookup"><span data-stu-id="4f31f-182">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="4f31f-183">Любой пользователь из Интернета или любой локальный пользователь, применяющий Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="4f31f-183">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="4f31f-184">(Вы можете указать, кто будет включен в каталог, на странице [Область набора](#dial-scope).)</span><span class="sxs-lookup"><span data-stu-id="4f31f-184">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="4f31f-185">**Набор дополнительного номера**. Если этот параметр включен, вызывающие могут связываться с пользователями в вашей организации путем набора их дополнительного номера.</span><span class="sxs-lookup"><span data-stu-id="4f31f-185">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="4f31f-186">Любой пользователь из Интернета или любой локальный пользователь, применяющий Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью **набора дополнительного номера**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-186">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="4f31f-187">(Вы можете указать, кто будет включен в каталог, на странице [Область набора](#dial-scope).)</span><span class="sxs-lookup"><span data-stu-id="4f31f-187">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="4f31f-188">Для пользователей, которых нужно сделать доступными с помощью функции "Набор дополнительного номера", должен быть указан дополнительный номер в рамках одного из следующих телефонных атрибутов, определенных в Active Directory или Azure Active Directory (дополнительные сведения см. в статье [Добавление пользователей по одному или массово](/microsoft-365/admin/add-users/add-users)).</span><span class="sxs-lookup"><span data-stu-id="4f31f-188">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="4f31f-189">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="4f31f-189">OfficePhone</span></span>
- <span data-ttu-id="4f31f-190">HomePhone</span><span class="sxs-lookup"><span data-stu-id="4f31f-190">HomePhone</span></span>
- <span data-ttu-id="4f31f-191">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="4f31f-191">Mobile/MobilePhone</span></span>
- <span data-ttu-id="4f31f-192">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="4f31f-192">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="4f31f-193">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="4f31f-193">OtherTelephone</span></span>

<span data-ttu-id="4f31f-194">Для ввода дополнительного номера в поле номера телефона пользователя может требоваться один из следующих форматов.</span><span class="sxs-lookup"><span data-stu-id="4f31f-194">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="4f31f-195">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="4f31f-195">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="4f31f-196">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="4f31f-196">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="4f31f-197">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="4f31f-197">*x\<extension>*</span></span>

- <span data-ttu-id="4f31f-198">Пример 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="4f31f-198">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="4f31f-199">Пример 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="4f31f-199">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="4f31f-200">Пример 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="4f31f-200">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="4f31f-201">Вы также можете настроить дополнительный номер в [Центре администрирования Microsoft 365](https://admin.microsoft.com/) или [Центре администрирования Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="4f31f-201">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="4f31f-202">Может пройти до 12 часов, прежде чем изменения станут доступны автосекретарям и очередям вызовов.</span><span class="sxs-lookup"><span data-stu-id="4f31f-202">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="4f31f-203">Если вы хотите использовать как **Набор номера по имени**, так и **Набор дополнительного имени**, вы можете назначить клавишу набора для основного автосекретаря, чтобы связываться с автосекретарем, включенным для функции **Набор по имени**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-203">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="4f31f-204">В этом автосекретаре можно назначить клавишу 1 (с которой не связаны буквы), чтобы связываться с автосекретарем путем **набора дополнительного номера**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-204">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="4f31f-205">Выбрав параметр **Поиск в каталоге**, нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-205">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="4f31f-206">Поток звонков в нерабочее время</span><span class="sxs-lookup"><span data-stu-id="4f31f-206">Call flow for after hours</span></span>

![Снимок экрана: параметры дня и часов для нерабочего времени](media/auto-attendant-business-hours.png)

<span data-ttu-id="4f31f-p126">Рабочие часы можно настроить отдельно для каждого автосекретаря. Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней. Вы можете настроить перерывы в течение рабочего дня. Все часы, которые не настроены как рабочие, считаются нерабочими. Вы можете настроить различные правила обработки входящих звонков и приветствия для нерабочего времени.</span><span class="sxs-lookup"><span data-stu-id="4f31f-p126">Business hours can be set for each auto attendant. If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default. Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours. You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="4f31f-212">В зависимости от того, как вы настроили автосекретарей и очереди вызовов, вам может потребоваться только указать маршрутизацию звонков в нерабочее время для автосекретарей с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="4f31f-212">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="4f31f-213">Если вам нужна отдельная маршрутизация звонков для вызывающих абонентов в нерабочее время, укажите свои часы работы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="4f31f-213">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="4f31f-214">Выберите **Добавить новое время**, чтобы указать несколько наборов часов для определенного дня, например, чтобы указать перерыв на обед.</span><span class="sxs-lookup"><span data-stu-id="4f31f-214">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="4f31f-215">Указав рабочие часы, выберите параметры маршрутизации звонков для нерабочего времени.</span><span class="sxs-lookup"><span data-stu-id="4f31f-215">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="4f31f-216">Доступны те же параметры, что и для маршрутизации звонков в рабочее время, указанные выше.</span><span class="sxs-lookup"><span data-stu-id="4f31f-216">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="4f31f-217">После завершения нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-217">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="4f31f-218">Потоки звонков в выходные</span><span class="sxs-lookup"><span data-stu-id="4f31f-218">Call flows during holidays</span></span>

![Снимок экрана: выходные и параметры приветствия в выходные](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="4f31f-220">У вашего автосекретаря может быть поток звонков для каждого [настроенного вами выходного](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4f31f-220">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="4f31f-221">Вы можете добавить до 20 запланированных выходных для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4f31f-221">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="4f31f-222">На странице "Настройки звонков в выходные" нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-222">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="4f31f-223">Введите имя этого выходного.</span><span class="sxs-lookup"><span data-stu-id="4f31f-223">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="4f31f-224">В раскрывающемся списке **Выходной** выберите праздник, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="4f31f-224">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="4f31f-225">Выберите тип приветствия, который нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="4f31f-225">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры действий для звонков в выходные](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="4f31f-227">Выберите вариант **Отключить** или **Перенаправить звонок**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-227">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="4f31f-228">Если вы выбрали перенаправление, выберите целевой объект маршрутизации звонка.</span><span class="sxs-lookup"><span data-stu-id="4f31f-228">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="4f31f-229">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-229">Select **Save**.</span></span>

![Снимок экрана: параметры выходных со списком праздников](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="4f31f-231">При необходимости повторите эту процедуру для каждого дополнительного выходного.</span><span class="sxs-lookup"><span data-stu-id="4f31f-231">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="4f31f-232">После добавления всех выходных нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-232">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="4f31f-233">Область набора</span><span class="sxs-lookup"><span data-stu-id="4f31f-233">Dial scope</span></span>

![Снимок экрана: параметры включения и исключения области набора](media/auto-attendant-dial-scope.png)

<span data-ttu-id="4f31f-235">*Область набора* определяет, какие пользователи доступны в каталоге, если вызывающий абонент использует функцию набора по имени или набора по дополнительному номеру.</span><span class="sxs-lookup"><span data-stu-id="4f31f-235">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="4f31f-236">Значение по умолчанию **Все пользователи в сети** включает всех пользователей вашей организации, которые находятся в сети или в локальной среде с использованием Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f31f-236">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="4f31f-237">Вы можете включить или исключить определенных пользователей, выбрав **Настраиваемая группа пользователей** в разделе **Включить** или **Исключить** и указав одну или несколько групп Microsoft 365, списков рассылки или групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="4f31f-237">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="4f31f-238">Например, может потребоваться исключить руководителей организации из каталога набора номера.</span><span class="sxs-lookup"><span data-stu-id="4f31f-238">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="4f31f-239">(Если пользователь находится в обоих списках, он будет исключен из каталога.)</span><span class="sxs-lookup"><span data-stu-id="4f31f-239">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="4f31f-240">Может потребоваться до 36 часов, чтобы имя нового пользователя появилось в каталоге.</span><span class="sxs-lookup"><span data-stu-id="4f31f-240">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="4f31f-241">После настройки области набора выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-241">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="4f31f-242">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="4f31f-242">Resource accounts</span></span>

<span data-ttu-id="4f31f-243">У всех автосекретарей должны быть связанные учетные записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="4f31f-243">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="4f31f-244">У автосекретарей первого уровня должна быть как минимум одна учетная запись ресурса со связанным служебным номером.</span><span class="sxs-lookup"><span data-stu-id="4f31f-244">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="4f31f-245">При желании вы можете назначить автосекретарю несколько учетных записей ресурсов, у каждой из которых будет отдельный служебный номер.</span><span class="sxs-lookup"><span data-stu-id="4f31f-245">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Снимок экрана: панель добавления учетной записи ресурса](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="4f31f-247">Чтобы добавить учетную запись ресурса, выберите **Добавить учетную запись** и найдите учетную запись, которую нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="4f31f-247">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="4f31f-248">Затем нажмите **Добавить** и снова — **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-248">Select **Add**, and then select **Add**.</span></span>

![Снимок экрана: список учетных записей ресурсов, в котором показана учетная запись ресурса с назначенным служебным номером](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="4f31f-250">Завершив добавление учетных записей служб, выберите **Отправить** для завершения настройки автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4f31f-250">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="4f31f-251">Передача внешних номеров телефонов — технические сведения</span><span class="sxs-lookup"><span data-stu-id="4f31f-251">External phone number transfers - technical details</span></span>

<span data-ttu-id="4f31f-252">Обратитесь к разделу [Предварительные требования](plan-auto-attendant-call-queue.md#prerequisites), чтобы разрешить автосекретарям внешнюю передачу звонков.</span><span class="sxs-lookup"><span data-stu-id="4f31f-252">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="4f31f-253">Кроме того:</span><span class="sxs-lookup"><span data-stu-id="4f31f-253">In addition:</span></span>

- <span data-ttu-id="4f31f-254">Для учетной записи ресурса с [лицензией на тарифный план](calling-plans-for-office-365.md) номер телефона для внешней передачи должен быть введен в формате E.164 (+[код страны или региона][код города][номер телефона]).</span><span class="sxs-lookup"><span data-stu-id="4f31f-254">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="4f31f-255">Для учетной записи ресурса с лицензией на телефонную систему и политикой прямой маршрутизации голосовой связи по сети формат номера телефона для внешней передачи зависит от параметров [пограничного контроллера сеансов (SBC)](direct-routing-connect-the-sbc.md).</span><span class="sxs-lookup"><span data-stu-id="4f31f-255">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="4f31f-256">Отображаемый исходящий номер телефона определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4f31f-256">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="4f31f-257">Для номеров тарифного плана отображается исходный номер телефона звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f31f-257">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="4f31f-258">Для номеров прямой маршрутизации отправляемый номер основан на параметре P-Asserted-Identity (PAI) в SBC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4f31f-258">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="4f31f-259">Если установлено значение "Отключено", отображается исходный номер телефона звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f31f-259">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="4f31f-260">Это параметр по умолчанию (рекомендуемый).</span><span class="sxs-lookup"><span data-stu-id="4f31f-260">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="4f31f-261">Если установлено значение "Включено", отображается номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="4f31f-261">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="4f31f-262">В гибридной среде Skype для бизнеса для передачи звонка автосекретаря в ТСОП создайте нового локального пользователя с переадресацией звонков на номер ТСОП.</span><span class="sxs-lookup"><span data-stu-id="4f31f-262">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="4f31f-263">Для пользователя должна быть включена корпоративная голосовая связь и назначена политика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4f31f-263">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="4f31f-264">Дополнительные сведения см. в разделе [Передача звонка автосекретаря в ТСОП](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="4f31f-264">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="4f31f-265">Создание автосекретаря с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f31f-265">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="4f31f-266">Вы также можете использовать PowerShell для создания и настройки автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="4f31f-266">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="4f31f-267">Далее перечислены командлеты, необходимые для управления автосекретарем:</span><span class="sxs-lookup"><span data-stu-id="4f31f-267">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="4f31f-268">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="4f31f-268">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="4f31f-269">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="4f31f-269">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="4f31f-270">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="4f31f-270">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="4f31f-271">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="4f31f-271">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="4f31f-272">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="4f31f-272">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="4f31f-273">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="4f31f-273">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="4f31f-274">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="4f31f-274">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="4f31f-275">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="4f31f-275">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="4f31f-276">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="4f31f-276">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="4f31f-277">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="4f31f-277">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="4f31f-278">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="4f31f-278">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="4f31f-279">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="4f31f-279">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="4f31f-280">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="4f31f-280">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="4f31f-281">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="4f31f-281">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="4f31f-282">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="4f31f-282">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="4f31f-283">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="4f31f-283">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="4f31f-284">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="4f31f-284">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="4f31f-285">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4f31f-285">Related topics</span></span>

[<span data-ttu-id="4f31f-286">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="4f31f-286">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="4f31f-287">Получение служебных номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="4f31f-287">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="4f31f-288">Доступность аудиоконференций и тарифных планов в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="4f31f-288">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="4f31f-289">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4f31f-289">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
