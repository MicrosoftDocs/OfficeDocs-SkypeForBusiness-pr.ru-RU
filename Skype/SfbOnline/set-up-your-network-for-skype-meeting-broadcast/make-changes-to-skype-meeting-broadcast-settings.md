---
title: Внесение изменений в параметры трансляции собраний Skype для Организации
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
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
- SMB
- ms.lync.lac.BroadcastMeetings
description: Вы можете включить трансляцию собраний Skype и внести изменения в параметры и политики для этих собраний.
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753414"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="23355-103">Внесение изменений в параметры трансляции собраний Skype для Организации</span><span class="sxs-lookup"><span data-stu-id="23355-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23355-104">Центр администрирования Microsoft Teams заменяет центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="23355-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="23355-105">Все параметры, необходимые для управления Skype для бизнеса, теперь находятся в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="23355-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="23355-106">Для управления функциями Skype для бизнеса в центре администрирования Teams необходимо назначить [роль администратора Azure Active Directory](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) для администратора глобального администратора или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="23355-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="23355-107">Дополнительные сведения можно найти в разделе [Управление параметрами Skype для бизнеса в центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="23355-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="23355-108">Вы можете включить трансляцию собраний Skype и внести изменения в параметры и политики для этих собраний.</span><span class="sxs-lookup"><span data-stu-id="23355-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="23355-109">**Включение трансляции собраний Skype** Включение трансляции собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="23355-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="23355-110">После включения трансляции собраний Skype необходимо [настроить сеть для трансляции собраний Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="23355-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="23355-111">Если вы хотите хранить семинары и другие трансляции для пользователей за пределами вашей организации, выполните это действие.</span><span class="sxs-lookup"><span data-stu-id="23355-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="23355-112">**Включение функций предварительной версии трансляции собраний Skype для моей организации** Программы для клиентов Skype для бизнеса предоставляют вам более ранний доступ к новым продуктам и функциям.</span><span class="sxs-lookup"><span data-stu-id="23355-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="23355-113">Это даст вашей организации краткий обзор того, что поступает, и возможность протестировать новые функции в собственной среде и оставить отзыв перед тем, как мы выпуским сборки продуктов в общедоступные.</span><span class="sxs-lookup"><span data-stu-id="23355-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="23355-114">Skype для бизнеса (ознакомительная версия)</span><span class="sxs-lookup"><span data-stu-id="23355-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="23355-115">**Разрешение организаторов для планирования анонимных собраний** Это позволяет организаторов создавать широковещательные мероприятия, позволяющие любому пользователю за пределами организации присоединиться без необходимости входа.</span><span class="sxs-lookup"><span data-stu-id="23355-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="23355-116">**Разрешение записи широковещательных собраний** Это позволит любому собранию, которое вы хотите записать, выступающее или организатором.</span><span class="sxs-lookup"><span data-stu-id="23355-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="23355-117">**URL-адрес поддержки службы поддержки для участников** Введите ссылку для участников широковещательного показа собрания, если вам нужна помощь по подключению к собранию или участию на нем.</span><span class="sxs-lookup"><span data-stu-id="23355-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="23355-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="23355-118">Related topics</span></span>

[<span data-ttu-id="23355-119">Настройка сети для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="23355-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
