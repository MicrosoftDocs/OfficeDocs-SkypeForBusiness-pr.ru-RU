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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Сведения о настройке и тестировании автоматических ассистентов для Microsoft Teams.
ms.openlocfilehash: 2cb796db37f40025dc7a78123da729fd5812bbbb
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48220288"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="8dd1f-103">Настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="8dd1f-103">Set up an auto attendant</span></span>

<span data-ttu-id="8dd1f-104">С помощью автосекретарей пользователи могут позвонить в вашу организацию и переходить в систему меню для общения с нужным Отделом, очередью звонков, лицом или оператором.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="8dd1f-105">Вы можете создавать автоматические ассистенты в Организации с помощью центра администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="8dd1f-106">Перед выполнением процедур, описанных в этой статье, убедитесь, что у вас есть план прочтения [для команд автосекретаря и очереди звонков](plan-auto-attendant-call-queue.md) , а затем следуйте [инструкциям по началу работы](plan-auto-attendant-call-queue.md#getting-started) .</span><span class="sxs-lookup"><span data-stu-id="8dd1f-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="8dd1f-107">Автоматические ассистенты могут направлять звонки в соответствии с входными данными для вызывающего абонента в одном из указанных ниже мест.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations:</span></span>

- <span data-ttu-id="8dd1f-108">**Сотрудник Организации** — сотрудник вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="8dd1f-109">Это может быть пользователь в сети или пользователь, размещенный в локальной среде, с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="8dd1f-110">**Голосовое приложение** — другой автоматический секретарь или очередь звонков.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="8dd1f-111">(Выберите учетную запись ресурса, связанную с автосекретарем или очередью звонков при выборе этого пункта назначения.)</span><span class="sxs-lookup"><span data-stu-id="8dd1f-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="8dd1f-112">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="8dd1f-113">(Дополнительные [технические сведения о внешних передачах](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="8dd1f-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="8dd1f-114">Голосовая **почта** — голосовой почтовый ящик, связанный с указанными вами группами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="8dd1f-115">**Operator** — оператор, определенный для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="8dd1f-116">Определение оператора является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-116">Defining an operator is optional.</span></span> <span data-ttu-id="8dd1f-117">Этот оператор можно задать в качестве любого из других мест в этом списке.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="8dd1f-118">При настройке автосекретаря вам будет предложено выбрать один из этих вариантов на разных этапах.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="8dd1f-119">Чтобы настроить автосекретарь, в центре администрирования Teams разверните элемент **Голосовая связь**, выберите **автосекретарьs**и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="8dd1f-120">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="8dd1f-120">General info</span></span>

![](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="8dd1f-121">Введите имя автосекретаря в поле в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-121">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="8dd1f-122">Если вы хотите назначить оператор, укажите назначение для вызова оператора.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-122">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="8dd1f-123">Это необязательно (но рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="8dd1f-123">This is optional (but recommended).</span></span> <span data-ttu-id="8dd1f-124">Вы можете настроить параметр **оператора** , чтобы разрешить звонящим выйти из меню и поговорить с определенным человеком.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-124">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="8dd1f-125">Укажите часовой пояс для этого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-125">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="8dd1f-126">Часовой пояс используется для вычисления рабочих часов, если вы [создаете отдельный поток звонков в течение часа](#call-flow-for-after-hours).</span><span class="sxs-lookup"><span data-stu-id="8dd1f-126">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="8dd1f-127">Укажите язык для этого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-127">Specify a language for this auto attendant.</span></span> <span data-ttu-id="8dd1f-128">Это язык, который будет использоваться для создаваемых системой голосовых запросов.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-128">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="8dd1f-129">Выберите этот параметр, если вы хотите включить голосовые данные.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-129">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="8dd1f-130">Если этот параметр включен, имя каждого пункта меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-130">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="8dd1f-131">Например, вызывающие объекты могут сказать "один", чтобы выбрать параметр меню, сопоставленный с клавишей 1, или указать "продажи", чтобы выбрать пункт меню "продажи".</span><span class="sxs-lookup"><span data-stu-id="8dd1f-131">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="8dd1f-132">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-132">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="8dd1f-133">Поток звонков</span><span class="sxs-lookup"><span data-stu-id="8dd1f-133">Call flow</span></span>

![](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="8dd1f-134">Укажите, нужно ли воспроизводить приветствие, когда автосекретарь отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-134">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="8dd1f-135">Если выбрать команду **Воспроизвести звуковой файл** , вы можете использовать кнопку **Добавить файл** , чтобы отправить записанное приветствие, сохраненное в виде звукового файла. WAV,. MP3 или. Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-135">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="8dd1f-136">Размер записи не может превышать 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-136">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="8dd1f-137">Если вы выбрали команду **Введите сообщение приветствия** , система будет прочитать текст, который вы вводите (до 1000 символов), когда автосекретарь ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-137">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="8dd1f-138">Укажите, как вы хотите перенаправить звонок.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-138">Choose how you want to route the call.</span></span>

<span data-ttu-id="8dd1f-139">Если выбрать команду **Отключить**, автосекретарь будет зависнуть звонок.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-139">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="8dd1f-140">Если вы выбрали команду **перенаправить звонок**, вы можете выбрать один из назначений маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-140">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="8dd1f-141">Если вы выбрали пункт **Параметры меню воспроизвести**, вы можете **Воспроизвести звуковой файл** или **ввести текст в сообщении приветствия** , а затем выбрать параметры меню и поиск по каталогам.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-141">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="8dd1f-142">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="8dd1f-142">Menu options</span></span>

![](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="8dd1f-143">Для параметров набора номера можно назначить клавиши 0-9 на клавиатуре телефона одному из адресатов маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-143">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="8dd1f-144">(Клавиши \* (Повтор) и \# (назад) зарезервированы системой и не могут быть переназначены.)</span><span class="sxs-lookup"><span data-stu-id="8dd1f-144">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="8dd1f-145">Сопоставления клавиш не должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-145">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="8dd1f-146">Например, можно создать меню с клавишами 0, 1 и 3, сопоставленными с параметрами, в то время как клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-146">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="8dd1f-147">Мы рекомендуем сопоставить ключ 0 с оператором, если вы настроили его.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-147">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="8dd1f-148">Если оператор не имеет значения ни один из клавиш, голосовая команда "оператор" также отключается.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-148">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="8dd1f-149">Для каждого пункта меню укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8dd1f-149">For each menu option, specify the following:</span></span>

- <span data-ttu-id="8dd1f-150">**Клавиша вызова** — клавиша на клавиатуре телефона для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-150">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="8dd1f-151">Если входные данные доступны, вызывающий абонент также может сказать этот номер, чтобы получить доступ к параметру.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-151">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="8dd1f-152">**Voice Command** — определяет голосовую команду, которую вызывающий абонент может предоставить для доступа к этому параметру, если включены голосовые входные данные.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-152">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="8dd1f-153">Она может содержать несколько слов, таких как "услуга обслуживания клиентов" или "операции и причины".</span><span class="sxs-lookup"><span data-stu-id="8dd1f-153">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="8dd1f-154">Например, вызывающий абонент может нажать 2, скажите "два" или скажите "продажи", чтобы выбрать параметр, сопоставленный с клавишей 2.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-154">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="8dd1f-155">Этот текст также отображается по тексту в речь для запроса на подтверждение службы, который может выглядеть примерно так, как "Передача звонка в продажи".</span><span class="sxs-lookup"><span data-stu-id="8dd1f-155">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="8dd1f-156">**Перенаправить на** — назначение маршрутизации звонков, используемое для вызывающих абонентов, если этот параметр выбран.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-156">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="8dd1f-157">Если вы перенаправлялись на автосекретарь или очередь звонков, выберите связанную с ней учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-157">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="8dd1f-158">Поиск в каталоге</span><span class="sxs-lookup"><span data-stu-id="8dd1f-158">Directory search</span></span>

<span data-ttu-id="8dd1f-159">Если вы назначаете ключи набора для конечных объектов, мы рекомендуем выбрать параметр **None** для **поиска в каталоге**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-159">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="8dd1f-160">Если вызывающий абонент пытается набрать имя или расширение с помощью ключей, которые назначены конкретным получателям, они могут неожиданно перенаправляться в место назначения, прежде чем они закончит вводить имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-160">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="8dd1f-161">Мы рекомендуем создать отдельный автосекретарь для поиска в службе каталогов и попросите основной автосекретарь на него через ключ набора.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-161">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="8dd1f-162">Если вы не назначаете ключи набора номера, выберите параметр для **поиска по каталогу**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-162">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="8dd1f-163">**Набрать номер** — если вы включите этот параметр, вызывающие абоненты могут нанести имя пользователя или ввести его на клавиатуре телефона.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-163">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="8dd1f-164">Любой пользователь в сети с лицензией на телефонную систему или любой пользователь, размещенный в локальной среде Skype для бизнеса Server, является подходящим пользователем и может быть найден с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-164">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="8dd1f-165">(Вы можете настроить пользователей, которые не включены в каталог на странице " [область набора номера](#dial-scope) ".)</span><span class="sxs-lookup"><span data-stu-id="8dd1f-165">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="8dd1f-166">**Набрать номер с помощью расширения** если вы включите этот параметр, абоненты могут подключаться к своим пользователям из вашей организации, набирая их добавочные номера.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-166">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="8dd1f-167">Любой пользователь в сети с лицензией на телефонную систему или любой пользователь, размещенный в локальной среде Skype для бизнеса Server, является подходящим пользователем и может быть найден с помощью **набора номера по расширению**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-167">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="8dd1f-168">(Вы можете настроить пользователей, которые не включены в каталог на странице " [область набора номера](#dial-scope) ".)</span><span class="sxs-lookup"><span data-stu-id="8dd1f-168">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="8dd1f-169">Для пользователей, которые должны быть доступны для набора номера с помощью расширения, необходимо задать расширение как часть одного из указанных ниже атрибутов, определенных в службе каталогов Active Directory или Azure Active Directory (Дополнительные сведения можно найти [в разделе Добавление пользователей по отдельности или массовое заполнение](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) ).</span><span class="sxs-lookup"><span data-stu-id="8dd1f-169">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="8dd1f-170">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="8dd1f-170">OfficePhone</span></span>
- <span data-ttu-id="8dd1f-171">HomePhone</span><span class="sxs-lookup"><span data-stu-id="8dd1f-171">HomePhone</span></span>
- <span data-ttu-id="8dd1f-172">Мобильный или MobilePhone</span><span class="sxs-lookup"><span data-stu-id="8dd1f-172">Mobile/MobilePhone</span></span>
- <span data-ttu-id="8dd1f-173">TelephoneNumber/заданный</span><span class="sxs-lookup"><span data-stu-id="8dd1f-173">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="8dd1f-174">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="8dd1f-174">OtherTelephone</span></span>

<span data-ttu-id="8dd1f-175">Формат, необходимый для ввода расширения в поле "телефонный номер пользователя", должен быть \* + <phone number> ext <extension> =\* или \* + <phone number> x <extension> \*.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-175">The required format to enter the extension in the user phone number field is either *+<phone number>ext=<extension>* or *+<phone number>x<extension>*.</span></span>

<span data-ttu-id="8dd1f-176">Вы можете настроить расширение в [центре администрирования Microsoft 365](https://admin.microsoft.com/) или в [центре администрирования Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8dd1f-176">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="8dd1f-177">Чтобы изменения были доступны для автосекретарей и очередей звонков, может потребоваться до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-177">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="8dd1f-178">Если вы хотите использовать функции **набора номера по имени** и **набора номера** , вы можете назначить для него ключ набора номера на основном автосекретаря, чтобы получить доступ к автосекретарь **по имени**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-178">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="8dd1f-179">В рамках этого автосекретаря вы можете присвоить клавишу 1 (которая не имеет связанных с ней букв) и связаться с автосекретарем **набора номера** .</span><span class="sxs-lookup"><span data-stu-id="8dd1f-179">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="8dd1f-180">Выбрав один из вариантов **поиска в каталоге** , нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-180">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="8dd1f-181">Поток звонков за часы</span><span class="sxs-lookup"><span data-stu-id="8dd1f-181">Call flow for after hours</span></span>

![](media/auto-attendant-business-hours.png)

<span data-ttu-id="8dd1f-182">Рабочие часы можно настроить для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-182">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="8dd1f-183">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-183">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="8dd1f-184">Рабочие часы можно настроить с разбивкой на время в течение дня, а все часы, не заданные в качестве рабочих часов, рассматриваются после-часов.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-184">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="8dd1f-185">Вы можете настроить различные параметры обработки входящих звонков и приветствия в течение не более часа.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-185">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="8dd1f-186">В зависимости от того, как вы настроили автоматические ассистенты и очереди звонков, вам может потребоваться указать только после-часового звонка для автосекретарей с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-186">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="8dd1f-187">Если вы хотите отдельно настроить маршрутизацию звонков для вызывающих абонентов после выхода из него, укажите рабочие часы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-187">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="8dd1f-188">Нажмите кнопку **Добавить** , чтобы указать несколько наборов часов для определенного дня, например для выбора перерыва на обед.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-188">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="8dd1f-189">После того как вы зауказали рабочее время, а затем выберете параметры маршрутизации звонков в течение часа.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-189">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="8dd1f-190">Те же параметры доступны для маршрутизации вызовов рабочих часов, указанных выше.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-190">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="8dd1f-191">Когда все будет готово, нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="8dd1f-191">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="8dd1f-192">Потоки звонка во время праздников</span><span class="sxs-lookup"><span data-stu-id="8dd1f-192">Call flows during holidays</span></span>

![](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="8dd1f-193">У автосекретаря может быть поток звонков для каждого [настроенного праздника](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8dd1f-193">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="8dd1f-194">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-194">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="8dd1f-195">На странице Параметры звонка нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-195">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="8dd1f-196">Введите имя для этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-196">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="8dd1f-197">Из раскрывающегося списка **праздников** выберите праздничный день, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-197">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="8dd1f-198">Выберите тип приветствия, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-198">Choose the type of greeting that you want to use.</span></span>

    ![](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="8dd1f-199">Выберите, хотите ли вы **Отключить** или **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-199">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="8dd1f-200">Если вы выбрали перенаправление, выберите назначение маршрутизации звонков для звонка.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-200">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="8dd1f-201">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-201">Click **Save**.</span></span>

![](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="8dd1f-202">Повторите процедуру, если это необходимо для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-202">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="8dd1f-203">После добавления всех праздников нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-203">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="8dd1f-204">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="8dd1f-204">Dial scope</span></span>

![](media/auto-attendant-dial-scope.png)

<span data-ttu-id="8dd1f-205">*Область набора номера* определяет, какие пользователи доступны в каталоге, когда вызывающий абонент использует коммутируемое имя или коммутируемое подключение.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-205">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="8dd1f-206">Значения по умолчанию для **всех пользователей** в Организации включают в себя пользователей, которые являются сетевыми и подключенными к сети с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-206">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="8dd1f-207">Вы можете включить или исключить конкретных пользователей, выбрав **пользовательскую группу** в разделе **включить** или **исключить** и выбрать одну или несколько групп Microsoft 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-207">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="8dd1f-208">Например, вы можете исключить руководителей в организации из каталога набора.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-208">For example, you might want to exclude executives in your organization from the dialing directory.</span></span>

> [!NOTE]
> <span data-ttu-id="8dd1f-209">Для нового пользователя в каталоге может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-209">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="8dd1f-210">Завершив настройку области набора номера, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-210">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="8dd1f-211">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="8dd1f-211">Resource accounts</span></span>

<span data-ttu-id="8dd1f-212">У всех автосекретарей должна быть соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-212">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="8dd1f-213">Для автосекретаря первого уровня требуется по крайней мере одна учетная запись ресурса с соответствующим номером услуги.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-213">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="8dd1f-214">При желании вы можете назначить несколько учетных записей ресурсов для автосекретаря, каждый из которых имеет отдельный номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-214">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="8dd1f-215">Чтобы добавить учетную запись ресурса, нажмите кнопку **Добавить учетную** запись и выполните поиск учетной записи, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-215">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="8dd1f-216">Нажмите кнопку **Добавить**, а затем — **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-216">Click **Add**, and then click **Add**.</span></span>

![](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="8dd1f-217">Завершив добавление учетных записей служб, нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-217">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="8dd1f-218">После этого Автоматическая Настройка автосекретаря завершается.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-218">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="8dd1f-219">Внешние номера телефонов — технические сведения</span><span class="sxs-lookup"><span data-stu-id="8dd1f-219">External phone number transfers - technical details</span></span>

<span data-ttu-id="8dd1f-220">При передаче звонков на внешний телефонный номер учетной записи ресурса, связанной с автосекретарем или очередью звонков, должен быть указан номер телефона и лицензия Microsoft 365 Phone System.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-220">When transferring calls to an external phone number, the resource account associated with the auto attendant or call queue must have a phone number and a Microsoft 365 Phone System - Virtual User license.</span></span> <span data-ttu-id="8dd1f-221">Вдобавок</span><span class="sxs-lookup"><span data-stu-id="8dd1f-221">Additionally:</span></span>

- <span data-ttu-id="8dd1f-222">Назначение лицензии на [план звонков](calling-plans-for-office-365.md) для учетной записи ресурса с номером тарифного плана.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-222">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
- <span data-ttu-id="8dd1f-223">Для учетной записи ресурса с прямым номером маршрутизации назначьте [политику голосовой маршрутизации в сети](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8dd1f-223">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>

<span data-ttu-id="8dd1f-224">Отображаемый исходящий номер телефона определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8dd1f-224">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="8dd1f-225">Для номеров планов звонков отображается номер телефона исходного вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-225">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="8dd1f-226">Для прямых маршрутов номер отправляется на основе параметра P-Assert-Identity (PAI) на SBC, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-226">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="8dd1f-227">Если установлено значение "отключено", отображается номер телефона исходного вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-227">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="8dd1f-228">Этот параметр является рекомендуемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-228">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="8dd1f-229">Если установлено значение "включено", отображается номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-229">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="8dd1f-230">Передача данных между магистральными тарифными планами и магистральными магистрали прямой маршрутизации не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-230">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

<span data-ttu-id="8dd1f-231">В гибридной среде для передачи вызова автосекретаря в КТСОП через Skype для бизнеса PSTN вы можете создать нового локального пользователя с помощью переадресации звонков, для которого установлен номер КТСОП.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-231">In a hybrid environment, to transfer an auto attendant call to the PSTN via Skype for Business PSTN integration, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="8dd1f-232">Пользователь должен быть активирован для корпоративной голосовой связи и имеет назначенную политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-232">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="8dd1f-233">Дополнительные сведения можно найти в разделе Переадресация [звонков по автосекретарем в КТСОП](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="8dd1f-233">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="8dd1f-234">Создание автосекретаря с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dd1f-234">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="8dd1f-235">Вы также можете использовать PowerShell для создания и настройки автоматических ассистентов.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-235">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="8dd1f-236">Ниже приведены командлеты, необходимые для управления автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="8dd1f-236">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="8dd1f-237">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8dd1f-237">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="8dd1f-238">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8dd1f-238">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="8dd1f-239">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8dd1f-239">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [<span data-ttu-id="8dd1f-240">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="8dd1f-240">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="8dd1f-241">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8dd1f-241">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="8dd1f-242">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="8dd1f-242">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="8dd1f-243">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="8dd1f-243">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="8dd1f-244">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="8dd1f-244">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="8dd1f-245">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="8dd1f-245">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="8dd1f-246">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="8dd1f-246">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="8dd1f-247">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="8dd1f-247">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="8dd1f-248">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="8dd1f-248">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="8dd1f-249">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="8dd1f-249">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="8dd1f-250">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="8dd1f-250">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="8dd1f-251">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="8dd1f-251">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="8dd1f-252">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="8dd1f-252">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="8dd1f-253">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="8dd1f-253">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)


## <a name="related-topics"></a><span data-ttu-id="8dd1f-254">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8dd1f-254">Related topics</span></span>

[<span data-ttu-id="8dd1f-255">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="8dd1f-255">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="8dd1f-256">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="8dd1f-256">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="8dd1f-257">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="8dd1f-257">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="8dd1f-258">Пример для малого бизнеса: Настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="8dd1f-258">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="8dd1f-259">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8dd1f-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
