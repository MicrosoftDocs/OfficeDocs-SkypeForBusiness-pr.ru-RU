---
title: Настройка облачного автосекретаря
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Сведения о настройке и тестировании автоматических автосекретарей в облачных целях для Microsoft Teams.
ms.openlocfilehash: bd23262a3b8cd3c50cffbb4be6aa70317d209613
ms.sourcegitcommit: a0df7479662b3bea488c19722ad588981f58a5e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2019
ms.locfileid: "36447945"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="837c0-103">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="837c0-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="837c0-104">Автосекретарь позволяет людям, которые могут позвонить в организацию, и переходить в систему меню, чтобы получить их в нужный отдел, очередь звонков, человека или оператор.</span><span class="sxs-lookup"><span data-stu-id="837c0-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="837c0-105">Вы можете создать автосекретарь для своей организации с помощью центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="837c0-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="837c0-106">Чтобы создать автосекретарь, на панели навигации слева выберите пункт **Голосовая связь** , а затем —**Добавить новые** **ассистенты** > .</span><span class="sxs-lookup"><span data-stu-id="837c0-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="837c0-107">Если вы хотите узнать больше об автосекретарях, посмотрите, [что такое автосекретарь облака?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="837c0-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="837c0-108">Эта статья относится как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="837c0-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="837c0-109">Этап 1 — Начало работы</span><span class="sxs-lookup"><span data-stu-id="837c0-109">Step 1 — Get started</span></span>

- <span data-ttu-id="837c0-110">Для связи с учетной записью ресурса необходимо наличие автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="837c0-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="837c0-111">Дополнительные сведения об учетных записях ресурсов и всех необходимых лицензиях смотрите [в разделе Управление учетными записями ресурсов в Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="837c0-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="837c0-112">Чтобы перенаправить звонки на оператора или параметр меню, который является сетевым пользователем с лицензией на **телефонную систему** , вам потребуется включить их для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="837c0-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="837c0-113">В разделе [Назначение лицензий на Skype для бизнеса](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) или [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="837c0-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="837c0-114">Вы также можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="837c0-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="837c0-115">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="837c0-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="837c0-116">Шаг 2: создание нового автосекретаря</span><span class="sxs-lookup"><span data-stu-id="837c0-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="837c0-117">Для каждого автосекретаря требуется наличие соответствующей [учетной записи ресурса](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="837c0-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="837c0-118">Сначала необходимо создать учетную запись ресурса, после чего вы сможете связать ее с автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="837c0-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="837c0-119">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="837c0-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="837c0-120">В \*\*\*\* > \*\*\*\* **центре администрирования Microsoft Teams**щелкните "автосекретарь" и выберите пункт " **+ создать**".</span><span class="sxs-lookup"><span data-stu-id="837c0-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="837c0-121">Страница "Общие сведения"</span><span class="sxs-lookup"><span data-stu-id="837c0-121">General info page</span></span>

![Снимок экрана: страница "мой секретарь"](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="837c0-124">**Имя** Введите понятное отображаемое имя вашего автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="837c0-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="837c0-125">Имя является обязательным и может содержать до 64 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="837c0-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="837c0-126">Оно указано в столбце **Name (имя** ) на \*\*\*\* вкладке автосекретарьы.</span><span class="sxs-lookup"><span data-stu-id="837c0-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="837c0-128">**Учетная запись ресурса** Нажмите эту кнопку, чтобы выбрать одну или несколько учетных записей ресурсов для подключения к новому автосекретарею.</span><span class="sxs-lookup"><span data-stu-id="837c0-128">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="837c0-129">Для всех автосекретарей требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="837c0-129">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="837c0-130">У учетной записи ресурса может быть номер телефона, связанный с учетной записью, но номер телефона не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="837c0-130">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="837c0-131">Для автосекретаря верхнего уровня обычно используется учетная запись ресурса с назначенным номером телефона, но вложенный автосекретарь (используемый в качестве меню уровня 2, к которому подключается автосекретарь первого уровня) может не содержать номер телефона, назначенный его учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="837c0-131">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

![Значок цифры 3, ссылающаяся на выноску на предыдущем снимке экрана](media/sfbcallout3.png)

<span data-ttu-id="837c0-133">**Часовой пояс** Вы должны настроить часовой пояс для автосекретаря, но он не должен совпадать с часовым поясом основного адреса, указанного в Организации.</span><span class="sxs-lookup"><span data-stu-id="837c0-133">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="837c0-134">Каждый автосекретарь может иметь другой часовой пояс, и рабочие часы, заданные для автосекретаря, задаются в зависимости от выбранного вами часового пояса.</span><span class="sxs-lookup"><span data-stu-id="837c0-134">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![Значок числа 4 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout4.png)

<span data-ttu-id="837c0-136">**Language (язык** ) Выберите язык, который вы хотите использовать для автосекретаря, на любом из доступных языков.</span><span class="sxs-lookup"><span data-stu-id="837c0-136">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="837c0-137">Язык, установленный в этом разделе, — это язык, используемый автосекретарем для общения с абонентами, вызывающими этот автоматический секретарь, и все системные запросы воспроизводится на этом языке.</span><span class="sxs-lookup"><span data-stu-id="837c0-137">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![Значок числа 5, на котором показана ссылка на выноску на предыдущем снимке экрана](media/sfbcallout5.png)

<span data-ttu-id="837c0-139">**Operator (оператор** ) Это необязательно, но вы можете настроить параметр **оператора** таким образом, чтобы вызывающие абоненты выходили из меню и поговорить с пользователем.</span><span class="sxs-lookup"><span data-stu-id="837c0-139">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="837c0-140">Клавиша 0 назначается оператору по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="837c0-140">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="837c0-141">Если вы настроили оператор, вам также потребуется указать пользователей, которые будут вызывать этот параметр в **меню "Правка** " на странице " **Обработка звонков в рабочее время** ".</span><span class="sxs-lookup"><span data-stu-id="837c0-141">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="837c0-142">Если вы установили оператора для автосекретаря, вам нужно **будет** ввести соответствующий текст подсказки в поле вызывающий абоненты или изменить звуковой файл таким образом, чтобы он включал этот параметр.</span><span class="sxs-lookup"><span data-stu-id="837c0-142">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="837c0-143">Например, "Чтобы связаться с оператором, нажмите ноль".</span><span class="sxs-lookup"><span data-stu-id="837c0-143">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="837c0-144">Есть несколько способов задания оператора:</span><span class="sxs-lookup"><span data-stu-id="837c0-144">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="837c0-145">**Сотрудник компании**, имеющий лицензию на**телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="837c0-145">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="837c0-146">**Сотрудник компании** может быть онлайн-пользователем или пользователем, находящимся на территории локального предприятия и использующим Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="837c0-146">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="837c0-147">**Голосовое приложение** Выберите имя учетной записи ресурса, связанной с уже созданной очередью звонков или автоматическим ассистентом.</span><span class="sxs-lookup"><span data-stu-id="837c0-147">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="837c0-148">Вы можете настроить его таким образом, чтобы голосовой звонок отправлялся на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="837c0-148">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="837c0-149">Для этого выберите сотрудника **в своей компании** и настройте звонки этого пользователя прямо в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="837c0-149">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Значок числа 6 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout6.png)

<span data-ttu-id="837c0-151">**Включение голосового ввода** Если выбран этот параметр, распознавание речи доступно.</span><span class="sxs-lookup"><span data-stu-id="837c0-151">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="837c0-152">Пользователи, которые вызывают абонентов, могут использовать голосовые данные на указанном [вами языке](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="837c0-152">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="837c0-153">Если вы хотите, чтобы пользователи могли использовать только клавиатуру телефона, вы можете отключить распознавание речи, установив значение OFF.</span><span class="sxs-lookup"><span data-stu-id="837c0-153">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="837c0-154">Завершив выбор параметров, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="837c0-154">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="837c0-155">Страница "рабочие часы"</span><span class="sxs-lookup"><span data-stu-id="837c0-155">Business hours page</span></span>

<span data-ttu-id="837c0-156">По умолчанию в рабочее время 9:00 – 5:00 PM, с понедельника по пятницу.</span><span class="sxs-lookup"><span data-stu-id="837c0-156">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="837c0-157">Все часы, не включенные в рабочие часы, учитываются после рабочих часов.</span><span class="sxs-lookup"><span data-stu-id="837c0-157">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="837c0-158">Вы можете нажать кнопку **выбрать 24/7** , чтобы сделать все часы в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="837c0-158">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="837c0-159">Если вы не выбрали параметр **выбрать 24/7** , на странице **Параметры звонка после набора часов** будет использоваться для настройки правил обработки звонков после создания автосекретаря в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="837c0-159">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

![Снимок экрана: страница "рабочие часы"](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="837c0-162">По умолчанию для рабочих часов задано значение понедельник — пятница, 9:00 – 5:00 PM.</span><span class="sxs-lookup"><span data-stu-id="837c0-162">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="837c0-163">Выберите команду **Очистить все часы** , чтобы отменить выбор всех часов в расписании.</span><span class="sxs-lookup"><span data-stu-id="837c0-163">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="837c0-164">Если выбрать вариант **восстановить значения по умолчанию**, рабочие часы будут сброшены в понедельник в пятницу, 9:00 – 5:00 PM.</span><span class="sxs-lookup"><span data-stu-id="837c0-164">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="837c0-166">Чтобы изменить рабочие часы, выберите рабочее время, которое вы хотите задать в календаре.</span><span class="sxs-lookup"><span data-stu-id="837c0-166">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="837c0-167">В календаре вы можете выбрать рабочие часы в течение 30 минут, а часы, выбранные в этом поле, зависят от часового пояса, заданного на странице " **Общие сведения** ".</span><span class="sxs-lookup"><span data-stu-id="837c0-167">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="837c0-168">Чтобы задать перерыв, например обеденное время, отмените выбор соответствующих часов в календаре.</span><span class="sxs-lookup"><span data-stu-id="837c0-168">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="837c0-169">Вы можете настроить несколько перерывов в рабочих часах.</span><span class="sxs-lookup"><span data-stu-id="837c0-169">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="837c0-170">Завершив выбор параметров, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="837c0-170">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="837c0-171">Параметры звонков в рабочее время</span><span class="sxs-lookup"><span data-stu-id="837c0-171">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="837c0-172">Если вы используете настраиваемое расписание рабочих часов, вам также потребуется настроить функцию обработки звонков после рабочего времени с помощью страницы **Обработка звонков после нескольких часов** , и вы получите те же параметры, что и **параметры звонков в бизнес-часах**.</span><span class="sxs-lookup"><span data-stu-id="837c0-172">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="837c0-173">Вы можете настроить приветствия, подсказки и меню, которые будут слышать кто-то при звонке на номер телефона, связанный с автосекретарем вашей организации, в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="837c0-173">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="837c0-174">![Снимок экрана: раздел](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![приветствия "страница обработки звонков в рабочее время" в разделе "действия страницы" обработки звонков в бизнес-часах](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="837c0-174">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="837c0-176">**Приветствие** Приветствие в рабочее время не является обязательным и может иметь значение **без приветствия**.</span><span class="sxs-lookup"><span data-stu-id="837c0-176">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="837c0-177">В этом случае вызывающий абонент не слышит сообщение или приветствие до тех пор, пока звонок не будет обработан одним из выбранных вами действий.</span><span class="sxs-lookup"><span data-stu-id="837c0-177">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="837c0-178">Вы также можете загрузить аудиофайл (в формате WAV, mp3 или WMA) или создать настраиваемое приветствие, используя функцию преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="837c0-178">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="837c0-179">**Загрузить аудиофайл** Если выбран этот параметр, запишите приветствие и загрузите полученный звуковой файл (в формате WAV, .mp3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="837c0-179">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="837c0-180">**Ввод сообщения приветствия** Если выбрать этот параметр, введите текст, который система должна прочитать (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="837c0-180">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="837c0-181">Например, можно ввести "Вас приветствует Contoso.</span><span class="sxs-lookup"><span data-stu-id="837c0-181">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="837c0-182">Ваш звонок очень важен для нас."</span><span class="sxs-lookup"><span data-stu-id="837c0-182">Your call is important to us."</span></span> <span data-ttu-id="837c0-183">в поле **Текст для вызывающих абонентов**.</span><span class="sxs-lookup"><span data-stu-id="837c0-183">in the **Callers will hear** box.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="837c0-185">Вы можете выбрать, как будут обрабатываться звонки, поступающие в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="837c0-185">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="837c0-186">Вы можете выбрать из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="837c0-186">You can chose from the following actions:</span></span>

- <span data-ttu-id="837c0-187">**Отключить** Если выбран этот параметр, вызывающий абонент будет отключен после прослушивания приветствия в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="837c0-187">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="837c0-188">**Переадресовать звонок** Этот параметр можно использовать для автоматической переадресации вызова, используя следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="837c0-188">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="837c0-189">**Сотрудник компании** с лицензией на **телефонную систему** , для которой включена Корпоративная голосовая связь или назначенные планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="837c0-189">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="837c0-190">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="837c0-190">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="837c0-191">Для этого выберите сотрудника **в компании** и настройте для него переадресацию звонков прямо на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="837c0-191">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="837c0-192">**Сотрудникам компании** может быть пользователь в сети или пользователь, размещенный в локальной среде, с помощью Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="837c0-192">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="837c0-193">Другой **Автоматический секретарь**</span><span class="sxs-lookup"><span data-stu-id="837c0-193">Another **Auto attendant**</span></span>

   <span data-ttu-id="837c0-194">Вы можете использовать существующий автоматический секретарь для создания второго уровня параметров меню, содержащих подменю.</span><span class="sxs-lookup"><span data-stu-id="837c0-194">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="837c0-195">Эти функции называются вложенными автосекретарями.</span><span class="sxs-lookup"><span data-stu-id="837c0-195">These are called nested auto attendants.</span></span> <span data-ttu-id="837c0-196">Чтобы отправить звонок во вложенный автоматический секретарь, выберите сотрудника **в компании** и назначьте учетную запись ресурса, в которой уже есть соответствующий автоматический секретарь, или в том случае, если вы хотите связать его с автосекретарем после того, как вы закончите создавать этот автоматический секретарь.</span><span class="sxs-lookup"><span data-stu-id="837c0-196">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="837c0-197">**Параметры меню "воспроизведение** " можно также использовать для настройки подсказок для воспроизведений.</span><span class="sxs-lookup"><span data-stu-id="837c0-197">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Значок цифры 3, ссылающаяся на выноску на предыдущем снимке экрана](media/sfbcallout3.png)

<span data-ttu-id="837c0-199">**Запрос меню** Чтобы создать главное меню, вы можете использовать функции преобразования текста в речь или загрузить звуковой файл (WAV, MP3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="837c0-199">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="837c0-200">Вы можете ввести запрос в поле **Настройка навигации по меню для вызывающих абонентов** или записать звуковой файл, например: "для продажи, произнесите или нажмите или произнесите 1.</span><span class="sxs-lookup"><span data-stu-id="837c0-200">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="837c0-201">Для служб нажмите или скажите 2.</span><span class="sxs-lookup"><span data-stu-id="837c0-201">For Services, press or say 2.</span></span> <span data-ttu-id="837c0-202">Для поддержки пользователей нажмите или скажите 3.</span><span class="sxs-lookup"><span data-stu-id="837c0-202">For Customer Support, press or say 3.</span></span> <span data-ttu-id="837c0-203">Для оператора нажмите или произнесите 0.</span><span class="sxs-lookup"><span data-stu-id="837c0-203">For the operator, press or say 0.</span></span> <span data-ttu-id="837c0-204">Чтобы снова услышать это меню, нажмите звездочку или произнесите команду "повторить" ".</span><span class="sxs-lookup"><span data-stu-id="837c0-204">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="837c0-205">**Ввод сообщения приветствия** Если вы выбрали этот параметр, введите текст, который будет считаться системой (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="837c0-205">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="837c0-206">**Добавление звукового файла** Если вы выбрали этот параметр, вам нужно будет записать приветствие, а затем загрузить звуковой файл (в формате WAV, MP3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="837c0-206">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Значок числа 4 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout4.png)

<span data-ttu-id="837c0-208">**Настройка параметров меню** Вы можете добавить или удалить параметры меню с помощью клавиш на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="837c0-208">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="837c0-209">Чтобы добавить параметр меню, нажмите клавишу **+ и назначьте клавишу набора номера**.</span><span class="sxs-lookup"><span data-stu-id="837c0-209">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="837c0-210">Ниже показана соответствующая строка параметров.</span><span class="sxs-lookup"><span data-stu-id="837c0-210">A corresponding row of options will appear below.</span></span> <span data-ttu-id="837c0-211">Чтобы удалить параметр меню, щелкните слева от соответствующей клавиши на клавиатуре и щелкните значок удаления выше.</span><span class="sxs-lookup"><span data-stu-id="837c0-211">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="837c0-212">Строка сопоставления клавиш будет удалена.</span><span class="sxs-lookup"><span data-stu-id="837c0-212">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="837c0-213">Вам потребуется обновить текст подсказки в меню или заново записать звук отдельно при добавлении к параметрам удаления, так как он не будет автоматически выполняться для этого запроса меню.</span><span class="sxs-lookup"><span data-stu-id="837c0-213">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="837c0-214">Любые параметры меню можно добавлять и удалять в любом порядке, при этом сопоставления клавиш необязательно должны быть последовательными.</span><span class="sxs-lookup"><span data-stu-id="837c0-214">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="837c0-215">Например, можно создать меню с помощью сопоставления с параметрами клавиш 0, 1 и 3, при этом клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="837c0-215">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="837c0-216">Клавиши \* (повтор) и \# (назад) зарезервированы системой и не могут быть переназначены.</span><span class="sxs-lookup"><span data-stu-id="837c0-216">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="837c0-217">Если включен параметр распознавания речи, нажатие клавиши \* соответствует голосовой команде "Повтор", а нажатие клавиши # — голосовой команде "Назад".</span><span class="sxs-lookup"><span data-stu-id="837c0-217">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="837c0-218">Чтобы настроить параметры меню, после выбора ключа вызова необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="837c0-218">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="837c0-219">Введите **голосовую команду** для параметра.</span><span class="sxs-lookup"><span data-stu-id="837c0-219">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="837c0-220">Это может быть не более 64 символов и может содержать несколько слов, например "Обслуживание клиентов" или "операции и причины".</span><span class="sxs-lookup"><span data-stu-id="837c0-220">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="837c0-221">Если включена функция распознавания речи, имя будет распознаваться автоматически, а вызывающий абонент сможет нажать клавишу 3, сказать «три» или «обслуживание клиентов», чтобы выбрать параметр, закрепленный за клавишей 3.</span><span class="sxs-lookup"><span data-stu-id="837c0-221">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="837c0-222">Выберите, куда будет отправляться звонок при нажатии соответствующей клавиши, или параметр, выбранный с помощью функции распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="837c0-222">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="837c0-223">Кому можно направить вызов:</span><span class="sxs-lookup"><span data-stu-id="837c0-223">The call can be sent to:</span></span>

  - <span data-ttu-id="837c0-224">**Оператор** Если параметр "Оператор" уже настроен, он автоматически сопоставляется с клавишей 0, но его можно также удалить или закрепить за другой клавишей.</span><span class="sxs-lookup"><span data-stu-id="837c0-224">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="837c0-225">Если связь с оператором не закреплена за какой-либо клавишей, то голосовая команда "Оператор" также будет отключена.</span><span class="sxs-lookup"><span data-stu-id="837c0-225">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="837c0-226">**Сотрудник компании**, имеющий лицензию на**телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="837c0-226">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="837c0-227">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="837c0-227">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="837c0-228">Для этого выберите сотрудника **в компании** и настройте для него звонки, переадресованные непосредственно в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="837c0-228">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="837c0-229">**Сотрудникам вашей компании** может быть пользователь в сети или пользователь, размещенный в локальной среде, с помощью Skype для бизнеса Server или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="837c0-229">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>
    - <span data-ttu-id="837c0-230">Другой **Автоматический секретарь**</span><span class="sxs-lookup"><span data-stu-id="837c0-230">Another **Auto attendant**</span></span>

       <span data-ttu-id="837c0-231">Вы можете использовать существующий автоматический секретарь для создания второго уровня параметров меню, содержащих подменю.</span><span class="sxs-lookup"><span data-stu-id="837c0-231">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="837c0-232">Эти функции называются вложенными автосекретарями.</span><span class="sxs-lookup"><span data-stu-id="837c0-232">These are called nested auto attendants.</span></span> <span data-ttu-id="837c0-233">Чтобы отправить звонок во вложенный автоматический секретарь, выберите сотрудника **в компании** и назначьте учетную запись ресурса, в которой уже есть соответствующий автоматический секретарь, или в том случае, если вы хотите связать его с автосекретарем после того, как вы закончите создавать этот автоматический секретарь.</span><span class="sxs-lookup"><span data-stu-id="837c0-233">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="837c0-234">Также будет использоваться **время работы** вложенных автосекретарей (автосекретарей второго уровня), в том числе для вызовов, переадресуемых с других настроенных автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="837c0-234">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

       - <span data-ttu-id="837c0-235">**Голосовое приложение** Выберите имя учетной записи ресурса, связанной с уже созданной очередью звонков или автоматическим ассистентом.</span><span class="sxs-lookup"><span data-stu-id="837c0-235">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Значок числа 5, на котором показана ссылка на выноску на предыдущем снимке экрана](media/sfbcallout5.png)

<span data-ttu-id="837c0-237">**Вызов по имени** Выбор этого параметра позволяет вызывающим абонентам выполнить поиск сотрудников организации, используя функцию поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="837c0-237">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="837c0-238">Вы можете выбрать, каких пользователей можно вызвать, используя функцию "Вызов по имени", а каких — нет, настроив эти параметры на странице **Область вызова.**.</span><span class="sxs-lookup"><span data-stu-id="837c0-238">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="837c0-239">Любой пользователь в сети с лицензией на **телефонную систему** или любой пользователь, размещенный в локальной среде Skype для бизнеса Server или Lync Server 2013, может быть найден с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="837c0-239">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="837c0-240">Завершив выбор параметров, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="837c0-240">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="837c0-241">Параметры звонка в праздничные дни</span><span class="sxs-lookup"><span data-stu-id="837c0-241">Holiday call settings</span></span>

<span data-ttu-id="837c0-242">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="837c0-242">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="837c0-243">Для создания праздников можно перейти на экран \*\*\*\* > в параметрах организации "**праздники** ", а также создать новый обработчик вызова.</span><span class="sxs-lookup"><span data-stu-id="837c0-243">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Снимок экрана со страницей параметров звонка на праздник](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="837c0-246">Если вы уже создали другие автосекретарей, возможно, вы видите параметр, который можно использовать для редактирования в этом списке.</span><span class="sxs-lookup"><span data-stu-id="837c0-246">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="837c0-247">В противном случае вам потребуется создать новый обработчик вызова.</span><span class="sxs-lookup"><span data-stu-id="837c0-247">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="837c0-248">Чтобы добавить новый обработчик вызова, щелкните значок **+ новый обработчик вызова**.</span><span class="sxs-lookup"><span data-stu-id="837c0-248">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Снимок экрана, демонстрирующий Добавление нового обработчика вызова](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="837c0-251">В новом окне введите имя нового обработчика звонков в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="837c0-251">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="837c0-253">Если название вашего праздника уже есть в раскрывающемся списке **праздников** , вы можете использовать его.</span><span class="sxs-lookup"><span data-stu-id="837c0-253">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="837c0-254">Если нужного названия праздника еще не существует, выберите в раскрывающемся списке **создать новый праздник** и назначьте имя и дату нового праздника на появившемся новом экране.</span><span class="sxs-lookup"><span data-stu-id="837c0-254">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="837c0-255">Когда все будет готово, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="837c0-255">Click on **Save** when ready.</span></span>

<span data-ttu-id="837c0-256">Имена праздников могут содержать до 64 знаков; каждое имя праздника одного автосекретаря должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="837c0-256">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="837c0-257">Например, нельзя создать для одного автосекретаря два праздника с именем "День Благодарения".</span><span class="sxs-lookup"><span data-stu-id="837c0-257">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Значок цифры 3, ссылающаяся на выноску на предыдущем снимке экрана](media/sfbcallout3.png)

<span data-ttu-id="837c0-259">**Приветствие** Приветствие является необязательным и может иметь значение **без приветствия**.</span><span class="sxs-lookup"><span data-stu-id="837c0-259">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="837c0-260">В этом случае вызывающий абонент не услышит никакого сообщения или приветствия, пока вызов не будет обработан с использованием одного из выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="837c0-260">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="837c0-261">Вы также можете загрузить аудиофайл (в формате WAV, mp3 или WMA) или создать настраиваемое приветствие, используя функцию преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="837c0-261">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="837c0-262">**Без приветствия** При звонках на номер телефона автосекретаря не будет воспроизводиться приветствие.</span><span class="sxs-lookup"><span data-stu-id="837c0-262">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="837c0-263">**Добавление звукового файла** Если вы выберете этот параметр, запишите поздравление праздников, а затем отправьте звуковой файл (в формате WAV, MP3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="837c0-263">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="837c0-264">**Ввод сообщения приветствия** Если выбрать этот параметр, введите текст, который система должна прочитать (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="837c0-264">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="837c0-265">Например, вы можете ввести текст "Поздравляем с новым годом!</span><span class="sxs-lookup"><span data-stu-id="837c0-265">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="837c0-266">Наш офисы сейчас закрыты."</span><span class="sxs-lookup"><span data-stu-id="837c0-266">Our offices are currently closed."</span></span> <span data-ttu-id="837c0-267">в диалоговом окне **Введите сообщение с приветствием** .</span><span class="sxs-lookup"><span data-stu-id="837c0-267">in the **Type a greeting message** box.</span></span>

![Значок числа 4 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout4.png)

<span data-ttu-id="837c0-269">**Действия** Вы можете выбрать, что произойдет с звонками, поступающими в этот праздник.</span><span class="sxs-lookup"><span data-stu-id="837c0-269">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="837c0-270">Возможен выбор одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="837c0-270">You can chose from the following options:</span></span>

- <span data-ttu-id="837c0-271">**Отключить** Вызывающий абонент будет отключен после прослушивания праздничного приветствия.</span><span class="sxs-lookup"><span data-stu-id="837c0-271">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="837c0-272">**Переадресовать звонок** Этот параметр можно использовать для автоматической переадресации вызова, используя следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="837c0-272">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="837c0-273">**Сотрудник компании**, имеющий лицензию на **телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="837c0-273">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="837c0-274">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="837c0-274">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="837c0-275">Для этого выберите сотрудника **в своей компании**и настройте для него звонки, переадресованные непосредственно в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="837c0-275">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="837c0-276">**Сотрудник компании** может быть онлайн-пользователем или пользователем, находящимся на территории локального предприятия и использующим Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="837c0-276">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="837c0-277">**Голосовое приложение** Выберите имя учетной записи ресурса, связанной с уже созданной очередью звонков или автоматическим ассистентом.</span><span class="sxs-lookup"><span data-stu-id="837c0-277">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="837c0-278">По умолчанию все вызовы, поступающие в период праздников, после приветствия (при его наличии) переводятся в режим "Отключить", поэтому если вы хотите изменить этот режим работы, необходимо указать, кому следует переадресовать вызов.</span><span class="sxs-lookup"><span data-stu-id="837c0-278">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="837c0-279">Страница "Выбор списка набора"</span><span class="sxs-lookup"><span data-stu-id="837c0-279">Select dial scope page</span></span>

<span data-ttu-id="837c0-280">На этой странице вы можете указать, какие пользователи в вашей организации будут перечислены в каталоге, и вы сможете звонить по имени, когда человек, который будет звонить в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="837c0-280">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Снимок экрана, на котором показана страница "область набора номера"](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="837c0-282">![Значок с номером 1, ссылающийся на выноску на предыдущем снимке экрана](media/sfbcallout1.png) с помощью параметра " **включить** ", у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="837c0-282">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="837c0-283">**Все пользователи в сети** С помощью этого параметра можно включать в поиск в каталоге всех сотрудников вашей организации.</span><span class="sxs-lookup"><span data-stu-id="837c0-283">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="837c0-284">Все пользователи сети с лицензией на **телефонную систему** , а также пользователи, размещенные в локальной среде с помощью Skype для бизнеса Server или Lync Server 2013, у которых есть планы звонков в Office 365, будут перечислены.</span><span class="sxs-lookup"><span data-stu-id="837c0-284">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="837c0-285">**Настраиваемая группа пользователей** Если вы используете этот параметр, вы можете выполнить поиск группы Office 365, списка рассылки или группы безопасности, созданной в Организации, а также пользователей, добавленных в эту группу Office 365, список рассылки или группу безопасности, в которую входят пользователи из **сети Лицензия на телефонную систему** или размещенная в локальной среде с помощью Skype для бизнеса server 2015 или Lync server 2013.</span><span class="sxs-lookup"><span data-stu-id="837c0-285">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="837c0-286">Вы можете добавить несколько групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="837c0-286">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="837c0-288">С помощью параметра **исключить** есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="837c0-288">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="837c0-289">**Нет**. Использование этой функции означает, что при поиске по справочнику никакие пользователи не исключаются из списка.   </span><span class="sxs-lookup"><span data-stu-id="837c0-289">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="837c0-290">**Настраиваемая группа пользователей** Если вы используете этот параметр, вы можете найти группу Office 365, список рассылки или группу безопасности, созданную в Организации, а все пользователи, добавленные в эту группу Office 365, список рассылки или группы безопасности, будут исключены из поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="837c0-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="837c0-291">Вы можете добавить несколько групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="837c0-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="837c0-292">Для нового пользователя может потребоваться до 36 часов, когда кто-то использует подбирать по имени с помощью функции распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="837c0-292">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="837c0-293">После ввода всех необходимых полей и настройки меню и параметров обработки звонков нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="837c0-293">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="837c0-294">Редактирование и тестирование автоматических ассистентов</span><span class="sxs-lookup"><span data-stu-id="837c0-294">Editing and testing auto attendants</span></span>

<span data-ttu-id="837c0-295">После сохранения автосекретаря он отображается в списке на странице **Автосекретари**.</span><span class="sxs-lookup"><span data-stu-id="837c0-295">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="837c0-296">Это позволит вам быстро увидеть некоторые из настроенных параметров, включая имя, номер телефона, язык и состояние.</span><span class="sxs-lookup"><span data-stu-id="837c0-296">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="837c0-297">Если вы хотите внести изменения в автосекретарь, выберите автосекретарь, а затем на панели действий нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="837c0-297">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="837c0-298">Вы также можете быстро выполнить тестовый вызов для автосекретаря с помощью кнопки **тест** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="837c0-298">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="837c0-299">Командлеты для работы с автосекретарями</span><span class="sxs-lookup"><span data-stu-id="837c0-299">Auto attendant cmdlets</span></span>

<span data-ttu-id="837c0-300">Можно также использовать Windows PowerShell для создания и настройки автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="837c0-300">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="837c0-301">Ниже приведены командлеты, необходимые для управления автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="837c0-301">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="837c0-302">New-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="837c0-302">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="837c0-303">Set-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="837c0-303">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="837c0-304">Get-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="837c0-304">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="837c0-305">Get-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="837c0-305">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="837c0-306">Remove-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="837c0-306">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="837c0-307">New-Ксаутоаттендантмену</span><span class="sxs-lookup"><span data-stu-id="837c0-307">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="837c0-308">New-Ксонлинеаудиофиле</span><span class="sxs-lookup"><span data-stu-id="837c0-308">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="837c0-309">New-Ксаутоаттенданткаллфлов</span><span class="sxs-lookup"><span data-stu-id="837c0-309">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="837c0-310">Export-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="837c0-310">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="837c0-311">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="837c0-311">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="837c0-312">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="837c0-312">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="837c0-313">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="837c0-313">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="837c0-314">Get-Ксаутоаттендантсуппортедтимезоне</span><span class="sxs-lookup"><span data-stu-id="837c0-314">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="837c0-315">New-КсаутоаттенданткаллхандлингассоЦиатион</span><span class="sxs-lookup"><span data-stu-id="837c0-315">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="837c0-316">Get-Ксаутоаттендантсуппортедлангуаже</span><span class="sxs-lookup"><span data-stu-id="837c0-316">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="837c0-317">Import-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="837c0-317">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="837c0-318">New-Ксаутоаттенданткаллаблинтити</span><span class="sxs-lookup"><span data-stu-id="837c0-318">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="837c0-319">Дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="837c0-319">More about Windows PowerShell</span></span>

- <span data-ttu-id="837c0-320">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="837c0-320">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="837c0-321">С помощью Windows PowerShell вы можете управлять набором Office 365 и Microsoft Teams с помощью одной точки администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="837c0-321">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="837c0-322">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="837c0-322">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="837c0-323">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="837c0-323">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="837c0-324">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="837c0-324">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="837c0-325">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="837c0-325">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="837c0-326">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="837c0-326">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="837c0-327">Управление Office 365 с помощью Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="837c0-327">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="837c0-328">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="837c0-328">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="837c0-329">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="837c0-329">Related topics</span></span>

[<span data-ttu-id="837c0-330">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="837c0-330">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="837c0-331">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="837c0-331">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="837c0-332">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="837c0-332">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="837c0-333">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="837c0-333">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="837c0-334">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="837c0-334">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="837c0-335">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="837c0-335">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
