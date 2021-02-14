---
title: Известные проблемы планов звонков
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Узнайте об известных проблемах с планом звонков по ЗВОНКОВ по ННР и о том, как с ними работать.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220739"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="853a0-103">Известные проблемы планов звонков</span><span class="sxs-lookup"><span data-stu-id="853a0-103">Calling Plans known issues</span></span>

<span data-ttu-id="853a0-104">Планы звонков — это новая функция Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="853a0-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="853a0-105">Ниже даны текущие вопросы, которые отслеживаются и активно исследуются.</span><span class="sxs-lookup"><span data-stu-id="853a0-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="853a0-106">Они могут быть устранены при обновлении функции в будущих сборках.</span><span class="sxs-lookup"><span data-stu-id="853a0-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="853a0-107">Известные проблемы планов звонков</span><span class="sxs-lookup"><span data-stu-id="853a0-107">Calling Plans known issues</span></span>

|<span data-ttu-id="853a0-108">**Известная проблема**</span><span class="sxs-lookup"><span data-stu-id="853a0-108">**Known issue**</span></span>|<span data-ttu-id="853a0-109">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="853a0-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="853a0-110">При переходе с лицензий на техническую версию на лицензии для планов звонков лицензия не обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="853a0-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="853a0-111">Сначала приобретите новые лицензии, чтобы они были готовы к назначению пользователям.</span><span class="sxs-lookup"><span data-stu-id="853a0-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="853a0-112">Удалите промолилиза (техническую версию)  у пользователя, а затем  СРАЗУ назначьте ему новые лицензии на план внутренних и (или) международных и внутренних звонков. </span><span class="sxs-lookup"><span data-stu-id="853a0-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="853a0-113">При удалении и добавлении лицензий для нескольких пользователей крайне важно удалить лицензии у всех пользователей, использующих Windows PowerShell а затем сразу назначить лицензии всем пользователям, также использующим Windows PowerShell. </span><span class="sxs-lookup"><span data-stu-id="853a0-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="853a0-114">Это позволит не прерывать работу службы при обработке больших объемов пользовательских лицензий.</span><span class="sxs-lookup"><span data-stu-id="853a0-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="853a0-115">Примеры сценариев PowerShell см. в примере назначения лицензий Skype для [бизнеса и Microsoft Teams.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="853a0-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="853a0-116">**Примечание.** Если вы используете для гибридных пользователей локальное подключение  через ДНР, необходимо только назначить лицензию на **телефонную систему.**</span><span class="sxs-lookup"><span data-stu-id="853a0-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="853a0-117">Назначать **план голосовых** звонков не следует.</span><span class="sxs-lookup"><span data-stu-id="853a0-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="853a0-118">Однако если вы включите планы звонков в Microsoft 365 или Office 365 для пользователей Microsoft 365  или Office 365, им все равно потребуется назначить им план внутренних звонков или лицензию на план внутренних и международных звонков. </span><span class="sxs-lookup"><span data-stu-id="853a0-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="853a0-119">См. ["Назначение лицензий Skype для бизнеса и Microsoft Teams".](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="853a0-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="853a0-120">Если вам нужно больше номеров телефонов, обратитесь в службу поддержки продуктов [для бизнеса: справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="853a0-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="853a0-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="853a0-121">Related topics</span></span>
[<span data-ttu-id="853a0-122">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="853a0-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="853a0-123">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="853a0-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="853a0-124">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="853a0-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="853a0-125">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="853a0-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="853a0-126">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="853a0-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
