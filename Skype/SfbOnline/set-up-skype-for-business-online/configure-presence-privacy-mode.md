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
description: 'Узнайте, как настроить режим конфиденциальности для пользователей, чтобы они могли лучше контролировать доступность. '
ms.openlocfilehash: a2b4ed11f1d56927a4bc7eed6ce36b5b04411509
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753444"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="8263f-103">Настройка режима конфиденциальности присутствия</span><span class="sxs-lookup"><span data-stu-id="8263f-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8263f-104">Центр администрирования Microsoft Teams заменил Центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="8263f-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="8263f-105">Все параметры управления Skype для бизнеса теперь находятся в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="8263f-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="8263f-106">Чтобы управлять функциями Skype для бизнеса в Центре администрирования Teams, вам должна быть назначена роль администратора [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) глобального администратора или администратор Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8263f-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="8263f-107">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="8263f-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="8263f-108">Настройка присутствия в Skype для бизнеса Online позволяет людям более контролировать, кто может видеть, доступны ли они, на собрании или нет на работе.</span><span class="sxs-lookup"><span data-stu-id="8263f-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="8263f-109">Подробные сведения о параметрах присутствия и конфиденциальности Skype для бизнеса см. в сведениях о настройке присутствия [в Skype для бизнеса Online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="8263f-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="8263f-110">Выбор параметров сетевого присутствия по умолчанию для всех пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="8263f-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="8263f-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="8263f-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="8263f-112">Перейдите в Центр администрирования Skype для бизнеса Online и > **организации >.**</span><span class="sxs-lookup"><span data-stu-id="8263f-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="8263f-113">В **режиме конфиденциальности присутствия** выберите параметр и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="8263f-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="8263f-114">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="8263f-114">**Setting**</span></span>|<span data-ttu-id="8263f-115">**Кто может просматривать присутствие пользователя**</span><span class="sxs-lookup"><span data-stu-id="8263f-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8263f-116">**Автоматически отображать сведения о присутствии**</span><span class="sxs-lookup"><span data-stu-id="8263f-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="8263f-117">Любой пользователь Skype для бизнеса, который не входит в группы конфиденциальности **Внешние** или **Заблокированные**.</span><span class="sxs-lookup"><span data-stu-id="8263f-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="8263f-118">**Отображение сведений о присутствии только для контактов пользователя**</span><span class="sxs-lookup"><span data-stu-id="8263f-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="8263f-119">Любой пользователь из списка контактов, не  в который входит группа конфиденциальности "Внешние" или **"Заблокированные".**</span><span class="sxs-lookup"><span data-stu-id="8263f-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="8263f-120">Пользователь может изменить этот параметр в диалоговом окне "Параметры Skype **для** бизнеса".</span><span class="sxs-lookup"><span data-stu-id="8263f-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="8263f-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8263f-121">Related topics</span></span>
[<span data-ttu-id="8263f-122">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8263f-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="8263f-123">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8263f-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
