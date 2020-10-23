---
title: Настройка режима конфиденциальности присутствия
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.OrgPresencePrivacy
description: 'Узнайте, как настроить режим конфиденциальности для пользователей, чтобы они могли лучше управлять тем, как пользователи видят их доступность. '
ms.openlocfilehash: f0f9237f701be219a9cbce9a44704cbb582f48d4
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739187"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="fa226-103">Настройка режима конфиденциальности присутствия</span><span class="sxs-lookup"><span data-stu-id="fa226-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa226-104">Центр администрирования Microsoft Teams заменяет центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="fa226-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="fa226-105">Все параметры, необходимые для управления Skype для бизнеса, теперь находятся в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="fa226-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="fa226-106">Дополнительные сведения можно найти в разделе [Управление параметрами Skype для бизнеса в центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="fa226-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="fa226-107">Параметр присутствия в Skype для бизнеса Online позволяет людям больше управлять тем, кто может просматривать их доступность, на собрании и вне офиса.</span><span class="sxs-lookup"><span data-stu-id="fa226-107">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="fa226-108">Подробные сведения о присутствии и параметрах конфиденциальности в Skype для бизнеса можно найти [в разделе Настройка присутствия в Skype для бизнеса Online](configure-presence-in-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="fa226-108">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="fa226-109">Выбор параметра присутствия по умолчанию в Интернете для всех пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="fa226-109">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="fa226-110"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="fa226-110"><a name="__top"> </a></span></span>

1. <span data-ttu-id="fa226-111">Перейдите в центр администрирования Skype для бизнеса Online > **организации > общие**.</span><span class="sxs-lookup"><span data-stu-id="fa226-111">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="fa226-112">В разделе **режим конфиденциальности присутствия**выберите параметр, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fa226-112">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="fa226-113">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="fa226-113">**Setting**</span></span>|<span data-ttu-id="fa226-114">**Кто может просматривать сведения о присутствии пользователя**</span><span class="sxs-lookup"><span data-stu-id="fa226-114">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa226-115">**Автоматически отображать сведения о присутствии**</span><span class="sxs-lookup"><span data-stu-id="fa226-115">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="fa226-116">Любой пользователь Skype для бизнеса, который не входит в группы конфиденциальности **Внешние** или **Заблокированные**.</span><span class="sxs-lookup"><span data-stu-id="fa226-116">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="fa226-117">**Отображение сведений о присутствии только для контактов пользователя**</span><span class="sxs-lookup"><span data-stu-id="fa226-117">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="fa226-118">Любой пользователь в списке контактов пользователя, который не входит в группу конфиденциальности с **внешней** или **заблокированной** учетной записью.</span><span class="sxs-lookup"><span data-stu-id="fa226-118">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="fa226-119">Отдельные пользователи могут изменить этот параметр в диалоговом окне " **Параметры** " в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="fa226-119">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="fa226-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fa226-120">Related topics</span></span>
[<span data-ttu-id="fa226-121">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fa226-121">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fa226-122">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fa226-122">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
