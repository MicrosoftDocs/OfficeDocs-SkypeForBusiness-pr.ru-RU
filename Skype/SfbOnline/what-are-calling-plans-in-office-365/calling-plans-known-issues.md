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
description: Изучите известные проблемы, связанные с тарифным планом по КОММУТИРУЕМой телефонной связи и действиями, которые вы можете сделать.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220739"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="61750-103">Известные проблемы планов звонков</span><span class="sxs-lookup"><span data-stu-id="61750-103">Calling Plans known issues</span></span>

<span data-ttu-id="61750-104">Планы звонков — это новая функция, которую можно найти в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="61750-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="61750-105">Ниже перечислены проблемы, которые отслеживаются и активно изучаются.</span><span class="sxs-lookup"><span data-stu-id="61750-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="61750-106">Они будут потенциально разрешены, когда функция будет обновлена в последующих сборках.</span><span class="sxs-lookup"><span data-stu-id="61750-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="61750-107">Известные проблемы планов звонков</span><span class="sxs-lookup"><span data-stu-id="61750-107">Calling Plans known issues</span></span>

|<span data-ttu-id="61750-108">**Известная ошибка**</span><span class="sxs-lookup"><span data-stu-id="61750-108">**Known issue**</span></span>|<span data-ttu-id="61750-109">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="61750-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61750-110">Переход с лицензий на техническую версию на производственные лицензии на планы звонков не обновляет лицензию автоматически.</span><span class="sxs-lookup"><span data-stu-id="61750-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="61750-111">Сначала приобретите новые лицензии, чтобы они были готовы к назначению вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="61750-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="61750-112">Удалите лицензию рекламный (ознакомительная версия) от пользователя, а затем **немедленно** назначьте новый **план внутренних звонков** и (или) лицензиям на **внутренние и международные звонки** для пользователя.</span><span class="sxs-lookup"><span data-stu-id="61750-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="61750-113">При удалении и добавлении лицензий для нескольких пользователей чрезвычайно важно удалить лицензии всех пользователей с помощью Windows PowerShell, а затем **немедленно** назначить лицензии для всех пользователей также с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61750-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="61750-114">Это гарантирует, что при обработке больших объемов назначений лицензий пользователей не происходит нарушение обслуживания.</span><span class="sxs-lookup"><span data-stu-id="61750-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="61750-115">Пример сценариев PowerShell приведен в разделе [Назначение лицензий Skype для бизнеса и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="61750-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="61750-116">**Примечание.** Если вы используете локальную сеть PSTN для гибридных пользователей *, вам нужно* назначить лицензию на **телефонную систему** .</span><span class="sxs-lookup"><span data-stu-id="61750-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="61750-117">Вы также **не** должны назначать план голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="61750-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="61750-118">Тем не менее, если вы включаете планы звонков в Microsoft 365 или Office 365 для пользователей, которые находятся в Microsoft 365 или Office 365, необходимо по-прежнему назначать **план внутренних звонков** или лицензию на **внутренние и международные звонки** для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="61750-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="61750-119">Смотрите раздел [Назначение лицензий Skype для бизнеса и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="61750-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="61750-120">Если вам нужно получить больше номеров телефонов, [обратитесь в службу поддержки для бизнес-продуктов — Справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="61750-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="61750-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="61750-121">Related topics</span></span>
[<span data-ttu-id="61750-122">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="61750-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="61750-123">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="61750-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="61750-124">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="61750-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="61750-125">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="61750-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="61750-126">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="61750-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
