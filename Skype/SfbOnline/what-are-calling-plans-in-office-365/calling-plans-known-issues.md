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
description: Узнайте о известных проблемах с планом звонков по ЗВОНКОВ и о том, как с ними можно работать.
ms.openlocfilehash: 9c660ee3b173f104e26816460db45c5bcf400837
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238025"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="611cd-103">Известные проблемы планов звонков</span><span class="sxs-lookup"><span data-stu-id="611cd-103">Calling Plans known issues</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="611cd-104">Планы звонков — это новая функция в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="611cd-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="611cd-105">Ниже следуют текущие проблемы, которые отслеживаются и активно изучаете.</span><span class="sxs-lookup"><span data-stu-id="611cd-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="611cd-106">Они могут быть устранены при обновлении этой функции в будущих сборках.</span><span class="sxs-lookup"><span data-stu-id="611cd-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="611cd-107">Известные проблемы планов звонков</span><span class="sxs-lookup"><span data-stu-id="611cd-107">Calling Plans known issues</span></span>

|<span data-ttu-id="611cd-108">**Известная проблема**</span><span class="sxs-lookup"><span data-stu-id="611cd-108">**Known issue**</span></span>|<span data-ttu-id="611cd-109">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="611cd-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="611cd-110">При переходе с лицензий На техническую версию на лицензии для планов звонков лицензия не обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="611cd-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="611cd-111">Сначала приобретите новые лицензии, чтобы они были готовы к назначению пользователям.</span><span class="sxs-lookup"><span data-stu-id="611cd-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="611cd-112">Удалите у пользователя рекламные лицензии (Техническая версия),  а затем НЕМЕДЛЕННО  назначьте ему новые лицензии на план внутренних звонков и(или) план внутренних и международных звонков. </span><span class="sxs-lookup"><span data-stu-id="611cd-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="611cd-113">При удалении и добавлении лицензий для нескольких пользователей очень важно удалить лицензии у всех  пользователей, использующих Windows PowerShell, а затем сразу назначить лицензии всем пользователям, также использующим Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="611cd-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="611cd-114">Это гарантирует отсутствие прерываний в работе службы при обработке больших объемов пользовательских лицензий.</span><span class="sxs-lookup"><span data-stu-id="611cd-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="611cd-115">Примеры сценариев PowerShell см. в Skype для бизнеса [и Microsoft Teams лицензий.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="611cd-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="611cd-116">**Примечание.** Если вы используете для гибридных пользователей локальное подключение  к ОКП, необходимо назначить телефонная система **лицензию.**</span><span class="sxs-lookup"><span data-stu-id="611cd-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="611cd-117">Назначать **план голосовых** звонков не нужно.</span><span class="sxs-lookup"><span data-stu-id="611cd-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="611cd-118">Однако если вы включите планы звонков в Microsoft 365 или Office 365 для пользователей, которые находятся в Microsoft 365 или  Office 365, вам  потребуется назначить им план внутренних звонков или план внутренних и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="611cd-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="611cd-119">См. [Skype для бизнеса и Microsoft Teams лицензий.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="611cd-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="611cd-120">Если вам нужно получить больше номеров телефонов, обратитесь в службу поддержки [бизнес-продуктов— справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="611cd-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="611cd-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="611cd-121">Related topics</span></span>
[<span data-ttu-id="611cd-122">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="611cd-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="611cd-123">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="611cd-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="611cd-124">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="611cd-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="611cd-125">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="611cd-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="611cd-126">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="611cd-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
