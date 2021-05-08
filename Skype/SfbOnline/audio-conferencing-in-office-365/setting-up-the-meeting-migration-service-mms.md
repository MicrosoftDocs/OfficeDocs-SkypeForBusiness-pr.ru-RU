---
title: Использование службы переноса собраний (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Служба переноса собраний (MMS) — это служба, которая работает в фоновом режиме и автоматически обновляет Skype для бизнеса и Microsoft Teams собрания для пользователей. Эта служба позволяет пользователям не запускать средство переноса собраний для обновления собраний Skype для бизнеса и Microsoft Teams.
ms.openlocfilehash: 3866a11144ef6566422f4e7478b3e0e63ed4a0c5
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237615"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="4ca69-104">Использование службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="4ca69-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="4ca69-105">Служба переноса собраний (MMS) обновляет существующие собрания пользователя в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="4ca69-105">The Meeting Migration Service (MMS) is a service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="4ca69-106">При миграции пользователя из локальной сети в облако (как в Skype для бизнеса Online, так и в TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="4ca69-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="4ca69-107">Изменение параметров аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="4ca69-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="4ca69-108">Когда пользователь в Сети обновляется только Teams или когда для его режима в TeamsUpgradePolicy задавается SfBwithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="4ca69-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="4ca69-109">При использовании PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ca69-109">When you use PowerShell</span></span> 


<span data-ttu-id="4ca69-110">По умолчанию MMS автоматически активируется в каждом из этих случаев, хотя администраторы могут отключить ее на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="4ca69-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="4ca69-111">Кроме того, администраторы могут запускать перенос собраний вручную с помощью powerShell для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ca69-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="4ca69-112">**Ограничения. Службу** переноса собраний нельзя использовать, если применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="4ca69-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="4ca69-113">Почтовый ящик пользователя находится в Exchange локально.</span><span class="sxs-lookup"><span data-stu-id="4ca69-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="4ca69-114">Пользователь будет перенесен из облака в Skype для бизнеса Server локальной сети.</span><span class="sxs-lookup"><span data-stu-id="4ca69-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>

<span data-ttu-id="4ca69-115">В таких ситуациях конечные пользователи [](https://www.microsoft.com/download/details.aspx?id=51659) могут использовать средство переноса собраний для переноса собственных собраний.</span><span class="sxs-lookup"><span data-stu-id="4ca69-115">In these situations, end users can use the [Meeting Migration Tool](https://www.microsoft.com/download/details.aspx?id=51659) to migrate their own meetings instead.</span></span>

## <a name="how-mms-works"></a><span data-ttu-id="4ca69-116">Как работает MMS</span><span class="sxs-lookup"><span data-stu-id="4ca69-116">How MMS works</span></span>

<span data-ttu-id="4ca69-117">При запуске MMS для данного пользователя запрос на миграцию помещается в очередь.</span><span class="sxs-lookup"><span data-stu-id="4ca69-117">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="4ca69-118">Чтобы избежать каких-либо условий в очереди, запрос в очереди обрабатывается преднамеренно, пока не пролечит по крайней мере 90 минут.</span><span class="sxs-lookup"><span data-stu-id="4ca69-118">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="4ca69-119">После обработки запроса MMS выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4ca69-119">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="4ca69-120">Оно выполняет поиск всех собраний, организованных этим пользователем и запланированных в будущем, в почтовом ящике этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ca69-120">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="4ca69-121">На основе сведений, найденных в почтовом ящике пользователя, оно обновляет или планировать новые собрания в Teams или Skype для бизнеса Online для этого пользователя в зависимости от конкретного сценария.</span><span class="sxs-lookup"><span data-stu-id="4ca69-121">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="4ca69-122">В сообщении электронной почты оно заменяет блок собрания по сети в сведениях о собрании.</span><span class="sxs-lookup"><span data-stu-id="4ca69-122">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="4ca69-123">Обновленная версия собрания отправляется всем получателям собрания от имени организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="4ca69-123">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="4ca69-124">Приглашенные на собрание получат обновление с обновленными координатами собрания в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4ca69-124">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![Блокировка собрания, обновляемого MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="4ca69-126">С момента запуска MMS обычно занимает около 2 часов до переноса собраний пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ca69-126">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="4ca69-127">Однако если у пользователя много собраний, это может занять больше времени.</span><span class="sxs-lookup"><span data-stu-id="4ca69-127">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="4ca69-128">Если MMS столкнулась с ошибкой при переносе одного или нескольких собраний для пользователя, она будет периодически повторить попытку до 9 раз в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="4ca69-128">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="4ca69-129">**Примечания:**</span><span class="sxs-lookup"><span data-stu-id="4ca69-129">**Notes**:</span></span>

- <span data-ttu-id="4ca69-130">При переносе собрания MMS заменяет все сведения в блоке информации о собрании по сети.</span><span class="sxs-lookup"><span data-stu-id="4ca69-130">MMS replaces everything in the online meeting information block when a meeting is migrated.</span></span> <span data-ttu-id="4ca69-131">Если же пользователь изменил этот блок, внесенные им изменения будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="4ca69-131">Therefore, if a user has edited that block, their changes will be overwritten.</span></span> <span data-ttu-id="4ca69-132">Все остальные данные в сведениях о собрании, за исключением этого блока, останутся нетронутыми.</span><span class="sxs-lookup"><span data-stu-id="4ca69-132">Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span> <span data-ttu-id="4ca69-133">Это означает, что все файлы, вложенные в приглашение на собрание, будут по-прежнему включены.</span><span class="sxs-lookup"><span data-stu-id="4ca69-133">This means any files attached to the meeting invite will still be included.</span></span> 
- <span data-ttu-id="4ca69-134">Переносятся только те собрания Skype для бизнеса или Microsoft Teams, которые были запланированы с помощью кнопки **Добавить собрание Skype** в Outlook в Интернете или с помощью надстройки "Собрание Skype" для Outlook.</span><span class="sxs-lookup"><span data-stu-id="4ca69-134">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="4ca69-135">Если пользователь копирует и Skype сведения о собрании по сети из одного собрания в новое, это новое собрание не будет обновлено, так как в исходной службе нет собрания.</span><span class="sxs-lookup"><span data-stu-id="4ca69-135">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="4ca69-136">Содержимое собрания, созданное или присоединенное к собранию (доски, опросы и т. д.), не будет храниться после того, как MMS начнется.</span><span class="sxs-lookup"><span data-stu-id="4ca69-136">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="4ca69-137">Если организаторы собрания заранее прикрепили содержимое к собраниям, после того как MMS начнет работать, его потребуется воссоздать.</span><span class="sxs-lookup"><span data-stu-id="4ca69-137">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="4ca69-138">Ссылки на общие заметки собрания в элементе календаря и в собрании Skype также будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="4ca69-138">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="4ca69-139">Обратите внимание, что фактические заметки к собранию, хранимые в OneNote, по-прежнему будут там; перезаписывается только ссылка на общие заметки.</span><span class="sxs-lookup"><span data-stu-id="4ca69-139">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="4ca69-140">Собрания с числом участников больше 250 (включая организатора) не будут перенесены.</span><span class="sxs-lookup"><span data-stu-id="4ca69-140">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="4ca69-141">Некоторые символы ЮНИКОДа в теле приглашения могут быть неправильно обновлены до одного из следующих специальных символов: и, знаки ,,, 1/2, .</span><span class="sxs-lookup"><span data-stu-id="4ca69-141">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="4ca69-142">Запуск MMS для пользователя</span><span class="sxs-lookup"><span data-stu-id="4ca69-142">Triggering MMS for a user</span></span>

<span data-ttu-id="4ca69-143">В этом разделе описано, что происходит при запуске MMS в каждом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="4ca69-143">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="4ca69-144">При миграции пользователя из локальной сети в облако</span><span class="sxs-lookup"><span data-stu-id="4ca69-144">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="4ca69-145">Изменение параметров аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="4ca69-145">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="4ca69-146">Когда в режиме пользователя в TeamsUpgradePolicy установлено имя TeamsOnly или SfBWithTeamsCollabAndMeetings (с помощью Powershell или портала администрирования Teams)</span><span class="sxs-lookup"><span data-stu-id="4ca69-146">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="4ca69-147">При использовании powerShell используйте Start-CsExMeetingMigration</span><span class="sxs-lookup"><span data-stu-id="4ca69-147">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="4ca69-148">Обновление собраний при помещении локального пользователя в облако</span><span class="sxs-lookup"><span data-stu-id="4ca69-148">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="4ca69-149">Это самый распространенный сценарий, в котором MMS помогает создать более плавный переход для пользователей.</span><span class="sxs-lookup"><span data-stu-id="4ca69-149">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="4ca69-150">Без переноса собраний существующие собрания, организованные пользователем в Skype для бизнеса Server, больше не будут работать после его переноса по сети.</span><span class="sxs-lookup"><span data-stu-id="4ca69-150">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="4ca69-151">Поэтому при использовании средств локального администрирования (или панели управления администратором) для перемещения пользователя в облако существующие собрания автоматически перемещаются в облако следующим `Move-CsUser` образом:</span><span class="sxs-lookup"><span data-stu-id="4ca69-151">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="4ca69-152">Если задан переключатель, собрания переносятся непосредственно в Teams и пользователь будет работать `MoveToTeams` `Move-CsUser` в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="4ca69-152">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="4ca69-153">Для использования этого переключателя требуется Skype для бизнеса Server 2015 с cu8 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="4ca69-153">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="4ca69-154">Эти пользователи по-прежнему могут присоединяться Skype для бизнеса собраний, на которые они могут быть приглашены, используя клиент Skype для бизнеса или приложение Skype для собраний.</span><span class="sxs-lookup"><span data-stu-id="4ca69-154">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="4ca69-155">В противном случае собрания переносются в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4ca69-155">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="4ca69-156">В любом случае, если пользователю была назначена лицензия на аудиоконференцию перед его перемещением в облако, собрания будут создаваться с координатами телефонного связи.</span><span class="sxs-lookup"><span data-stu-id="4ca69-156">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="4ca69-157">Если вы переместите пользователя из локальной службы в облако и предполагаете, что он будет использовать аудиоконференции, перед перемещением пользователя рекомендуется назначить аудиоконференции, чтобы запускалась только одна миграция собрания.</span><span class="sxs-lookup"><span data-stu-id="4ca69-157">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="4ca69-158">Обновление собраний при изменении параметров аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="4ca69-158">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="4ca69-159">В следующих случаях MMS обновляет существующие Skype для бизнеса и Microsoft Teams собрания, чтобы добавить, удалить или изменить координаты телефонного дозвона:</span><span class="sxs-lookup"><span data-stu-id="4ca69-159">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="4ca69-160">Если пользователю назначается или удаляется лицензия на службу аудиоконференций Майкрософт, для этого пользователя не включен сторонний поставщик аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="4ca69-160">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="4ca69-161">При смене поставщика аудиоконференций пользователя с любого другого поставщика на Майкрософт при условии, что пользователю назначена лицензия на аудиоконференцию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ca69-161">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="4ca69-162">Дополнительные сведения см. в том, как назначить Майкрософт поставщиком услуг [аудиоконференций.](./assign-microsoft-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="4ca69-162">For more information, see [Assign Microsoft as the audio conferencing provider](./assign-microsoft-as-the-audio-conferencing-provider.md).</span></span> <span data-ttu-id="4ca69-163">Обратите внимание также, что срок поддержки сторонних поставщиков аудиоконференций [ACP] планируется на 1 апреля 2019 г., как было объявлено [ранее.](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)</span><span class="sxs-lookup"><span data-stu-id="4ca69-163">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md).</span></span>
- <span data-ttu-id="4ca69-164">Если включить или отключить аудиоконференцию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ca69-164">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="4ca69-165">При изменении или сбросе ИД конференции для пользователя, настроенного для использования общедоступных собраний.</span><span class="sxs-lookup"><span data-stu-id="4ca69-165">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="4ca69-166">При переключении пользователя на новый мост аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="4ca69-166">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="4ca69-167">Если номер телефона для моста аудиоконференций не назначен.</span><span class="sxs-lookup"><span data-stu-id="4ca69-167">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="4ca69-168">Это сложный сценарий, который требует дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="4ca69-168">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="4ca69-169">Дополнительные сведения см. в сведениях Об изменении [номеров телефонов](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)на мосте аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="4ca69-169">For more information, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="4ca69-p115">Не все изменения в параметрах аудиоконференции для пользователя приводят к запуску MMS. В частности, MMS не будет обновлять собрания в двух следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="4ca69-p115">Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="4ca69-172">При изменении SIP-адреса организатора собрания (его имени пользователя SIP или домена SIP)</span><span class="sxs-lookup"><span data-stu-id="4ca69-172">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="4ca69-173">При изменении URL-адреса собрания организации с помощью `Update-CsTenantMeetingUrl` команды.</span><span class="sxs-lookup"><span data-stu-id="4ca69-173">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="4ca69-174">Обновление собраний при назначении TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="4ca69-174">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="4ca69-175">По умолчанию перенос собраний запускается автоматически, когда пользователю предоставлен экземпляр `TeamsUpgradePolicy` с или `mode=TeamsOnly` `mode= SfBWithTeamsCollabAndMeetings` .</span><span class="sxs-lookup"><span data-stu-id="4ca69-175">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="4ca69-176">Если вы не хотите переносить собрания при предоставлении любого из этих режимов, укажите (при использовании PowerShell) или с помощью powerShell с помощью этого параметра укажите или сделайте так, чтобы при настройке режима совместной работы пользователя (при использовании Teams портала `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` администрирования).</span><span class="sxs-lookup"><span data-stu-id="4ca69-176">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="4ca69-177">Кроме того, обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="4ca69-177">Also note the following:</span></span>

- <span data-ttu-id="4ca69-178">Перенос собраний вызывается только в том случае, если вы `TeamsUpgradePolicy` предоставили разрешение конкретному пользователю.</span><span class="sxs-lookup"><span data-stu-id="4ca69-178">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="4ca69-179">При предоставлении или на уровне клиента перенос собраний не `TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` вызывается. </span><span class="sxs-lookup"><span data-stu-id="4ca69-179">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="4ca69-180">Пользователю можно предоставить режим TeamsOnly только в том случае, если он находится в сети.</span><span class="sxs-lookup"><span data-stu-id="4ca69-180">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="4ca69-181">Пользователи, которые находятся на локальной основе, должны быть перемещены, `Move-CsUser` как описано выше.</span><span class="sxs-lookup"><span data-stu-id="4ca69-181">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="4ca69-182">Предоставление режима, кроме TeamsOnly или SfBWithTeamsCollabAndMeetings, не преобразует существующие Teams собрания в Skype для бизнеса собрания.</span><span class="sxs-lookup"><span data-stu-id="4ca69-182">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="4ca69-183">Запуск переноса собраний вручную с помощью cmdlet PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ca69-183">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="4ca69-184">Кроме автоматического переноса собраний администраторы могут запускать перенос собраний для пользователя вручную с помощью этого cmdlet `Start-CsExMeetingMigration` .</span><span class="sxs-lookup"><span data-stu-id="4ca69-184">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="4ca69-185">Этот cmdlet очереди запроса на миграцию для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ca69-185">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="4ca69-186">Помимо обязательного параметра требуется два необязательных параметра и , которые позволяют указать, как `Identity` `SourceMeetingType` перенести `TargetMeetingType` собрания:</span><span class="sxs-lookup"><span data-stu-id="4ca69-186">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="4ca69-187">**TargetMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="4ca69-187">**TargetMeetingType:**</span></span>

- <span data-ttu-id="4ca69-188">Использование указывает, что Skype для бизнеса собрания остаются Skype для бизнеса, а Teams собрания остаются Teams `TargetMeetingType Current` собраниях.</span><span class="sxs-lookup"><span data-stu-id="4ca69-188">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="4ca69-189">Однако координаты аудиоконференции могут быть изменены, а все Skype для бизнеса собрания будут перенесены в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4ca69-189">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="4ca69-190">Это значение по умолчанию для TargetMeetingType.</span><span class="sxs-lookup"><span data-stu-id="4ca69-190">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="4ca69-191">Использование указывает на то, что любое существующее собрание необходимо перенести в Teams, независимо от того, где оно находится : в интернете или в Skype для бизнеса локально, независимо от того, требуется ли для аудиоконференции `TargetMeetingType Teams` обновление.</span><span class="sxs-lookup"><span data-stu-id="4ca69-191">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="4ca69-192">**SourceMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="4ca69-192">**SourceMeetingType:**</span></span>
- <span data-ttu-id="4ca69-193">Использование означает, что Skype для бизнеса собрания (как локального, так и сетевого) должны `SourceMeetingType SfB` обновляться.</span><span class="sxs-lookup"><span data-stu-id="4ca69-193">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="4ca69-194">Использование `SourceMeetingType Teams` означает, что Teams только собрания.</span><span class="sxs-lookup"><span data-stu-id="4ca69-194">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="4ca69-195">Использование означает, что Skype для бизнеса и Teams должны `SourceMeetingType All` быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="4ca69-195">Using `SourceMeetingType All` indicates that both Skype for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="4ca69-196">Это значение по умолчанию для SourceMeetingType.</span><span class="sxs-lookup"><span data-stu-id="4ca69-196">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="4ca69-197">В примере ниже показано, как инициировать перенос собраний для пользователей ashaw@contoso.com, чтобы перенести все собрания в Teams.</span><span class="sxs-lookup"><span data-stu-id="4ca69-197">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="4ca69-198">Управление MMS</span><span class="sxs-lookup"><span data-stu-id="4ca69-198">Managing MMS</span></span>

<span data-ttu-id="4ca69-199">С Windows PowerShell вы можете проверить состояние текущей миграции, вручную активировать перенос собраний и полностью отключить ее.</span><span class="sxs-lookup"><span data-stu-id="4ca69-199">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="4ca69-200">Проверка состояния переноса собраний</span><span class="sxs-lookup"><span data-stu-id="4ca69-200">Check the status of meeting migrations</span></span>

<span data-ttu-id="4ca69-201">С помощью `Get-CsMeetingMigrationStatus` этого cmdlet можно проверить состояние переноса собраний.</span><span class="sxs-lookup"><span data-stu-id="4ca69-201">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="4ca69-202">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="4ca69-202">Below are some examples.</span></span>

- <span data-ttu-id="4ca69-203">Чтобы получить сводное состояние всех миграций MMS, запустите следующую команду, которая предоставляет таблионное представление всех штатов миграции:</span><span class="sxs-lookup"><span data-stu-id="4ca69-203">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="4ca69-204">Чтобы получить полные сведения о всех миграциях за определенный период времени, используйте `StartTime` параметры `EndTime` и параметры.</span><span class="sxs-lookup"><span data-stu-id="4ca69-204">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="4ca69-205">Например, следующая команда возвращает полные сведения о всех миграциях, которые были совершены с 1 по 8 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="4ca69-205">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="4ca69-206">Чтобы проверить состояние миграции для определенного пользователя, используйте `Identity` параметр.</span><span class="sxs-lookup"><span data-stu-id="4ca69-206">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="4ca69-207">Например, следующая команда получит состояние переноса для пользователя ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="4ca69-207">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="4ca69-208">Если вы видите, что миграция завершилась сбойом, как можно скорее примите меры для устранения этих проблем, так как пользователи не смогут принимать участие в собраниях, организованных этими пользователями, пока вы не уберите их.</span><span class="sxs-lookup"><span data-stu-id="4ca69-208">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="4ca69-209">Если `Get-CsMeetingMigrationStatus` показана любая миграция в состоянии сбойного выполнения, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4ca69-209">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="4ca69-p126">Определите пользователей, которых затронул сбой. Для получения списка пользователей, которых затронул сбой, и возникших ошибок выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4ca69-p126">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. <span data-ttu-id="4ca69-212">Для каждого затронутого пользователя запустите средство переноса собраний, чтобы вручную перенести свои собрания.</span><span class="sxs-lookup"><span data-stu-id="4ca69-212">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="4ca69-213">Если с помощью средства переноса собраний перенос выполнить все равно не удается, есть два варианта действий.</span><span class="sxs-lookup"><span data-stu-id="4ca69-213">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="4ca69-214">Попросить пользователей создать собрания Skype заново.</span><span class="sxs-lookup"><span data-stu-id="4ca69-214">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="4ca69-215">[Связаться со службой поддержки](/microsoft-365/Admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="4ca69-215">[Contact support](/microsoft-365/Admin/contact-support-for-business-products).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="4ca69-216">Включение и отключение MMS</span><span class="sxs-lookup"><span data-stu-id="4ca69-216">Enabling and disabling MMS</span></span>

<span data-ttu-id="4ca69-217">MMS включена по умолчанию для всех организаций, но ее можно отключить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4ca69-217">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="4ca69-218">Отключить полностью для клиента.</span><span class="sxs-lookup"><span data-stu-id="4ca69-218">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="4ca69-219">Отключить только для изменений, связанных с аудиоконференцией.</span><span class="sxs-lookup"><span data-stu-id="4ca69-219">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="4ca69-220">В этом случае MMS будет по-прежнему работать при переносе пользователя из локальной сети в облако или при предоставлении режима TeamsOnly или SfBWithTeamsCollabAndMeetings в `TeamsUpgradePolicy` режиме .</span><span class="sxs-lookup"><span data-stu-id="4ca69-220">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="4ca69-221">Например, может потребоваться вручную перенести все собрания или временно отключить MMS, внося существенные изменения в параметры аудиоконференции для организации.</span><span class="sxs-lookup"><span data-stu-id="4ca69-221">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="4ca69-222">Чтобы узнать, включена ли MMS для вашей организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4ca69-222">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="4ca69-223">MMS включена, если `MeetingMigrationEnabled` параметр имеет параметр `$true` .</span><span class="sxs-lookup"><span data-stu-id="4ca69-223">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```PowerShell
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="4ca69-224">Чтобы полностью включить или отключить MMS, используйте `Set-CsTenantMigrationConfiguration` эту команду.</span><span class="sxs-lookup"><span data-stu-id="4ca69-224">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="4ca69-225">Например, чтобы отключить MMS, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4ca69-225">For example, to disable MMS, run the following command:</span></span>

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="4ca69-226">Если MMS включена в организации и вы хотите проверить, включена ли она для обновлений аудиоконференции, проверьте значение параметра в выходных `AutomaticallyMigrateUserMeetings` данных из `Get-CsOnlineDialInConferencingTenantSettings` .</span><span class="sxs-lookup"><span data-stu-id="4ca69-226">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="4ca69-227">Чтобы включить или отключить MMS для аудиоконференций, используйте `Set-CsOnlineDialInConferencingTenantSettings` .</span><span class="sxs-lookup"><span data-stu-id="4ca69-227">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="4ca69-228">Например, чтобы отключить MMS для аудиоконференции, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4ca69-228">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="4ca69-229">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4ca69-229">Related topics</span></span>

[<span data-ttu-id="4ca69-230">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="4ca69-230">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="4ca69-231">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="4ca69-231">Move users between on-premises and cloud</span></span>](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
