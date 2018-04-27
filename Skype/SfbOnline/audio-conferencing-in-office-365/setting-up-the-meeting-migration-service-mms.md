---
title: Настройка службы переноса собраний (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Служба переноса собраний (MMS) \x97 это служба Skype для бизнеса, которая работает в фоновом режиме и автоматически обновляет собрания Skype для бизнеса и Microsoft Teams для пользователей. Эта служба позволяет пользователям не запускать средство переноса собраний для обновления собраний Skype для бизнеса и Microsoft Teams."
ms.openlocfilehash: 3dd85d0e4eb588a916c7c4738c982a888133b3bd
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="3ce31-104">Настройка службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="3ce31-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="3ce31-105">Служба переноса собраний (MMS)  это служба Skype для бизнеса, которая работает в фоновом режиме и автоматически обновляет собрания Skype для бизнеса и Microsoft Teams для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3ce31-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users.</span></span> <span data-ttu-id="3ce31-106">Эта служба позволяет пользователям не запускать средство переноса собраний для обновления собраний Skype для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ce31-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>  <span data-ttu-id="3ce31-107">Это средство не переносятся Скайп для собраний Business участникам собрания групп Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3ce31-107">This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.</span></span>  
  
 <span data-ttu-id="3ce31-108">**Требования**</span><span class="sxs-lookup"><span data-stu-id="3ce31-108">**Requirements**</span></span>
  
<span data-ttu-id="3ce31-109">Для использования MMS почтовые ящики организаторов собрания должны находиться в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3ce31-109">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="3ce31-110">**Основные сценарии**</span><span class="sxs-lookup"><span data-stu-id="3ce31-110">**Primary scenarios**</span></span>
  
<span data-ttu-id="3ce31-111">MMS обновляет собрания Skype для пользователей в следующих двух основных сценариях.</span><span class="sxs-lookup"><span data-stu-id="3ce31-111">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="3ce31-112">Перенос пользователя с локального сервера Skype для бизнеса в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3ce31-112">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="3ce31-113">Изменение администратором параметров аудиоконференции для пользователя, при котором требуется изменение сведений об аудиоконференции в собраниях пользователя.</span><span class="sxs-lookup"><span data-stu-id="3ce31-113">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="3ce31-114">**Распространенные сценарии, в которых невозможно использовать MMS**</span><span class="sxs-lookup"><span data-stu-id="3ce31-114">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="3ce31-p103">Вот несколько распространенных сценариев, которые могут относиться к вашей ситуации. Это все поддерживаемые сценарии переноса. Но в следующих сценариях MMS работать не будет, и вам придется использовать [средство переноса собраний](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="3ce31-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="3ce31-118">Почтовые ящики пользователей расположены на локальном сервере Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="3ce31-118">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="3ce31-119">Использование стороннего поставщика аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="3ce31-119">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="3ce31-120">Перенос пользователей из Skype для бизнеса Online на локальный сервер Skype Server</span><span class="sxs-lookup"><span data-stu-id="3ce31-120">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="3ce31-121">Обновление собраний при переносе локального пользователя в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3ce31-121">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="3ce31-p104">Это наиболее распространенный сценарий, в котором MMS поможет обеспечить более удобный перенос для ваших пользователей. При переносе пользователя c локального сервера Skype для бизнеса в Skype для бизнеса Online MMS обнаружит нового пользователя и проверит календарь этого пользователя на наличие собраний Skype для бизнеса и Microsoft Teams. Во всех будущих собраниях будут заданы обновленные сведения об этом пользователе.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p104">This is the most common scenario where MMS can help create a smoother transition for your users. When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="3ce31-125">Использование сервера Skype Server 2015 для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="3ce31-125">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="3ce31-126">Для наиболее эффективного использования MMS в этом сценарии советуем придерживаться приведенных ниже рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="3ce31-126">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="3ce31-127">Так как для работы MMS необходимо, чтобы почтовый ящик пользователя находился в Exchange Online, то если вы одновременно переносите почтовые ящики с локального сервера Exchange Server, сначала переместите почтовый ящик пользователя в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3ce31-127">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="3ce31-p105">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p105">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="3ce31-131">Использование стороннего поставщика конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="3ce31-131">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="3ce31-p106">Если вы используете сторонний поставщик аудиоконференций, то запуск MMS зависит от параметров аудиоконференций в вашей организации. Вы можете включить автоматическую замену номеров для телефонной связи у поставщика аудиоконференций при назначении пользователю лицензии для **аудиоконференции**. Может потребоваться и другая схема, при которой нужно будет сохранить номера для телефонной связи от поставщика аудиоконференций. Чтобы узнать значение этого параметра для своей организации, запустите следующий командлет Windows PowerShell и проверьте значение параметра  `AutomaticallyReplaceAcpProvider`. Если вам нужна помощь с PowerShell, обратитесь к разделу [Управление организацией Skype для бизнеса с помощью PowerShell](setting-up-the-meeting-migration-service-mms.md#WPSInfo) в конце этой статьи.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p106">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP. To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="3ce31-p107">Если этот параметр имеет значение $true, то при назначении пользователю лицензии для **аудиоконференции** MMS будет запущена и обновит параметры пользователя. Номера для телефонной связи от вашего поставщика аудиоконференций будут сохранены до назначения лицензии для **аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p107">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="3ce31-p108">Если этот параметр имеет значение $false, то MMS не будет обновлять собрания даже при назначении пользователю лицензии для **аудиоконференции**. Номера для телефонной связи от вашего поставщика аудиоконференций будут сохранены до того момента, когда пользователь вручную не будет подготовлен для аудиоконференции в центре администрирования приложения Skype для бизнеса или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p108">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="3ce31-141">Обновление собраний при изменении параметров аудиоконференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="3ce31-141">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="3ce31-142">MMS обновляет существующие собрания Skype для бизнеса Online и Microsoft Teams в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="3ce31-142">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="3ce31-143">При назначении или удалении лицензии для **аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="3ce31-143">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="3ce31-144">При включении или отключении аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="3ce31-144">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="3ce31-145">При изменении или сбросе идентификатора конференции для пользователя, участвующего в общедоступных собраниях.</span><span class="sxs-lookup"><span data-stu-id="3ce31-145">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="3ce31-146">При переключении пользователя на новый мост аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="3ce31-146">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="3ce31-p109">При освобождении номера телефона на мосте аудиоконференции. Это сложный сценарий, который потребует дополнительных действий. Дополнительные сведения см. в разделе [Измените платные или бесплатные номера телефонов для моста аудиоконференций.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="3ce31-p109">When a phone number is unassigned from a audio conferencing bridge. This is a complex scenario which requires additional steps. For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3ce31-p110">MMS обновляет собрания только в том случае, если вы используете мост Майкрософт. При использовании стороннего поставщика аудиоконференций пользователям потребуется обновить свои собрания вручную. В этом случае можно воспользоваться [средством переноса собраний](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="3ce31-p110">MMS only updates meetings when you're using the Microsoft bridge. If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="3ce31-p111">Не все изменения в параметрах аудиоконференции для пользователя приводят к запуску MMS. В частности, MMS не будет обновлять собрания в двух следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="3ce31-p111">Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="3ce31-155">При изменении SIP-адреса организатора собрания (его имени пользователя SIP или домена SIP)</span><span class="sxs-lookup"><span data-stu-id="3ce31-155">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="3ce31-156">При изменении URL-адреса собрания организации с помощью команды [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="3ce31-156">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="3ce31-157">Что делает MMS при обновлении собраний?</span><span class="sxs-lookup"><span data-stu-id="3ce31-157">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="3ce31-158">Когда служба MMS определяет, что необходимо обновить собрания пользователя, она выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3ce31-158">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="3ce31-159">Определение всех собраний Skype для бизнеса и Microsoft Teams, которые пользователь запланировал на будущее</span><span class="sxs-lookup"><span data-stu-id="3ce31-159">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="3ce31-160">Все собрания Skype для бизнеса или Microsoft Teams, произошедшие до запуска MMS, не учитываются.</span><span class="sxs-lookup"><span data-stu-id="3ce31-160">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="3ce31-161">Обновляются только те собрания, организатором которых является пользователь.</span><span class="sxs-lookup"><span data-stu-id="3ce31-161">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="3ce31-162">Замена блока с информацией о собрании в сведениях о собрании</span><span class="sxs-lookup"><span data-stu-id="3ce31-162">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="3ce31-163">Отправка обновлений всем участникам собрания от имени организатора собрания</span><span class="sxs-lookup"><span data-stu-id="3ce31-163">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="3ce31-164">**Сколько времени занимает перенос собраний с помощью MMS?**</span><span class="sxs-lookup"><span data-stu-id="3ce31-164">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="3ce31-p112">Время, которое требуется MMS для переноса собраний, зависит от количества затронутых пользователей и от общего количества собраний Skype для бизнеса или Microsoft Teams в календаре для каждого пользователя. Минимальное время переноса составляет 10 минут. Хотя некоторые объемные операции переноса могут занимать до 12 часов, большинство операций должно завершиться в течение часа.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p112">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. At a minimum, it will take 10 minutes to run. While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="3ce31-168">**Ограничения и возможные проблемы**</span><span class="sxs-lookup"><span data-stu-id="3ce31-168">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="3ce31-p113">Переносятся только те собрания Skype для бизнеса или Microsoft Teams, которые были запланированы с помощью кнопки **Добавить собрание Skype** в Outlook в Интернете или с помощью надстройки "Собрание Skype" для Outlook. Другими словами, если пользователь копирует и вставляет сведения о собрании по сети из одного собрания в другое, это новое собрание не будет обновлено.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p113">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="3ce31-p114">При переносе собрания MMS заменяет все сведения в блоке информации о собрании по сети. Если же пользователь изменил этот блок, внесенные им изменения будут перезаписаны. Все остальные данные в сведениях о собрании, за исключением этого блока, останутся нетронутыми.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="3ce31-p115">Содержимое собрания, которое было создано или присоединено к собранию (доски, опросы и т. д.), не сохранится после переноса с помощью MMS. Если организаторы собрания добавили содержимое к собранию заранее, это содержимое не придется снова создавать после запуска MMS.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="3ce31-p116">Ссылки на общие заметки собрания в элементе календаря и в собрании Skype также будут перезаписаны. Обратите внимание, что сами заметки собрания, которые хранятся в OneNote, останутся там; изменится только ссылка на общие заметки собрания.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="3ce31-179">Собрания с числом участников больше 250 (включая организатора) не будут перенесены.</span><span class="sxs-lookup"><span data-stu-id="3ce31-179">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="3ce31-180">Некоторые символы Юникода в тексте приглашения могут ошибочно заменяться на один из следующих специальных символов: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="3ce31-180">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="3ce31-181">Что увидят пользователи после того, как MMS обновит их собрания?</span><span class="sxs-lookup"><span data-stu-id="3ce31-181">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="3ce31-p117">Как и средство переноса собраний, MMS обновляет собрания от имени пользователей. Поэтому ваши пользователи увидят только принятия приглашений на собрание для своих собраний. Чтобы у пользователей не возникли затруднения, рекомендуем заранее оповещать их не только о переносе пользователей из локальной системы в Skype для бизнеса Online, но и об изменениях параметров аудиоконференции, которые приведут к запуску MMS.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p117">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="3ce31-185">Управление MMS</span><span class="sxs-lookup"><span data-stu-id="3ce31-185">Managing MMS</span></span>

<span data-ttu-id="3ce31-p118">Для управления MMS и проверки состояния операций переноса нужно использовать Windows PowerShell. В этом разделе предполагается, что вы знакомы с использованием PowerShell для управления организацией Skype для бизнеса. Если вам нужна помощь с PowerShell, обратитесь к разделу [Управление организацией Skype для бизнеса с помощью PowerShell](setting-up-the-meeting-migration-service-mms.md#WPSInfo) в конце этой статьи.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="3ce31-189">Как проверить состояние переноса собраний?</span><span class="sxs-lookup"><span data-stu-id="3ce31-189">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="3ce31-p119">Для проверки состояния переноса собраний можно запустить командлет  `Get-CsMeetingMigrationStatus`. Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="3ce31-192">Для получения общего состояния переноса MMS выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3ce31-192">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="3ce31-193">Эта команда выведет состояния всех операций переноса в таблице:</span><span class="sxs-lookup"><span data-stu-id="3ce31-193">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="3ce31-194">Состояние UserCount —</span><span class="sxs-lookup"><span data-stu-id="3ce31-194">State UserCount---------------</span></span><br/> <span data-ttu-id="3ce31-195">Ожидающие 21</span><span class="sxs-lookup"><span data-stu-id="3ce31-195">Pending 21</span></span><br/><span data-ttu-id="3ce31-196">InProgress 6</span><span class="sxs-lookup"><span data-stu-id="3ce31-196">InProgress 6</span></span><br/> <span data-ttu-id="3ce31-197">Сбой 2</span><span class="sxs-lookup"><span data-stu-id="3ce31-197">Failed 2</span></span> <br/> <span data-ttu-id="3ce31-198">Успешных 131</span><span class="sxs-lookup"><span data-stu-id="3ce31-198">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="3ce31-p120">Если вы видите, что некоторые операции переноса завершились сбоем, устраните ошибки как можно быстрее. Пока вы не устраните ошибки, пользователи не смогут присоединяться к собраниям, создаваемым этими пользователями. Дополнительные сведения см. в разделе [Что делать, если произошла ошибка?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="3ce31-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="3ce31-p121">Для получения полных сведений об операциях переноса за определенный период времени воспользуйтесь параметрами  `StartTime` и `EndTime`. Например, следующая команда выведет сведения о всех операциях переноса, которые выполнялись с 1 по 8 октября 2016 г.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="3ce31-p122">Можно также проверить состояние переноса для конкретного пользователя с помощью параметра  `UserId`. Например, следующая команда получит состояние переноса для пользователя ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="3ce31-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="3ce31-206">Что делать, если произошла ошибка?</span><span class="sxs-lookup"><span data-stu-id="3ce31-206">What do I do if there is an error?</span></span>
<span data-ttu-id="3ce31-207"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="3ce31-207"></span></span>

<span data-ttu-id="3ce31-208">Если вы запустили командлет  `Get-CsMeetingMigrationStatus` для получения сведений о состоянии переноса и обнаружили, что некоторые операции переноса находятся в состоянии Сбой, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3ce31-208">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="3ce31-p123">Определите пользователей, которых затронул сбой. Для получения списка пользователей, которых затронул сбой, и возникших ошибок выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3ce31-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="3ce31-211">Для каждого из этих пользователей запустите [средство переноса собраний](https://go.microsoft.com/fwlink/p/?linkid=626047) для переноса собраний этих пользователей вручную.</span><span class="sxs-lookup"><span data-stu-id="3ce31-211">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="3ce31-212">Если с помощью средства переноса собраний перенос выполнить все равно не удается, есть два варианта действий.</span><span class="sxs-lookup"><span data-stu-id="3ce31-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="3ce31-213">Попросить пользователей создать собрания Skype заново.</span><span class="sxs-lookup"><span data-stu-id="3ce31-213">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="3ce31-214">[Связаться со службой поддержки](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="3ce31-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="3ce31-215">Включение и отключение MMS</span><span class="sxs-lookup"><span data-stu-id="3ce31-215">Enabling and disabling MMS</span></span>
<span data-ttu-id="3ce31-216"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="3ce31-216"></span></span>

<span data-ttu-id="3ce31-p124">MMS по умолчанию включена для всех организаций, но при необходимости ее можно отключить. Например, если вы хотите перенести все собрания вручную или пользуетесь сторонним поставщиком аудиоконференций, MMS может не понадобиться. Вы можете также временно отключить MMS. Например, это можно сделать, если вы вносите масштабные изменения в настройках аудиоконференции для вашей организации и не хотите, чтобы MMS запускалась, пока все изменения не будут завершены.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p124">MMS is enabled by default for all organizations, but it can be disabled as needed. For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. You may also choose to temporarily disable MMS. For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="3ce31-p125">Чтобы узнать, включена ли MMS для вашей организации, выполните следующую команду и проверьте значение параметра  `MeetingMigrationEnabled`. Если этот параметр имеет значение $true, MMS включена.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="3ce31-223">Чтобы отключить MMS, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3ce31-223">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="3ce31-224">Чтобы включить MMS, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3ce31-224">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="3ce31-225">Включение и отключение MMS только для изменений параметров аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="3ce31-225">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="3ce31-226"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="3ce31-226"></span></span>

<span data-ttu-id="3ce31-p126">Вы также можете отключить MMS только для изменений параметров аудиоконференции. При этом MMS по-прежнему будет запускаться при переносе локальной системы Skype для бизнеса в Skype для бизнеса Online. Чтобы узнать, включена ли MMS для изменений параметров аудиоконференции, выполните следующую команду и проверьте значение параметра  `AutomaticallyMigrateUserMeetings`. Если этот параметр имеет значение $true, MMS будет запускаться для обновления собраний пользователей при изменении параметров аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p126">You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="3ce31-231">Чтобы отключить MMS для аудиоконференции, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ce31-231">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="3ce31-232">Чтобы включить MMS для аудиоконференции, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3ce31-232">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="3ce31-233">Как вручную запустить перенос собраний?</span><span class="sxs-lookup"><span data-stu-id="3ce31-233">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="3ce31-234"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="3ce31-234"></span></span>

<span data-ttu-id="3ce31-p127">Кроме автоматического переноса собраний, можно также запустить перенос собраний вручную с помощью командлета **Start-CsExMeetingMigration**. Этот командлет добавляет пользователя в очередь переноса собраний. Служба переноса собраний прочтет запрос пользователя и перенесет собрания. Состояние переноса можно проверить с помощью командлета **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p127">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**. This cmdlet adds the user in meeting migration queue. Meeting Migration Service will read the user request and migrate their meetings. You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="3ce31-239">Ниже показан пример, который удаляет перенос собраний для пользователя ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="3ce31-239">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="3ce31-240">Управление организацией Skype для бизнеса с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ce31-240">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="3ce31-241"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="3ce31-241"></span></span>

 <span data-ttu-id="3ce31-242">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="3ce31-242">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="3ce31-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3ce31-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3ce31-244">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="3ce31-244">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="3ce31-p128">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="3ce31-p129">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="3ce31-251">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="3ce31-251">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="3ce31-252">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3ce31-252">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="3ce31-253">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3ce31-253">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3ce31-254">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3ce31-254">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3ce31-255">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3ce31-255">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="3ce31-256">Дополнительные сведения о запуске Windows PowerShell см. в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или[Подключение к Skype для бизнеса с использованием Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="3ce31-256">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="3ce31-p130">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="3ce31-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3ce31-260">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3ce31-260">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3ce31-261">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="3ce31-261">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3ce31-p131">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3ce31-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3ce31-264">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ce31-264">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3ce31-265">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3ce31-265">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3ce31-266">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3ce31-266">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="3ce31-267">See also</span><span class="sxs-lookup"><span data-stu-id="3ce31-267">Related topics</span></span>

[<span data-ttu-id="3ce31-268">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="3ce31-268">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
