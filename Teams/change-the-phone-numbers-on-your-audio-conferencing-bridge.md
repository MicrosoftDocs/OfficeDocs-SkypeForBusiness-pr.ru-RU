---
title: Изменение номеров телефонов на мосте аудиоконференции
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Узнайте, как назначить новый номер телефона службы мосту конференц-связи, чтобы расширить покрытие для пользователей.
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918755"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="d1559-103">Изменение номеров телефонов для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="d1559-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="d1559-104">При покупке **лицензий на** аудиоконференцию корпорация Майкрософт размещения моста аудиоконференций для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d1559-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="d1559-105">Мост аудиоконференции предоставляет номера телефонов для телефонного звонка из разных мест, чтобы организаторы и участники собрания могли использовать их для звонков в Skype для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1559-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="d1559-106">Помимо номеров телефонов, уже назначенных мосту аудиоконференции, можно получить дополнительные номера служб [(платные](/microsoftteams/getting-service-phone-numbers) и бесплатные номера, используемые для аудиоконференации) из других мест, а затем назначить их мосту для аудиоконференции, чтобы расширить покрытие для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d1559-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1559-107">Чтобы можно было назначить или отозначить номер телефона для моста conferencing,этот номер должен быть номером службы.</span><span class="sxs-lookup"><span data-stu-id="d1559-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="d1559-108">Тип номера можно узнать в столбце "Тип номера" в Центре администрирования  >   Microsoft Teams. </span><span class="sxs-lookup"><span data-stu-id="d1559-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="d1559-109">Для того чтобы пользователи первыми настроили кредиты на связь Microsoft 365 или Office 365, пользователям нужно набрать бесплатный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="d1559-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="d1559-110">Шаги для назначения нового служебного номера мосту конференц-связи</span><span class="sxs-lookup"><span data-stu-id="d1559-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="d1559-111">Шаг 1. Назначение нового номера телефона мосту аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="d1559-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="d1559-112">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d1559-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d1559-113">В области навигации слева перейдите к номерам  >  **голосовых телефонов.**</span><span class="sxs-lookup"><span data-stu-id="d1559-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="d1559-114">Выберите номер телефона в списке и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="d1559-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="d1559-115">На странице **"Изменение"** в области **"Назначено"** разоберите список и выберите **"Применить мост**  >  **конференций".**</span><span class="sxs-lookup"><span data-stu-id="d1559-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="d1559-116">Шаг 2. Изменение номера телефона по умолчанию для моста конференц-связи (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d1559-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="d1559-117">Номер телефона по умолчанию для моста конференц-связи определяет номер звоня, который будет использоваться при размещении исходячего звонка участником или организатором в рамках собрания.</span><span class="sxs-lookup"><span data-stu-id="d1559-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="d1559-118">В качестве номера по умолчанию для моста conferencing можно установить только платный номер службы. **Бесплатные номера службы нельзя** сделать номером по умолчанию для моста услуг.</span><span class="sxs-lookup"><span data-stu-id="d1559-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="d1559-119">Если вы назначаете платный номер службы и хотите сделать его новым номером по умолчанию для моста аудиоконференций, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d1559-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="d1559-120">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d1559-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d1559-121">В области навигации слева перейдите к мостам  >  **конференц-залов собраний.**</span><span class="sxs-lookup"><span data-stu-id="d1559-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="d1559-122">Выделим платный номер службы, который вы хотите настроить как номер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1559-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="d1559-123">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="d1559-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="d1559-124">Шаг 3. Изменение номеров телефонов по умолчанию, включенных в приглашения на собрания пользователей (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d1559-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="d1559-125">Телефонные номера пользователей по умолчанию включаются в приглашения на собрания при их расписании.</span><span class="sxs-lookup"><span data-stu-id="d1559-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="d1559-126">Дополнительные сведения, в том числе о том, как новым пользователям назначены номера телефонов по умолчанию, см. в настройках телефонных номеров, включенных в приглашения в [Microsoft Teams,](set-the-phone-numbers-included-on-invites-in-teams.md) или в [приложениях Skype](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d1559-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="d1559-127">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d1559-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d1559-128">В области навигации слева  перейдите в меню "Пользователи" и щелкните отображаемого имени нужного пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="d1559-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="d1559-129">Рядом с **кнопкой "Аудиоконференция"** нажмите кнопку "Изменить". </span><span class="sxs-lookup"><span data-stu-id="d1559-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="d1559-130">В **области "Платный номер"** или **"Бесплатный** номер" выберите номер в dropdown и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="d1559-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="d1559-131">После внесения изменений новые номера телефонов по умолчанию будут включены в приглашения организаторов, когда они в следующий раз запланировали новое собрание.</span><span class="sxs-lookup"><span data-stu-id="d1559-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="d1559-132">Шаг 4. Обновление существующих приглашений на собрания с помощью службы переноса собраний (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d1559-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="d1559-133">В первых двух шагах потребуется запустить Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1559-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="d1559-134">Если вы обновили номера телефонов по умолчанию, включенные в приглашения на собрания для некоторых или всех пользователей, вы можете обновить приглашения на собрания, которые уже были отправлены пользователям в вашей организации до изменения номеров телефонов по умолчанию с помощью службы переноса собраний.</span><span class="sxs-lookup"><span data-stu-id="d1559-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="d1559-135">Дополнительные сведения см. [в сведениях о настройке службы переноса собраний (MMS).](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="d1559-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="d1559-p106">Запустите службу перемещения собраний (MMS) для пользователей, у которых на шаге 2 были изменены номера телефонов по умолчанию. Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d1559-p106">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2. To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="d1559-p107">Также можно просмотреть состояние перемещения собрания. Когда не останется операций с состоянием  *Ожидает*  или *Выполняется*  , все собрания будут запланированы повторно.</span><span class="sxs-lookup"><span data-stu-id="d1559-p107">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="d1559-140">Шаги для отмены назначения служебного номера мосту конференц-связи</span><span class="sxs-lookup"><span data-stu-id="d1559-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="d1559-141">После отмены назначения номера телефона мосту конференц-связи пользователи не смогут присоединяться к собраниям с его помощью.</span><span class="sxs-lookup"><span data-stu-id="d1559-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="d1559-142">Так как номер телефона изменяется, важно обновить всех пользователей, которые могут использовать его по умолчанию, и существующие приглашения на собрания до того, как этот номер будет не назначен мосту аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="d1559-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="d1559-143">Если удалить номер телефона, не обновив пользователей и их собрания, существующие приглашения на собрания могут содержать телефонный номер, который не будет работать для присоединения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="d1559-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="d1559-144">В первых трех шагах потребуется запустить Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1559-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="d1559-145">Чтобы узнать, как это сделать, щелкните "Хотите узнать, как управлять с помощью [Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="d1559-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="d1559-146">Шаг 1. Обновление данных пользователей, у которых есть номер телефона, который будет не назначен в качестве одного из номеров по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d1559-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="d1559-147">Замените платный или бесплатный номер по умолчанию для всех пользователей, которым этот номер не назначен, и начните процедуру повторного планирования собраний.</span><span class="sxs-lookup"><span data-stu-id="d1559-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="d1559-148">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d1559-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="d1559-149">Вы также можете изменить платный или бесплатный номер по умолчанию в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1559-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d1559-150">Однако, это не повлечёт за собой автоматическую перепланировку их встреч.</span><span class="sxs-lookup"><span data-stu-id="d1559-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="d1559-151">Дополнительные сведения см. в настройках номеров телефонов, включенных в приглашения [в Microsoft Teams,](set-the-phone-numbers-included-on-invites-in-teams.md) или в [приложениях Skype](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d1559-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d1559-152">В зависимости от размера организации это может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="d1559-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="d1559-153">Шаг 2. Просмотр состояния перемещения собрания с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1559-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="d1559-154">Все собрания будут запланированы повторно после того, как не будут завершены операции в состоянии ожидания или *выполнения.* </span><span class="sxs-lookup"><span data-stu-id="d1559-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="d1559-155">Дополнительные сведения о службе перемещения собраний см. в разделе [Настройка службы переноса собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="d1559-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="d1559-156">Шаг 3. Отмена назначения старого номера телефона мосту аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="d1559-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="d1559-157">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d1559-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d1559-158">На панели навигации слева перейдите в раздел **Голосовая связь** > **Номера телефонов**.</span><span class="sxs-lookup"><span data-stu-id="d1559-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="d1559-159">Если номер телефона бесплатный, выберите его в списке и нажмите кнопку **"Освободить".**</span><span class="sxs-lookup"><span data-stu-id="d1559-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="d1559-160">Если номер телефона является платным, [](https://go.microsoft.com/fwlink/?linkid=2091806) обратитесь в службу поддержки Майкрософт, чтобы он не был назначен.</span><span class="sxs-lookup"><span data-stu-id="d1559-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="d1559-161">Если номер телефона бесплатный, нажмите кнопку **"Да"** в окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="d1559-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d1559-162">После отмены назначения номера телефона для моста аудиоконференций, телефонный номер больше не будет доступен пользователям для подключения к новым или существующим собраниям.</span><span class="sxs-lookup"><span data-stu-id="d1559-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d1559-163">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1559-163">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="d1559-164"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="d1559-164"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="d1559-165">Проверка готовности Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1559-165">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="d1559-166">Эти действия проверяют, что вы работаете Windows PowerShell версии 3.0 или более новой.</span><span class="sxs-lookup"><span data-stu-id="d1559-166">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="d1559-167">Введите **меню «Пуск»** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d1559-167">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="d1559-168">Введите _Get-Host_ в окне **Windows PowerShell** для проверки версии.</span><span class="sxs-lookup"><span data-stu-id="d1559-168">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="d1559-169">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1559-169">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="d1559-170">Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="d1559-170">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="d1559-171">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="d1559-171">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="d1559-172">Также необходимо установить модуль Windows PowerShell Skype для бизнеса Online, который позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d1559-172">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="d1559-173">Этот модуль поддерживается только на 64-битных компьютерах, и его можно скачать из Центра загрузки Майкрософт по Windows PowerShell модуля [Skype для бизнеса Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="d1559-173">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="d1559-174">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="d1559-174">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="d1559-175">Если вам нужно узнать больше, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx)в одном окне Windows PowerShell окна.</span><span class="sxs-lookup"><span data-stu-id="d1559-175">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="d1559-176">Запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1559-176">To start Windows PowerShell</span></span>

 <span data-ttu-id="d1559-177">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d1559-177">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="d1559-178">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d1559-178">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="d1559-179">В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365 с помощью:</span><span class="sxs-lookup"><span data-stu-id="d1559-179">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>

> [!NOTE]
> <span data-ttu-id="d1559-180">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1559-180">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="d1559-181">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d1559-181">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="d1559-182">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d1559-182">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="d1559-183">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или подключение к Skype для бизнеса Online с помощью [Windows PowerShell.](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1559-183">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="d1559-184">Экономия времени и автоматизация</span><span class="sxs-lookup"><span data-stu-id="d1559-184">Save time and automate</span></span>

<span data-ttu-id="d1559-185">Чтобы сэкономить время за счет автоматизации этого процесса, вы можете использовать [cmdlets Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) или **Set-CsOnlineDialInConferencingUserDefaultNumber.**</span><span class="sxs-lookup"><span data-stu-id="d1559-185">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="d1559-186">Используйте командлет [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="d1559-186">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="d1559-187">Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="d1559-187">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="d1559-188">Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="d1559-188">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d1559-189">Чтобы узнать идентификатор BridgeID, используйте командлет **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="d1559-189">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="d1559-190">Чтобы задать бесплатный номер 8005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="d1559-190">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="d1559-191">Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию 8005551234 на 8005551239 и автоматически повторно запланировать собрания, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="d1559-191">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="d1559-192">Чтобы задать бесплатный номер 8005551234 в качестве номера по умолчанию для всех пользователей, находящихся в США, и автоматически повторно запланировать собрания, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="d1559-192">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="d1559-193">Используемая выше информация должна соответствовать контактным данным пользователей, заданная в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1559-193">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d1559-194">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d1559-194">Troubleshooting</span></span>

<span data-ttu-id="d1559-195">**Кнопка "Отостить" недоступна**</span><span class="sxs-lookup"><span data-stu-id="d1559-195">**Unassign button isn't available**</span></span>

<span data-ttu-id="d1559-196">Если вы хотите отопределить номер, но кнопка недоступна, при наведении на нее курсором вы будете перенаправлены в службу поддержки со следующим сообщением: "От моста нельзя отоделить стандартные или общие номера. _Чтобы отоименовать выделенные платные номера, обратитесь в службу поддержки._</span><span class="sxs-lookup"><span data-stu-id="d1559-196">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="d1559-197">Чтобы получить дополнительные сведения о мостах, запустите следующую следующую экономию:</span><span class="sxs-lookup"><span data-stu-id="d1559-197">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="d1559-198">В результатах, кроме других сведений, таких как Identity, Name и Region, также должен быть номер Службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1559-198">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="d1559-199">**Например,** чтобы отоименить номерСлужбы DefaultServiceNumber "8005551234",</span><span class="sxs-lookup"><span data-stu-id="d1559-199">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="d1559-200">О Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1559-200">About Windows PowerShell</span></span>

<span data-ttu-id="d1559-201">С помощью Windows PowerShell вы можете управлять пользователями и тем, что им можно и что нельзя делать.</span><span class="sxs-lookup"><span data-stu-id="d1559-201">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="d1559-202">Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач, особенно если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="d1559-202">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="d1559-203">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="d1559-203">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d1559-204">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d1559-204">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="d1559-205">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="d1559-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="d1559-206">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="d1559-206">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d1559-207">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d1559-207">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d1559-208">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1559-208">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="d1559-209">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d1559-209">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="d1559-210">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d1559-210">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="d1559-211">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d1559-211">Related topics</span></span>
[<span data-ttu-id="d1559-212">Изменение настроек для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="d1559-212">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
