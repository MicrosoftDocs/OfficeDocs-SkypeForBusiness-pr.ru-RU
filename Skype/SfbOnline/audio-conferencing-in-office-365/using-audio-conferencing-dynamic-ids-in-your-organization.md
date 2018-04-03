---
title: С помощью идентификаторы динамических звук конференц-связи в вашей организации
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
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
description: 'Служба конференц-связи звук обновляется для предоставления каждого Скайп для бизнеса и группами Майкрософт собрания с помощью различных конференции идентификаторы. Идентификаторы динамических конференции являются значительно повысить за статического конференции идентификаторы, так как они предоставляют:'
ms.openlocfilehash: 418e6f486b8108791930c7843bfed8bdc56e83ef
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a><span data-ttu-id="ec3ff-104">С помощью идентификаторы динамических звук конференц-связи в вашей организации</span><span class="sxs-lookup"><span data-stu-id="ec3ff-104">Using Audio Conferencing dynamic IDs in your organization</span></span>

<span data-ttu-id="ec3ff-105">Служба конференц-связи звук обновляется для предоставления каждого Скайп для бизнеса и группами Майкрософт собрания с помощью различных конференции идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-105">The Audio Conferencing service is being updated to provide each Skype for Business and Microsoft Teams meeting with different conference IDs.</span></span> <span data-ttu-id="ec3ff-106">Идентификаторы динамических конференции являются значительно повысить за статического конференции идентификаторы, так как они предоставляют:</span><span class="sxs-lookup"><span data-stu-id="ec3ff-106">Dynamic conference IDs are a significant improvement over static conference IDs, because they provide:</span></span>
  
- <span data-ttu-id="ec3ff-107">**Улучшенной безопасности** Конференции идентификаторы являются уникальными для каждого Скайп для бизнеса или группами Майкрософт собрания и создаются при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-107">**Enhanced security** The conference IDs are unique for each Skype for Business or Microsoft Teams meeting and are generated when the meeting is being scheduled.</span></span>
    
- <span data-ttu-id="ec3ff-108">**Улучшенная работа для последовательных и параллельных собраний**. Собрания с одним организатором получают определенные сведения для подключения, которые не дают перепутать использующих телефонные подключения участников одного собрания с участниками другого собрания, если эти собрания запланированы примерно на одинаковое время.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-108">**A better experience for back-to-back and side-to-side meetings** Meetings for a single organizer are given specific dial-in information that prevents phone participants of one meeting from being mixed with participants of another one when they're scheduled next to each other.</span></span>
    
- <span data-ttu-id="ec3ff-109">**Беспроблемный переход**. Если ваша организация поддерживает динамические идентификаторы конференц-связи, все собрания, которые уже были запланированы в вашей организации с использованием статических идентификаторов конференц-связи, останутся активными.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-109">**A seamless transition** When your organization is enabled for dynamic conference IDs, all the meetings that have been already scheduled in your organization with static conference IDs will continue to work.</span></span>
    
> [!TIP]
> <span data-ttu-id="ec3ff-110">Идентификаторы динамических доступны только для пользователей, которым разрешена ** звукового конференц-связи ** и корпорация Майкрософт задаются в виде их поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-110">Dynamic IDs are only available to users who are enabled for ** Audio Conferencing** and have Microsoft set as their audio conferencing provider.</span></span> <span data-ttu-id="ec3ff-111">Вы можете [Назначение Майкрософт в качестве поставщика услуг аудиоконференций](assign-microsoft-as-the-audio-conferencing-provider.md) для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-111">You can [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md) for your users.</span></span>
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a><span data-ttu-id="ec3ff-112">Какие изменения будут видеть пользователи в моей организацией</span><span class="sxs-lookup"><span data-stu-id="ec3ff-112">What changes will the users in my organization see?</span></span>

<span data-ttu-id="ec3ff-113">После включения идентификаторы динамических конференции для вашей организации все новые Скайп для работы или группами Майкрософт, собраний, запланированных пользователями, для которых включена для конференц-связи звук будет проводить конференции идентификаторы, которые будут отличаться от Идентификатор статического конференции, которое они имели до.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-113">After dynamic conference IDs have been enabled for your organization, any new Skype for Business or Microsoft Teams meeting that is scheduled by users in your organization who are enabled for Audio Conferencing will have conference IDs that will be different from the static conference ID they had before.</span></span> <span data-ttu-id="ec3ff-114">Организаторы с статического идентификаторы конференции перед нужно напомнить пользователи, присоединяющиеся к их собрания, которые теперь необходимо использовать новый идентификатор в приглашении на собрание, прежде чем они смогут присоединиться.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-114">Organizers who had static conference IDs before need to remind the users joining their meetings that they now need to use a new conference ID in the meeting's invite before they can join it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec3ff-115">Собрания, которые были помощнику по пользователя с помощью статического конференции идентификаторы до включения для динамического конференции, идентификаторы будет продолжать имеют идентификаторы статического конференции, поэтому они будут продолжать планировать собрания без какого-либо ущерба организации.</span><span class="sxs-lookup"><span data-stu-id="ec3ff-115">Meetings that were scheduled by a user with static conference IDs before the organization was enabled for dynamic conference IDs will continue to have the static conference IDs, so they'll continue to schedule meetings without any impact.</span></span> 
  
<span data-ttu-id="ec3ff-116">В этих примерах показано новой версии интерфейса для двух Скайп для бизнеса собраний, организованные одного пользователя, но будут теперь иметь два разных конференции идентификаторы:</span><span class="sxs-lookup"><span data-stu-id="ec3ff-116">These examples show you the new experience for two Skype for Business meetings that have been organized by the same user but will both now have two different conference IDs:</span></span> 
  
 <span data-ttu-id="ec3ff-117">**Собрание 1** было запланировано с 9:00 до 10:00, его идентификатором конференц-связи является 93907123:</span><span class="sxs-lookup"><span data-stu-id="ec3ff-117">**Meeting #1** has been scheduled from 9:00 AM to 10:00 AM and it has 93907123 as its conference ID:</span></span>
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 <span data-ttu-id="ec3ff-119">**Собрание 2** было запланировано тем же пользователем с 10:00 до 11:00, его идентификатором конференц-связи является 16353789:</span><span class="sxs-lookup"><span data-stu-id="ec3ff-119">**Meeting #2** has been scheduled by the same user from 10:00 AM to 11:00 AM and it has 16353789 as its conference ID:</span></span>
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a><span data-ttu-id="ec3ff-121">See also</span><span class="sxs-lookup"><span data-stu-id="ec3ff-121">Related topics</span></span>

- [<span data-ttu-id="ec3ff-122">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ec3ff-122">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [<span data-ttu-id="ec3ff-123">Лицензирование надстроек Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec3ff-123">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
