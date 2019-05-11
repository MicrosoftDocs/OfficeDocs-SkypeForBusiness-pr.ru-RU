---
title: Настройка облачного автосекретаря
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Узнайте, как настроить и тестирование облачных автосекретари для обработки для вашей организации эффективным звонков.
ms.openlocfilehash: 7e655339ef35c127dcb1f106d9d9dbf7f498804d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902828"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="8e69a-103">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="8e69a-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="8e69a-104">Автосекретари, позволяет людям, вызов для вашей организации и выберите меню системы, чтобы получить их в правом отдел, вызвать очереди, лицо или оператор.</span><span class="sxs-lookup"><span data-stu-id="8e69a-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="8e69a-105">С помощью центра администрирования группами Майкрософт, можно создать автосекретарь для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8e69a-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="8e69a-106">Чтобы создать автосекретарь, перейдите к **голосовой связи** в левой панели навигации и выберите **автосекретари** > **Добавить новые**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="8e69a-107">Если вы хотите узнать больше о автосекретари, [Каковы автосекретари облаке?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="8e69a-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="8e69a-108">Эта статья относится к группам Майкрософт и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="8e69a-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>



## <a name="step-1---get-started"></a><span data-ttu-id="8e69a-109">Шаг 1 - начало работы</span><span class="sxs-lookup"><span data-stu-id="8e69a-109">Step 1 - Get started</span></span>

- <span data-ttu-id="8e69a-110">Автосекретарь необходимо иметь учетную запись связанных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8e69a-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="8e69a-111">Сведения о учетные записи ресурса в разделе [Управление учетными записями ресурсов в группах](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="8e69a-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="8e69a-112">Если вы планируете нумерации прямой маршрутизации, необходимо получить и назначение лицензий на следующие учетные записи ресурса \(Office 365 корпоративный E1, E3 или E5 с телефонной системой надстройки\).</span><span class="sxs-lookup"><span data-stu-id="8e69a-112">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="8e69a-113">Вместо этого при назначении номера службы Майкрософт, необходимо получить и назначьте следующие лицензии свою учетную запись ресурса \(Office 365 корпоративный E1, E3 или E5 с телефонной системой надстройки и вызов планирование\).</span><span class="sxs-lookup"><span data-stu-id="8e69a-113">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="8e69a-114">Корпорация Майкрософт работает на соответствующей модели лицензирования для приложений, таких как автосекретари облако и очереди вызовов, для теперь необходимо использовать модель лицензирования пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e69a-114">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!CAUTION]
> <span data-ttu-id="8e69a-115">Чтобы получить и использовать бесплатных номеров телефонов, необходимо настроить кредитов коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="8e69a-115">To get and use toll-free phone numbers, you need to set up Communications Credits.</span></span> <span data-ttu-id="8e69a-116">Чтобы это сделать, обратитесь [Каковы кредитов коммуникации?](what-are-communications-credits.md) и [настроить кредитов коммуникаций для вашей организации](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="8e69a-116">To do this see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

> [!TIP]
> <span data-ttu-id="8e69a-117">Можно настроить переадресацию звонков для оператора или пункт меню, который является Online пользователя с **Телефонной системой** лицензии, необходимо включить их для корпоративной голосовой связи или назначить им вызов планы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e69a-117">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them.</span></span> <span data-ttu-id="8e69a-118">В разделе [Назначение Скайп для бизнеса лицензий](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) или [группами Майкрософт назначение лицензий](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="8e69a-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="8e69a-119">Кроме того, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e69a-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="8e69a-120">Например выполните:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="8e69a-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="8e69a-121">Шаг 2. Создание нового автосекретаря</span><span class="sxs-lookup"><span data-stu-id="8e69a-121">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e69a-122">Каждые автосекретаря необходимо иметь связанной [учетной записи ресурса](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="8e69a-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="8e69a-123">Сначала необходимо создать учетную запись ресурса, а затем связать автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8e69a-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8e69a-124">С помощью центра администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8e69a-124">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="8e69a-125">**Центр администрирования группами Майкрософт**, нажмите кнопку **голосовой связи** > **автосекретари**, нажмите кнопку **+ New**:</span><span class="sxs-lookup"><span data-stu-id="8e69a-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="8e69a-126">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="8e69a-126">General info page</span></span>

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Номер 1](media/sfbcallout1.png)

<span data-ttu-id="8e69a-129">**Имя** Введите понятное отображаемое имя вашего автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8e69a-129">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="8e69a-130">Имя является обязательным и может содержать до 64 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="8e69a-130">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="8e69a-131">Оно будет указано в столбце **Имя** на вкладке **Автосекретари**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-131">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Номер 2](media/sfbcallout2.png)

<span data-ttu-id="8e69a-133">**Учетная запись ресурса** Нажмите эту кнопку, чтобы выбрать одну или несколько записей ресурсов для подключения к вашей автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="8e69a-133">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="8e69a-134">Все автосекретари должны иметь учетную запись связанных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8e69a-134">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="8e69a-135">Учетная запись ресурса может иметь номер телефона, связанный со учетной записи, но это не всегда возможно.</span><span class="sxs-lookup"><span data-stu-id="8e69a-135">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="8e69a-136">Автосекретарь верхнего уровня обычно есть учетная запись ресурса с номером телефона назначенный, но вложенных автосекретаря (использовать в качестве первого уровня автосекретаря подключается к меню уровень 2) может не иметь номер телефона, назначенных его учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="8e69a-136">A top-level auto attendant usually have a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

![Номер 3](media/sfbcallout3.png)

<span data-ttu-id="8e69a-p108">**Часовой пояс**. Укажите часовой пояс для функции автосекретаря. Он не обязательно должен совпадать с часовым поясом, соответствующим указанному для вашей организации основному адресу. Для каждого автосекретаря можно указать свой часовой пояс, на основе которого в каждом конкретном случае будут установлены соответствующие рабочие часы.</span><span class="sxs-lookup"><span data-stu-id="8e69a-p108">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization. Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![Номер 4](media/sfbcallout4.png)

<span data-ttu-id="8e69a-141">**Язык** Выберите язык, который будет использоваться для вашей автосекретаря из любого из списка доступных языков.</span><span class="sxs-lookup"><span data-stu-id="8e69a-141">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="8e69a-142">Язык, здесь — это язык, автосекретаря используется для взаимодействия с пользователями, вызов для этот автосекретарь, и все запросы на системы будет воспроизводиться на этом языке.</span><span class="sxs-lookup"><span data-stu-id="8e69a-142">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

![Номер 5](media/sfbcallout5.png)

<span data-ttu-id="8e69a-144">**Оператор**Это дополнительная функция, которая является необязательной для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8e69a-144">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="8e69a-145">Тем не менее можно задать параметр **оператора** для людей, вызвать в должны иметь возможность разорвать меню говорить человека, помогая им.</span><span class="sxs-lookup"><span data-stu-id="8e69a-145">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="8e69a-146">Оператору автоматически назначается клавиша 0.</span><span class="sxs-lookup"><span data-stu-id="8e69a-146">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="8e69a-147">Если этот параметр настроен, вам нужно будет сообщить вызывающим абонентам о том, что он доступен в разделе **"Редактировать параметры меню"** на странице **"Обработка вызовов в рабочее время"**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-147">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="8e69a-148">Если оператор для вашего автосекретаря настроен, вам необходимо ввести соответствующий текст подсказки в поле **"Текст для вызывающих абонентов"** или изменить звуковой файл с учетом этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8e69a-148">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="8e69a-149">Например, "Чтобы связаться с оператором, нажмите ноль".</span><span class="sxs-lookup"><span data-stu-id="8e69a-149">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="8e69a-150">Для выбора в качестве оператора доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="8e69a-150">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="8e69a-151">**Сотрудник компании**, имеющий лицензию на**телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e69a-151">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="8e69a-152">**Сотрудник компании** может быть онлайн-пользователем или пользователем, находящимся на территории локального предприятия и использующим Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e69a-152">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="8e69a-153">**Вызов очереди** , настройки.</span><span class="sxs-lookup"><span data-stu-id="8e69a-153">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="8e69a-154">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="8e69a-154">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="8e69a-155">Для этого выберите **лицо в вашей компании** и звонки этого пользователя будет переадресован непосредственно на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="8e69a-155">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Номер 6](media/sfbcallout6.png)

<span data-ttu-id="8e69a-157">**Включение речевой ввод** Распознавание речи доступен, если выбран этот параметр.</span><span class="sxs-lookup"><span data-stu-id="8e69a-157">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="8e69a-158">Люди, вызвать в можно использовать голосовой ввод [языка, заданную вами](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8e69a-158">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="8e69a-159">Распознавание речи можно отключить, установив отключить, чтобы только позволяют использовать свои клавиатуру телефона.</span><span class="sxs-lookup"><span data-stu-id="8e69a-159">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="8e69a-160">После завершения выбора, щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-160">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="8e69a-161">Страница рабочих часов</span><span class="sxs-lookup"><span data-stu-id="8e69a-161">Business hours page</span></span>

<span data-ttu-id="8e69a-162">По умолчанию устанавливаются 9: 00 до 17: 00 понедельника по пятницу рабочих часов.</span><span class="sxs-lookup"><span data-stu-id="8e69a-162">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="8e69a-163">Все часы, которые не включены в часы работы, считаются нерабочим временем.</span><span class="sxs-lookup"><span data-stu-id="8e69a-163">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="8e69a-164">Можно щелкнуть **выберите 24/7** , чтобы сделать все часов рабочих часов.</span><span class="sxs-lookup"><span data-stu-id="8e69a-164">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="8e69a-165">Если вы выбрали параметр **выберите 24/7** , страницы **после часов вызова параметры** будут используется для настройки обработки для после рабочих часов для автосекретаря звонков.</span><span class="sxs-lookup"><span data-stu-id="8e69a-165">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Номер 1](media/sfbcallout1.png)

<span data-ttu-id="8e69a-168">По умолчанию устанавливаются рабочих часов понедельник-пятница, 9:00:00 - 17:00:00.</span><span class="sxs-lookup"><span data-stu-id="8e69a-168">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="8e69a-169">Параметр **снимите все часы** снимите флажок все часы часов в расписании.</span><span class="sxs-lookup"><span data-stu-id="8e69a-169">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="8e69a-170">Когда вы выбираете **Восстановить значения по умолчанию**, понедельник-пятница, 9:00:00 - 17:00 по восстановит рабочих часов.</span><span class="sxs-lookup"><span data-stu-id="8e69a-170">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Номер 2](media/sfbcallout2.png)

<span data-ttu-id="8e69a-172">Чтобы изменить рабочие часы, выделите часы, которые нужно установить, с помощью календаря.</span><span class="sxs-lookup"><span data-stu-id="8e69a-172">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="8e69a-173">Календарь позволяет выбрать рабочих часов в 30-минутный интервалов и рабочих часов, здесь задается в соответствии часовой пояс, установленной на странице " **Общие сведения** ".</span><span class="sxs-lookup"><span data-stu-id="8e69a-173">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="8e69a-174">Чтобы задать перерыв, например обеденное время, отмените выбор соответствующих часов в календаре.</span><span class="sxs-lookup"><span data-stu-id="8e69a-174">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="8e69a-175">Можно установить несколько разрывов в рамках рабочих часов.</span><span class="sxs-lookup"><span data-stu-id="8e69a-175">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="8e69a-176">После завершения выбора, щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-176">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="8e69a-177">Параметры вызова рабочих часов</span><span class="sxs-lookup"><span data-stu-id="8e69a-177">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="8e69a-178">При использовании расписания настраиваемых рабочих часов, также необходимо настроить вызова обработки нерабочие часы, с помощью страницы **после часов обработка звонков** , который будет предоставить те же параметры, как **Параметры вызова рабочих часов**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-178">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="8e69a-179">Можно настроить приветствие, приглашения и меню, пользователей, которые вызова в номер телефона автосекретаря вашей организации будет воспроизводить рабочего времени.</span><span class="sxs-lookup"><span data-stu-id="8e69a-179">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="8e69a-180">![Обработка звонков рабочих часов. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
 ![Рабочих часов, продолжение обработки звонков.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="8e69a-180">![Business hours call handling.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Business hours call handling continued.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Номер 1](media/sfbcallout1.png)

<span data-ttu-id="8e69a-182">**Приветствия** Приветствие для рабочих часов является необязательной и может быть установлено **не приветствие**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-182">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="8e69a-183">В этом случае вызывающего услышите не сообщение или приветствие перед вызов обрабатывается с помощью одного из указанных действий, которые вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="8e69a-183">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="8e69a-184">Вы также можете загрузить аудиофайл (в формате WAV, mp3 или WMA) или создать настраиваемое приветствие, используя функцию преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="8e69a-184">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="8e69a-185">**Нет приветствие** Нет приветствие будет воспроизводиться при людей вызов номер телефона автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8e69a-185">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="8e69a-186">**Загрузить аудиофайл** Если выбран этот параметр, запишите приветствие и загрузите полученный звуковой файл (в формате WAV, .mp3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="8e69a-186">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="8e69a-187">**Тип сообщения приветствия** Если выбран этот параметр, введите текст, который будет системы для чтения (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="8e69a-187">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="8e69a-188">Например, можно ввести "Вас приветствует Contoso.</span><span class="sxs-lookup"><span data-stu-id="8e69a-188">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="8e69a-189">Ваш звонок очень важен для нас."</span><span class="sxs-lookup"><span data-stu-id="8e69a-189">Your call is important to us."</span></span> <span data-ttu-id="8e69a-190">в поле **Текст для вызывающих абонентов**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-190">in the **Callers will hear** box.</span></span>

* * *

![Номер 2](media/sfbcallout2.png)

<span data-ttu-id="8e69a-192">Вы можете выбрать, как будут обрабатываться звонки, поступающие в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="8e69a-192">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="8e69a-193">Можно выбрать один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="8e69a-193">You can chose from the following actions:</span></span>

- <span data-ttu-id="8e69a-194">**Отключить** Если выбран этот параметр, вызывающий абонент будет отключен после прослушивания приветствия в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="8e69a-194">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="8e69a-195">**Переадресовать звонок** Этот параметр можно использовать для автоматической переадресации вызова, используя следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8e69a-195">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="8e69a-196">**Лица в компании** с **Телефонной системой** лицензии, который включен для корпоративной голосовой связи или назначенных вызов планы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e69a-196">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="8e69a-197">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="8e69a-197">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="8e69a-198">Для этого выберите **лицо в компании** и установите их переадресация на голосовую почту напрямую звонков этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="8e69a-198">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="8e69a-199">**Лица в компании** может быть Online пользователя или пользователь размещенных в локальной с помощью Скайп for Business Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e69a-199">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="8e69a-200">Другой **автосекретаря**</span><span class="sxs-lookup"><span data-stu-id="8e69a-200">Another **Auto attendant**</span></span>

   <span data-ttu-id="8e69a-201">Существующего автосекретаря можно использовать для создания второго уровня параметры меню, содержащий подменю.</span><span class="sxs-lookup"><span data-stu-id="8e69a-201">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="8e69a-202">Эти функции называются вложенными автосекретарями.</span><span class="sxs-lookup"><span data-stu-id="8e69a-202">These are called nested auto attendants.</span></span> <span data-ttu-id="8e69a-203">Чтобы направить звонок в вложенных автосекретаря, выберите **лицо в компании** и назначьте учетной записи ресурса, введите одно с уже автосекретарю связанного или одного, которое будет связать автосекретарю. После завершения работы Создание этот автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="8e69a-203">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="8e69a-204">**Меню Параметры воспроизведения** можно использовать также можно настроить в строке, который будет воспроизводиться.</span><span class="sxs-lookup"><span data-stu-id="8e69a-204">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Номер 3](media/sfbcallout3.png)

<span data-ttu-id="8e69a-206">**Строка меню** Чтобы создать приглашение главного меню, можно использовать преобразования текста в речь или загрузки аудиофайла (формате WAV, .mp3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="8e69a-206">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="8e69a-207">Можно ввести строке в поле **набор вашей навигации по меню для абонентов** или запишите звуковой файл и скажем, например: «для продаж, сказать или нажмите клавишу или сказать 1.</span><span class="sxs-lookup"><span data-stu-id="8e69a-207">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="8e69a-208">Для служб нажмите клавишу или сказать 2.</span><span class="sxs-lookup"><span data-stu-id="8e69a-208">For Services, press or say 2.</span></span> <span data-ttu-id="8e69a-209">Для поддержки клиентов нажмите клавишу или сказать 3.</span><span class="sxs-lookup"><span data-stu-id="8e69a-209">For Customer Support, press or say 3.</span></span> <span data-ttu-id="8e69a-210">Для оператора нажмите клавишу или сказать 0.</span><span class="sxs-lookup"><span data-stu-id="8e69a-210">For the operator, press or say 0.</span></span> <span data-ttu-id="8e69a-211">Чтобы прослушать это меню еще раз, нажмите кнопку "звезда" или сказать повторять.»</span><span class="sxs-lookup"><span data-stu-id="8e69a-211">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="8e69a-212">**Тип сообщения приветствия** Если включено, необходимо ввести текст, который будет системы для чтения (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="8e69a-212">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="8e69a-213">**Загрузки аудиофайла** Если включено, необходимо записать приветствие, а затем загрузите вашей звуковой файл (в формате формате WAV, mp3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="8e69a-213">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Номер 4](media/sfbcallout4.png)

<span data-ttu-id="8e69a-215">**Меню параметров установки** Можно добавлять или удалять параметры меню с помощью ключа кнопок на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="8e69a-215">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="8e69a-216">Добавление пункта меню, нажмите клавишу **+ Назначение клавиш вызова**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-216">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="8e69a-217">Соответствующей строки параметры будут отображаться ниже.</span><span class="sxs-lookup"><span data-stu-id="8e69a-217">A corresponding row of options will appear below.</span></span> <span data-ttu-id="8e69a-218">Для удаления пункта меню, просто щелкните слева от соответствующей клавиши на клавиатуре клавиши управления и щелкните значок «Удалить» выше.</span><span class="sxs-lookup"><span data-stu-id="8e69a-218">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="8e69a-219">Строка сопоставления клавиш будет удалена.</span><span class="sxs-lookup"><span data-stu-id="8e69a-219">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="8e69a-220">Необходимо обновить текст приглашения в меню или повторно отдельно записи звука при добавлении удаление параметров, так как он не будет сделано автоматически для существующей строке меню.</span><span class="sxs-lookup"><span data-stu-id="8e69a-220">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="8e69a-221">Любые параметры меню можно добавлять и удалять в любом порядке, при этом сопоставления клавиш необязательно должны быть последовательными.</span><span class="sxs-lookup"><span data-stu-id="8e69a-221">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="8e69a-222">Например, можно создать меню с помощью сопоставления с параметрами клавиш 0, 1 и 3, при этом клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="8e69a-222">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="8e69a-223">Ключи \* (Повторить) и \# (назад) зарезервированы системой и не может быть переназначить.</span><span class="sxs-lookup"><span data-stu-id="8e69a-223">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="8e69a-224">Если включен параметр распознавания речи, нажатие клавиши \* соответствует голосовой команде "Повтор", а нажатие клавиши # — голосовой команде "Назад".</span><span class="sxs-lookup"><span data-stu-id="8e69a-224">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="8e69a-225">Чтобы настроить параметры меню, после выбора ключи звонков, необходимо:</span><span class="sxs-lookup"><span data-stu-id="8e69a-225">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="8e69a-226">Введите **команду голосовой связи** параметра.</span><span class="sxs-lookup"><span data-stu-id="8e69a-226">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="8e69a-227">Это может быть длиной до 64 символов и может содержать несколько слов, например, «Обслуживание клиентов» или «операций и основанием.»</span><span class="sxs-lookup"><span data-stu-id="8e69a-227">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="8e69a-228">Если включена функция распознавания речи, имя будет распознаваться автоматически, а вызывающий абонент сможет нажать клавишу 3, сказать «три» или «обслуживание клиентов», чтобы выбрать параметр, закрепленный за клавишей 3.</span><span class="sxs-lookup"><span data-stu-id="8e69a-228">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="8e69a-229">Выберите, где звонок отправляется Если нажата соответствующий ключ или выбран параметр распознавание речи.</span><span class="sxs-lookup"><span data-stu-id="8e69a-229">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="8e69a-230">Кому можно направить вызов:</span><span class="sxs-lookup"><span data-stu-id="8e69a-230">The call can be sent to:</span></span>

  - <span data-ttu-id="8e69a-231">**Оператор** Если параметр "Оператор" уже настроен, он автоматически сопоставляется с клавишей 0, но его можно также удалить или закрепить за другой клавишей.</span><span class="sxs-lookup"><span data-stu-id="8e69a-231">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="8e69a-232">Если связь с оператором не закреплена за какой-либо клавишей, то голосовая команда "Оператор" также будет отключена.</span><span class="sxs-lookup"><span data-stu-id="8e69a-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="8e69a-233">**Сотрудник компании**, имеющий лицензию на**телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e69a-233">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="8e69a-234">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="8e69a-234">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="8e69a-235">Для этого выберите **лица в вашей компании** и установите их переадресация на голосовую почту напрямую звонков этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="8e69a-235">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="8e69a-236">**Сотрудник компании** может быть онлайн-пользователем или пользователем, находящимся на территории локального предприятия и использующим Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e69a-236">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 
    - <span data-ttu-id="8e69a-237">Другой **автосекретаря**</span><span class="sxs-lookup"><span data-stu-id="8e69a-237">Another **Auto attendant**</span></span>

       <span data-ttu-id="8e69a-238">Существующего автосекретаря можно использовать для создания второго уровня параметры меню, содержащий подменю.</span><span class="sxs-lookup"><span data-stu-id="8e69a-238">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="8e69a-239">Эти функции называются вложенными автосекретарями.</span><span class="sxs-lookup"><span data-stu-id="8e69a-239">These are called nested auto attendants.</span></span> <span data-ttu-id="8e69a-240">Чтобы направить звонок в вложенных автосекретаря, выберите **лицо в компании** и назначьте учетной записи ресурса, введите одно с уже автосекретарю связанного или одного, которое будет связать автосекретарю. После завершения работы Создание этот автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="8e69a-240">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="8e69a-241">Также будет использоваться **время работы** вложенных автосекретарей (автосекретарей второго уровня), в том числе для вызовов, переадресуемых с других настроенных автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="8e69a-241">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Номер 5](media/sfbcallout5.png)

<span data-ttu-id="8e69a-243">**Вызов по имени** Выбор этого параметра позволяет вызывающим абонентам выполнить поиск сотрудников организации, используя функцию поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="8e69a-243">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="8e69a-244">Вы можете выбрать, каких пользователей можно вызвать, используя функцию "Вызов по имени", а каких — нет, настроив эти параметры на странице **Область вызова.**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-244">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="8e69a-245">Используя функцию "Вызов по имени", можно найти любого онлайн-пользователя с лицензией на**телефонную систему**или локального пользователя, использующего Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e69a-245">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.</span></span>


* * *

<span data-ttu-id="8e69a-246">После завершения выбора, щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-246">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="8e69a-247">Параметры звонка праздничных дней</span><span class="sxs-lookup"><span data-stu-id="8e69a-247">Holiday call settings</span></span>

<span data-ttu-id="8e69a-248">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8e69a-248">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="8e69a-249">Можно перейти экрана в **масштабе организации параметры** > **праздники** для создания праздничных дней, или можно создавать их в ходе создания нового обработчика вызова.</span><span class="sxs-lookup"><span data-stu-id="8e69a-249">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Настройка праздников в автосекретаре](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Номер 1](media/sfbcallout1.png)

<span data-ttu-id="8e69a-252">Если вы уже создали других автосекретари, может появиться параметр можно использовать или изменить в, что вам нужно для этого списка.</span><span class="sxs-lookup"><span data-stu-id="8e69a-252">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="8e69a-253">В противном случае вам потребуется создать новый обработчик вызова.</span><span class="sxs-lookup"><span data-stu-id="8e69a-253">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="8e69a-254">Чтобы добавить новый обработчик звонок, щелкните **+ New вызывать обработчик**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-254">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Настройка праздники в автосекретарь (продолжение)](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Номер 1](media/sfbcallout1.png)

<span data-ttu-id="8e69a-257">В новом окне введите имя нового обработчика вызова в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="8e69a-257">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Номер 2](media/sfbcallout2.png)

<span data-ttu-id="8e69a-259">Если имя праздников уже существует в раскрывающемся списке **праздников** , можно использовать его.</span><span class="sxs-lookup"><span data-stu-id="8e69a-259">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="8e69a-260">Если имя праздничных дней, которое требуется еще не существует, выберите **Создать новый праздничных дней** в раскрывающемся списке и назначить имя и дату нового праздника, которое отображается на странице новое.</span><span class="sxs-lookup"><span data-stu-id="8e69a-260">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="8e69a-261">Щелкните **Сохранить** , когда все будет готово.</span><span class="sxs-lookup"><span data-stu-id="8e69a-261">Click on **Save** when ready.</span></span>

<span data-ttu-id="8e69a-262">Имена праздников могут содержать до 64 знаков; каждое имя праздника одного автосекретаря должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="8e69a-262">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="8e69a-263">Например, нельзя создать для одного автосекретаря два праздника с именем "День Благодарения".</span><span class="sxs-lookup"><span data-stu-id="8e69a-263">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Номер 3](media/sfbcallout3.png)

<span data-ttu-id="8e69a-265">**Приветствия** Приветствие является необязательной и может быть установлено **не приветствие**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-265">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="8e69a-266">В этом случае вызывающий абонент не услышит никакого сообщения или приветствия, пока вызов не будет обработан с использованием одного из выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="8e69a-266">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="8e69a-267">Вы также можете загрузить аудиофайл (в формате WAV, mp3 или WMA) или создать настраиваемое приветствие, используя функцию преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="8e69a-267">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="8e69a-268">**Нет приветствие** Нет приветствие будет воспроизводиться при людей вызов номер телефона автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8e69a-268">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="8e69a-269">**Загрузки аудиофайла** Если выбрать, запишите праздничное приветствие, а затем загрузите вашей звуковой файл (в формате WAV, .mp3 или WMA format)</span><span class="sxs-lookup"><span data-stu-id="8e69a-269">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="8e69a-270">**Тип сообщения приветствия** Если выбран этот параметр, введите текст, который будет системы для чтения (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="8e69a-270">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="8e69a-271">Например, вы можете ввести текст "Поздравляем с новым годом!</span><span class="sxs-lookup"><span data-stu-id="8e69a-271">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="8e69a-272">Наш офисы сейчас закрыты."</span><span class="sxs-lookup"><span data-stu-id="8e69a-272">Our offices are currently closed."</span></span> <span data-ttu-id="8e69a-273">в поле **Тип приветственное сообщение** .</span><span class="sxs-lookup"><span data-stu-id="8e69a-273">in the **Type a greeting message** box.</span></span>

![Номер 4](media/sfbcallout4.png)

<span data-ttu-id="8e69a-275">**Действия** Вы можете выбрать, что происходит с звонки, поступающие во время этого выходные дни.</span><span class="sxs-lookup"><span data-stu-id="8e69a-275">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="8e69a-276">Возможен выбор одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="8e69a-276">You can chose from the following options:</span></span>

- <span data-ttu-id="8e69a-277">**Отключить** Вызывающий абонент будет отключен после прослушивания праздничного приветствия.</span><span class="sxs-lookup"><span data-stu-id="8e69a-277">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="8e69a-278">**Переадресовать звонок** Этот параметр можно использовать для автоматической переадресации вызова, используя следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8e69a-278">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="8e69a-279">**Сотрудник компании**, имеющий лицензию на **телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e69a-279">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="8e69a-280">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="8e69a-280">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="8e69a-281">Для этого выберите **лицо в вашей компании**и задать этого пользователя их вызовы направляться непосредственно на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="8e69a-281">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="8e69a-282">**Сотрудник компании** может быть онлайн-пользователем или пользователем, находящимся на территории локального предприятия и использующим Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e69a-282">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 

  - <span data-ttu-id="8e69a-283">**Вызов очереди** переключение звонка на существующую очередь звонок, были установлены.</span><span class="sxs-lookup"><span data-stu-id="8e69a-283">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="8e69a-284">Другой **автосекретаря**, создание второго уровня параметры меню, содержащий подменю.</span><span class="sxs-lookup"><span data-stu-id="8e69a-284">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="8e69a-285">Эти функции называются вложенными автосекретарями.</span><span class="sxs-lookup"><span data-stu-id="8e69a-285">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="8e69a-286">По умолчанию все вызовы, поступающие в период праздников, после приветствия (при его наличии) переводятся в режим "Отключить", поэтому если вы хотите изменить этот режим работы, необходимо указать, кому следует переадресовать вызов.</span><span class="sxs-lookup"><span data-stu-id="8e69a-286">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="8e69a-287">Страница "Выбор списка набора"</span><span class="sxs-lookup"><span data-stu-id="8e69a-287">Select dial scope page</span></span>

<span data-ttu-id="8e69a-288">На этой странице можно настроить пользователей, которые в вашей организации будет перечислен в каталоге и доступных абонентских групп по имени, если пользователь, который вызывает вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8e69a-288">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="8e69a-290">![Номер 1](media/sfbcallout1.png) используется параметр **Включить** , у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="8e69a-290">![Number 1](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="8e69a-291">**Все активные пользователи** С помощью этого параметра позволяет всем пользователям в вашей организации, которые будут включены в поиск в каталоге.</span><span class="sxs-lookup"><span data-stu-id="8e69a-291">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="8e69a-292">В список будут включены все онлайн-пользователи с лицензией на **телефонную систему**, а также локальные пользователи, использующие Skype для бизнеса Server 2015 или Lync Server 2013 и имеющие планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e69a-292">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="8e69a-293">**Настраиваемая группа пользователей** Если этот параметр, можно выполнить поиск для группы Office 365, список рассылки или группу безопасности, которые были созданы в вашей организации и людей добавлена для этой группы Office 365, список рассылки или группу безопасности, которые либо **Online пользователи с Лицензия телефонной системы** или размещенных в локальной с помощью Скайп for Business Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e69a-293">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="8e69a-294">Вы можете добавить несколько групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="8e69a-294">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Номер 2](media/sfbcallout2.png)

<span data-ttu-id="8e69a-296">С помощью параметра **исключить** , у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="8e69a-296">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="8e69a-297">**Нет**. Использование этой функции означает, что при поиске по справочнику никакие пользователи не исключаются из списка.   </span><span class="sxs-lookup"><span data-stu-id="8e69a-297">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="8e69a-298">**Настраиваемая группа пользователей** Если используется этот параметр, можно выполнить поиск для группы Office 365, список рассылки или группу безопасности, которые были созданы в вашей организации и всех людей добавлена в эту группу Office 365 списка рассылки или групп безопасности, которые будут исключены из поиск в каталоге.</span><span class="sxs-lookup"><span data-stu-id="8e69a-298">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="8e69a-299">Вы можете добавить несколько групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="8e69a-299">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="8e69a-300">Может потребоваться до 36 часов для их имена, перечисленные в каталоге с помощью вызова по имени распознавания речи нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e69a-300">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="8e69a-301">После ввода обязательных полей и Настройка обработки меню и параметры звонков нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-301">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="8e69a-302">Редактирование и тестирование автосекретари</span><span class="sxs-lookup"><span data-stu-id="8e69a-302">Editing and testing auto attendants</span></span>

<span data-ttu-id="8e69a-303">После сохранения автосекретаря он отображается в списке на странице **Автосекретари**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-303">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="8e69a-304">Это позволит быстро увидеть некоторые параметры, которые были заданы, включая имя, номер телефона, язык и состояние.</span><span class="sxs-lookup"><span data-stu-id="8e69a-304">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="8e69a-305">Если вы хотите внести изменения для автосекретаря, выберите тот автосекретарь и в области действий нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8e69a-305">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="8e69a-306">Можно также быстро выполните тестовый вызов для вашей автосекретаря с помощью кнопки **тестирования** в области действий.</span><span class="sxs-lookup"><span data-stu-id="8e69a-306">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="want-to-know-more"></a><span data-ttu-id="8e69a-307">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="8e69a-307">Want to know more?</span></span>

<span data-ttu-id="8e69a-308">Можно также использовать Windows PowerShell для создания и настройки автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="8e69a-308">You can also use Windows PowerShell to create and set up auto attendants.</span></span>

### <a name="auto-attendant-cmdlets"></a><span data-ttu-id="8e69a-309">Командлеты для работы с автосекретарями</span><span class="sxs-lookup"><span data-stu-id="8e69a-309">Auto attendant cmdlets</span></span>

<span data-ttu-id="8e69a-310">Далее перечислены командлеты, необходимые для управления автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="8e69a-310">Here are the cmdlets that you need to manage an auto attendant.</span></span>

- [<span data-ttu-id="8e69a-311">Новый CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8e69a-311">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="8e69a-312">SET-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8e69a-312">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="8e69a-313">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8e69a-313">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csattendant?view=skype-ps) 
- [<span data-ttu-id="8e69a-314">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="8e69a-314">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="8e69a-315">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8e69a-315">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="8e69a-316">Новый CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="8e69a-316">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [<span data-ttu-id="8e69a-317">Новый CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="8e69a-317">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [<span data-ttu-id="8e69a-318">Новый CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="8e69a-318">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [<span data-ttu-id="8e69a-319">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="8e69a-319">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [<span data-ttu-id="8e69a-320">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="8e69a-320">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [<span data-ttu-id="8e69a-321">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="8e69a-321">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [<span data-ttu-id="8e69a-322">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="8e69a-322">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [<span data-ttu-id="8e69a-323">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="8e69a-323">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="8e69a-324">Новый CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="8e69a-324">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="8e69a-325">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="8e69a-325">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="8e69a-326">Импорт CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="8e69a-326">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="8e69a-327">Новый CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="8e69a-327">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a><span data-ttu-id="8e69a-328">Дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e69a-328">More about Windows PowerShell</span></span>

- <span data-ttu-id="8e69a-329">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="8e69a-329">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8e69a-330">С помощью Windows PowerShell можно управлять группами Майкрософт, с помощью точки администрирования, которые можно упростить повседневной работе, когда у вас есть несколько задач для выполнения и Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e69a-330">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8e69a-331">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="8e69a-331">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="8e69a-332">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8e69a-332">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="8e69a-333">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="8e69a-333">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="8e69a-334">Windows PowerShell имеет много преимуществ в скорости, простоты и повышения производительности по сравнению только с помощью центра администрирования Microsoft 365, например, при внесении изменений параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="8e69a-334">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="8e69a-335">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="8e69a-335">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="8e69a-336">Управление Office 365 с Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e69a-336">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="8e69a-337">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8e69a-337">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="8e69a-338">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8e69a-338">Related topics</span></span>

[<span data-ttu-id="8e69a-339">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="8e69a-339">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="8e69a-340">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="8e69a-340">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="8e69a-341">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="8e69a-341">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="8e69a-342">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="8e69a-342">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="8e69a-343">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="8e69a-343">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="8e69a-344">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="8e69a-344">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  
