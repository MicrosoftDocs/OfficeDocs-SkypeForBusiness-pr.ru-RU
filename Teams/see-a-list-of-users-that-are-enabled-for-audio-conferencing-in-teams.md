---
title: Просмотреть список пользователей, для которых включено для аудиоконференции в группах Майкрософт
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как для просмотра списка пользователей в вашей организации, которые разрешены для телефонных конференций из внутри групп Майкрософт. '
ms.openlocfilehash: 9bbdd5fd8536554c942db19c8c9f5ac41789c461
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884449"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="e58dd-103">Просмотреть список пользователей, для которых включено для аудиоконференции в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e58dd-103">See a list of users that are enabled for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="e58dd-104">После включения Microsoft группам пользователей в вашей организации для аудиоконференции можно просмотреть список тех пользователей, которые будут включены.</span><span class="sxs-lookup"><span data-stu-id="e58dd-104">After you have enabled Microsoft Teams users in your organization for Audio Conferencing, you can view the list of those users who have been enabled.</span></span> <span data-ttu-id="e58dd-105">При просмотре списка вы также сможете увидеть тип используемого поставщика услуг аудиоконференций для каждого пользователя в списке, телефонный номер для каждого пользователя по умолчанию, узнать, включены ли динамические идентификаторы конференции для вашей организации, а также статические идентификаторы конференции для аудиоконференций, которые проводят пользователи.</span><span class="sxs-lookup"><span data-stu-id="e58dd-105">When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a><span data-ttu-id="e58dd-106">Просмотр списка пользователей</span><span class="sxs-lookup"><span data-stu-id="e58dd-106">Viewing a list of users</span></span>

- <span data-ttu-id="e58dd-107">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="e58dd-107">In the left navigation, click **Users**.</span></span>


## <a name="what-else-should-i-know"></a><span data-ttu-id="e58dd-108">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e58dd-108">What else should I know?</span></span>

- <span data-ttu-id="e58dd-109">При просмотре списка пользователей, для которых включено, можно выбрать пользователя из списка, чтобы изменить параметры аудиоконференций для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e58dd-109">When you view the list of users that are enabled, you can select a user from the list to edit the audio conferencing settings for that user.</span></span>
    
- <span data-ttu-id="e58dd-110">Если выбрать одного пользователя, у которого в качестве поставщика услуг аудиоконференций указан Майкрософт, вы можете просмотреть телефонный номер по умолчанию, узнать, включены ли динамические идентификаторы конференции для вашей организации, а также сбросить идентификатор конференции для собраний, которые проводит этот пользователь.</span><span class="sxs-lookup"><span data-stu-id="e58dd-110">When you select a single user that is configured to use Microsoft as the audio conferencing provider, you can view the default phone number and whether your organization is enabled for dynamic conference IDs, and you can reset the conference ID for meetings that the user organizes.</span></span>
    
- <span data-ttu-id="e58dd-111">Если выбрать одного пользователя, который пользуется услугами стороннего поставщика аудиоконференций, вы можете просмотреть название стороннего поставщика аудиоконференций, платный телефонный номер и бесплатный телефонный номер (если они настроены).</span><span class="sxs-lookup"><span data-stu-id="e58dd-111">When you select a single user who is configured to use a third-party audio conferencing provider, you can view the name of the audio conferencing provider, the toll phone number, and the toll-free phone number (if they are set up).</span></span>
    
   
- <span data-ttu-id="e58dd-112">Вы можете использовать кнопку поиска, чтобы найти определенного пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="e58dd-112">You can use the search button to search for an individual user in the list.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e58dd-113">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e58dd-113">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e58dd-p102">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="e58dd-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e58dd-117">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="e58dd-117">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e58dd-118">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e58dd-118">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e58dd-119">Дополнительные сведения о Windows PowerShell, [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="e58dd-119">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e58dd-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="e58dd-120">Related topics</span></span>

[<span data-ttu-id="e58dd-121">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="e58dd-121">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
