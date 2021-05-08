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
description: 'Узнайте, как настроить режим конфиденциальности для пользователей, чтобы они могли лучше контролировать их доступность. '
ms.openlocfilehash: f8589dfb648693f0c0c4331a1a16119a3d7fe748
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239956"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="8c8bd-103">Настройка режима конфиденциальности присутствия</span><span class="sxs-lookup"><span data-stu-id="8c8bd-103">Configure presence privacy mode</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="8c8bd-104">Центр Microsoft Teams администрирования заменил центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="8c8bd-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="8c8bd-105">Все параметры управления Skype для бизнеса теперь находятся в Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="8c8bd-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="8c8bd-106">Чтобы управлять функциями Skype для бизнеса Teams в Центре администрирования azure [AD,](/azure/active-directory/roles/permissions-reference) вам должна быть назначена роль администратора Azure AD глобальный администратор Skype для бизнеса администратор.</span><span class="sxs-lookup"><span data-stu-id="8c8bd-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="8c8bd-107">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="8c8bd-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="8c8bd-108">Параметр присутствия Skype для бизнеса в Интернете дает людям больше контроля над тем, кто может видеть, доступны ли они, на собрании или нет на месте.</span><span class="sxs-lookup"><span data-stu-id="8c8bd-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="8c8bd-109">Подробные сведения о Skype для бизнеса присутствии и конфиденциальности см. в Skype для бизнеса [Online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="8c8bd-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="8c8bd-110">Выбор параметра присутствия по умолчанию для всех пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="8c8bd-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="8c8bd-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="8c8bd-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="8c8bd-112">Перейдите в центр администрирования Skype для бизнеса Online и **> организации > Общие.**</span><span class="sxs-lookup"><span data-stu-id="8c8bd-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="8c8bd-113">В **режиме конфиденциальности** присутствия выберите этот параметр и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8c8bd-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="8c8bd-114">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="8c8bd-114">**Setting**</span></span>|<span data-ttu-id="8c8bd-115">**Кто может просматривать присутствие пользователя**</span><span class="sxs-lookup"><span data-stu-id="8c8bd-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c8bd-116">**Автоматически отображать сведения о присутствии**</span><span class="sxs-lookup"><span data-stu-id="8c8bd-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="8c8bd-117">Любой пользователь Skype для бизнеса, который не входит в группы конфиденциальности **Внешние** или **Заблокированные**.</span><span class="sxs-lookup"><span data-stu-id="8c8bd-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="8c8bd-118">**Отображение сведений о присутствии только для контактов пользователя**</span><span class="sxs-lookup"><span data-stu-id="8c8bd-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="8c8bd-119">Любой пользователь из списка контактов пользователя,  который не входит в группу конфиденциальности "Внешние" или **"Заблокированные".**</span><span class="sxs-lookup"><span data-stu-id="8c8bd-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="8c8bd-120">Отдельные пользователи могут изменить этот параметр в диалоговом Skype для бизнеса **Параметры.**</span><span class="sxs-lookup"><span data-stu-id="8c8bd-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="8c8bd-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8c8bd-121">Related topics</span></span>
[<span data-ttu-id="8c8bd-122">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8c8bd-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="8c8bd-123">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8c8bd-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
