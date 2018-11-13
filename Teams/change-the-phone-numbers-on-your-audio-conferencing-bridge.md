---
title: Изменение номеров телефонов для моста аудиоконференций
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: При покупке лицензий аудиоконференций для Skype для бизнеса корпорация Майкрософт предоставит вашей организации мост аудиоконференции . Мост аудиоконференции предоставляет номера телефонов для подключения из различных мест, так что организаторы и участники собрания могут использовать их, чтобы присоединяться к собраниям Skype для бизнеса или Microsoft Teams с помощью телефона.
ms.openlocfilehash: 7bd00f23a54780c94cdebeb413a8897e572ec47d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294863"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="3a5b1-104">Изменение номеров телефонов для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="3a5b1-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="3a5b1-105">При покупке лицензий **Аудиоконференций** корпорации Майкрософт размещается вашей звукового конференц-канала для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-105">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="3a5b1-106">Мост аудиоконференций предоставляет телефонные номера телефонов в разных местах, чтобы Организаторы собраний и участники могут использовать их для присоединения к Скайп для бизнеса или группами Майкрософт собраний с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-106">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="3a5b1-107">В дополнение к телефонных номеров, назначенной конференц-канал, можно [получить дополнительные службы номеров](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (международную и обслуживание бесплатных номеров, используемый для аудиоконференций) из других расположениях и затем их для конференц-связи мост так, чтобы присвоить Разверните узел покрытия для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a5b1-108">Должны иметь возможность отменить роли и назначить номер телефона для конференц-канал, номер телефона должен быть номер «*службы*».</span><span class="sxs-lookup"><span data-stu-id="3a5b1-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="3a5b1-109">Можно просмотреть тип номера — по **голосовой связи** > **телефонных номеров** в устаревший портала и оформленные в столбце **Тип "число"** .</span><span class="sxs-lookup"><span data-stu-id="3a5b1-109">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the legacy portal and looking in the **Number Type** column.</span></span> <span data-ttu-id="3a5b1-110">Необходимо вначале настроить кредиты на связь Office 365, для того, чтобы пользователи, во время общения по мосту, могли звонить на бесплатный номер.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="3a5b1-111">Шаги для назначения нового служебного номера мосту конференц-связи</span><span class="sxs-lookup"><span data-stu-id="3a5b1-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="3a5b1-112">Шаг 1. Назначение нового номера телефона мосту аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="3a5b1-112">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

1. <span data-ttu-id="3a5b1-113">Войдите в Office 365 со своей рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="3a5b1-114">Перейдите в **Центр администрирования Office 365** > **центры администрирования** > **группами & Скайп** > **портала прежних версий** > **голосовой связи** > **телефонных номеров**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-114">Go to **Office 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="3a5b1-115">Выберите номер телефона в списке, затем на панели действий нажмите кнопку **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-115">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="3a5b1-116">На странице **Назначение** щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-116">On the **Assign** page, click **Save**.</span></span>

<span data-ttu-id="3a5b1-117">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-117">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="3a5b1-118">Если вы хотите назначить новый номер по умолчанию для звукового конференц-канала при назначении бесплатный номер службы, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3a5b1-118">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

1. <span data-ttu-id="3a5b1-119">Войдите в Office 365 со своей рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-119">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="3a5b1-120">Перейдите в **Центр администрирования Office 365** > **центры администрирования** > **группами & Скайп** > **собраний** > **Мостов конференции**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-120">Go to **Office 365 admin center** > **Admin centers** > **Teams & Skype** > **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="3a5b1-121">Выделите номер счета службы, который необходимо настроить значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-121">Highlight the service toll number that you want to configure as the default.</span></span>

4. <span data-ttu-id="3a5b1-122">Выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-122">Select **Set as default**.</span></span>

> [!NOTE]
> <span data-ttu-id="3a5b1-123">Новый номер телефона был назначен, даже в том случае, если номер стала новый номер по умолчанию, не изменить номер по умолчанию для существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-123">After a new phone number has been assigned, even if the number became the new default number, the default number for existing users won't change.</span></span> <span data-ttu-id="3a5b1-124">Для установки международную по умолчанию или телефоны, который добавляется организатора собрания приглашения, видеть инструкции для [Групп Майкрософт](set-the-phone-numbers-included-on-invites-in-teams.md) или инструкции по [Скайп для бизнеса в Интернет](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="3a5b1-124">To set the default toll or a toll-free number that is added to an organizer's meeting invites, see the instructions for [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or the instructions for [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span> 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="3a5b1-125">Шаг 2. Изменение номеров телефонов по умолчанию, которые указаны в приглашениях на собрания пользователей (необязательно)</span><span class="sxs-lookup"><span data-stu-id="3a5b1-125">Step 2 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="3a5b1-126">Номера телефонов по умолчанию для пользователя, из них, включенных в свои собрания приглашает при составлении приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-126">The default phone numbers for user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="3a5b1-127">Дополнительные сведения можно [задать телефона, номера, находящимся на приглашает в группах Майкрософт](set-the-phone-numbers-included-on-invites-in-teams.md) или [телефона, номера, находящимся на приглашает в Скайп для бизнеса в Интернет](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="3a5b1-127">For more information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>
  
1. <span data-ttu-id="3a5b1-128">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-128">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="3a5b1-129">Перейдите в **Центр администрирования Office 365** > **центры администрирования** > **группами & Скайп** > **портала прежних версий** > **аудиоконференции** > **пользователей**, а затем выберите пользователей в списке.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-129">Go to the **Office 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Audio conferencing** > **Users**, and select the users on the list.</span></span>

3. <span data-ttu-id="3a5b1-130">Нажмите кнопку **Изменить** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-130">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="3a5b1-131">Под заголовком **Платный номер по умолчанию** или **Бесплатный номер по умолчанию** выберите номер в списке и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-131">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="3a5b1-132">После сохранения изменений новые номера телефонов по умолчанию будут включены в приглашения на новые собрания при их планировании.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-132">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="3a5b1-133">Шаг 3. Обновление существующих приглашений на собрания с помощью службы перемещения собраний (необязательно)</span><span class="sxs-lookup"><span data-stu-id="3a5b1-133">Step 3 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="3a5b1-134">В первых двух шагах потребуется запустить Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-134">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="3a5b1-p107">С помощью службы перемещения собраний можно обновить отправленные приглашения на собрания в организации до изменения номеров телефонов по умолчанию. Дополнительные сведения см. в разделе [Настройка службы переноса собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="3a5b1-p107">Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed. For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="3a5b1-p108">Запустите службу перемещения собраний (MMS) для пользователей, у которых на шаге 2 были изменены номера телефонов по умолчанию. Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3a5b1-p108">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2. To do this, run the following command:</span></span>

```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="3a5b1-p109">Также можно просмотреть состояние перемещения собрания. Когда не останется операций с состоянием  *Ожидает*  или *Выполняется*  , все собрания будут запланированы повторно.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-p109">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="3a5b1-141">Шаги для отмены назначения служебного номера мосту конференц-связи</span><span class="sxs-lookup"><span data-stu-id="3a5b1-141">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="3a5b1-142">После отмены назначения номера телефона мосту конференц-связи пользователи не смогут присоединяться к собраниям с его помощью.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-142">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="3a5b1-143">Так как изменение номера телефона, важно для обновления всех пользователей, которые могут иметь номер телефона как их номер по умолчанию (при его наличии) и обновить их существующие приглашения на собрания перед номером телефона неназначенных из моста аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-143">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="3a5b1-144">Если номер телефона удаляется без обновления пользователей и их собрания, их существующие приглашения на собрания может содержать номер телефона, который не работает для присоединения к собраниям их.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-144">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="3a5b1-145">В первых трех шагах потребуется запустить Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-145">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="3a5b1-146">Чтобы просмотреть, как это сделать, нажмите кнопку [хотели бы узнать, как управлять с помощью Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="3a5b1-146">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="3a5b1-147">Шаг 1 — обновление пользователей, имеющих номер телефона для неназначенных как один из номеров их по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3a5b1-147">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="3a5b1-148">Замените счета по умолчанию или телефоны для всех пользователей, имеющих номер неназначенных как номер по умолчанию и начать процесс изменения расписания свои собрания.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-148">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="3a5b1-149">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3a5b1-149">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="3a5b1-150">Можно также изменить счета по умолчанию или бесплатная числа пользователей в Скайп по центру администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-150">You can also change the default toll or toll-free number of users in the Skype for Business admin center.</span></span> <span data-ttu-id="3a5b1-151">Однако, это не повлечёт за собой автоматическую перепланировку их встреч.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-151">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="3a5b1-152">Для получения дополнительных сведений см [задать телефона, номера, находящимся на приглашает в группах Майкрософт](set-the-phone-numbers-included-on-invites-in-teams.md) или [телефона, номера, находящимся на приглашает в Скайп для бизнеса в Интернет](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="3a5b1-152">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="3a5b1-153">В зависимости от размера организации это может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-153">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="3a5b1-154">Шаг 2. Просмотр состояния перемещения собрания с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a5b1-154">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="3a5b1-155">Будет выполнено всех собраний, когда нет операций в состоянии *ожидания* или *В процессе* .</span><span class="sxs-lookup"><span data-stu-id="3a5b1-155">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="3a5b1-156">Дополнительные сведения о службе перемещения собраний см. в разделе [Настройка службы переноса собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="3a5b1-156">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="3a5b1-157">Шаг 3. Отмена назначения старого номера телефона мосту аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="3a5b1-157">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="3a5b1-158">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-158">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="3a5b1-159">Перейдите в **Центр администрирования Office 365** > **центры администрирования** > **группами & Скайп** > **портала прежних версий** > **голосовой связи** > **телефонных номеров**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-159">Go to the **Office 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="3a5b1-160">Выберите номер телефона в списке, затем на панели действий нажмите кнопку **Отменить назначение**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-160">Select the phone number from the list, and in the Action pane, click **Unassign**.</span></span>

4. <span data-ttu-id="3a5b1-161">В диалоговом окне подтверждения нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-161">In the confirmation window, click **Yes**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3a5b1-162">После отмены назначения номера телефона для моста аудиоконференций, телефонный номер больше не будет доступен пользователям для подключения к новым или существующим собраниям.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3a5b1-163">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a5b1-163">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="3a5b1-164"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="3a5b1-164"></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="3a5b1-165">Проверка готовности Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a5b1-165">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="3a5b1-166">Эти шаги проверки под управлением Windows PowerShell версии 3.0 или выше.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-166">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="3a5b1-167">Введите **меню «Пуск»** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-167">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="3a5b1-168">Введите _Get-Host_ в окне **Windows PowerShell** для проверки версии.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-168">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="3a5b1-p114">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-p114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="3a5b1-172">Необходимо также установить модуль Windows PowerShell для Скайп для бизнеса в Интернет, который позволяет создавать удаленного сеанса Windows PowerShell, который подключается к Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-172">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="3a5b1-173">В этом модуле поддерживается только в 64-разрядных компьютеров и можно загрузить из центра загрузки Майкрософт по [Windows PowerShell модуль для Скайп для бизнеса в Интернет](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="3a5b1-173">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="3a5b1-174">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-174">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="3a5b1-175">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="3a5b1-175">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="3a5b1-176">Запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a5b1-176">To start Windows PowerShell</span></span>

 <span data-ttu-id="3a5b1-177">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3a5b1-177">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="3a5b1-178">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-178">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="3a5b1-179">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3a5b1-179">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="3a5b1-180">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-180">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="3a5b1-181">Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="3a5b1-181">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="3a5b1-182">Экономия времени и автоматизации</span><span class="sxs-lookup"><span data-stu-id="3a5b1-182">Save time and automate</span></span>

<span data-ttu-id="3a5b1-183">Экономия времени благодаря автоматизация этот процесс, можно использовать командлеты **Set-CsOnlineDialInConferencingUserDefaultNumber** или [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) .</span><span class="sxs-lookup"><span data-stu-id="3a5b1-183">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="3a5b1-184">Используйте командлет [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-184">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="3a5b1-185">Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="3a5b1-185">To change the default toll-free number for a user, run:</span></span>

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="3a5b1-186">Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-186">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a5b1-187">Чтобы узнать идентификатор BridgeID, используйте командлет **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-187">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="3a5b1-188">Чтобы задать бесплатный номер 8005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет</span><span class="sxs-lookup"><span data-stu-id="3a5b1-188">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="3a5b1-189">Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию 8005551234 на 8005551239 и автоматически повторно запланировать собрания, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="3a5b1-189">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="3a5b1-190">Чтобы задать бесплатный номер 8005551234 в качестве номера по умолчанию для всех пользователей, находящихся в США, и автоматически повторно запланировать собрания, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="3a5b1-190">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="3a5b1-191">Используемое выше местоположение должно совпадать с контактными данными пользователей, которые указаны в Центре администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-191">The location that is used above needs to match the contact information of user(s) that is set in the Office 365 admin center.</span></span>

## <a name="about-windows-powershell"></a><span data-ttu-id="3a5b1-192">О Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a5b1-192">About Windows PowerShell</span></span>

<span data-ttu-id="3a5b1-193">С помощью Windows PowerShell вы можете управлять пользователями и тем, что им можно и что нельзя делать.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-193">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="3a5b1-194">Windows PowerShell, которые помогут управлять Скайп и Office 365 для бизнеса Online с использованием точки администрирования, которые можно упростить повседневной работе, особенно в том случае, если у вас есть несколько задач для выполнения.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-194">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="3a5b1-195">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="3a5b1-195">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="3a5b1-196">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3a5b1-196">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="3a5b1-197">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="3a5b1-197">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="3a5b1-p118">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3a5b1-p118">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="3a5b1-200">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a5b1-200">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="3a5b1-201">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3a5b1-201">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="3a5b1-202">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3a5b1-202">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="3a5b1-203">See also</span><span class="sxs-lookup"><span data-stu-id="3a5b1-203">Related topics</span></span>
[<span data-ttu-id="3a5b1-204">Изменение параметров моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="3a5b1-204">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
