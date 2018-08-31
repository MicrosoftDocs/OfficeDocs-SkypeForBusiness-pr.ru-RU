---
title: Известные проблемы с планами звонков
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Узнайте, известные проблемы с телефонной для Office 365 (вызов ТСОП) и что можно сделать о них. '
ms.openlocfilehash: 6846fc2e5bd2e1293ca5185a642a813275921ea4
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779301"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="5a83f-103">Известные проблемы с планами звонков</span><span class="sxs-lookup"><span data-stu-id="5a83f-103">Calling Plans known issues</span></span>

<span data-ttu-id="5a83f-104">Тарифные планы в Office 365 являются новой возможностью в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="5a83f-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="5a83f-105">Ниже представлены проблемы, которые они отслеживаемые и активно изучению.</span><span class="sxs-lookup"><span data-stu-id="5a83f-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="5a83f-106">Они потенциально разрешается при обновлении компонента в будущем построения в Office 365 и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="5a83f-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="5a83f-107">Известные проблемы с планами звонков</span><span class="sxs-lookup"><span data-stu-id="5a83f-107">Calling Plans known issues</span></span>

|<span data-ttu-id="5a83f-108">**Известные проблемы**</span><span class="sxs-lookup"><span data-stu-id="5a83f-108">**Known issue**</span></span>|<span data-ttu-id="5a83f-109">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="5a83f-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5a83f-110">Переход от Технический обзор лицензий для производственной лицензии для вызова планы не обновлять автоматически лицензии.</span><span class="sxs-lookup"><span data-stu-id="5a83f-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="5a83f-111">Сначала приобрести новых лицензий так, чтобы они готов к назначению для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5a83f-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="5a83f-112">Удаление лицензии акции (Tech Preview) от пользователя, а затем **сразу ЖЕ** назначить новых лицензий **Планирование внутреннего вызова** и/или **Внутренний и планирование International вызов** для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a83f-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="5a83f-113">Если удаление и добавление лицензий для нескольких пользователей, чрезвычайно важным фактором, что удалить лицензии у всех пользователей с помощью Windows PowerShell и **сразу ЖЕ** назначение лицензий для всех пользователей, также с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a83f-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="5a83f-114">При этом будет убедитесь, что без нарушения в обслуживании при обработке больших объемов назначение лицензии пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a83f-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="5a83f-115">Примеры скриптов PowerShell в разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="5a83f-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="5a83f-116">**Примечание:** При использовании локального подключения к ТСОП для пользователей гибридной вы *только* необходимо назначить лицензии **Телефонной системой** .</span><span class="sxs-lookup"><span data-stu-id="5a83f-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="5a83f-117">**Не** должен также назначить голосовой связи, вызов планирование.</span><span class="sxs-lookup"><span data-stu-id="5a83f-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="5a83f-118">При включении вызов планы в Office 365 для пользователей, которые находятся в Office 365, необходимо по-прежнему назначение **Планирование внутренних звонков** или **Внутренний и вызов планирование International** лицензии для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="5a83f-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="5a83f-119">В разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="5a83f-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5a83f-120">Если вам потребуется получить дополнительные номера телефонов, чем это, пожалуйста, [обратитесь в службу поддержки продуктов бизнес - Admin справки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="5a83f-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="5a83f-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a83f-121">Related topics</span></span>
[<span data-ttu-id="5a83f-122">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="5a83f-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="5a83f-123">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="5a83f-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="5a83f-124">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="5a83f-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="5a83f-125">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="5a83f-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="5a83f-126">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="5a83f-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 