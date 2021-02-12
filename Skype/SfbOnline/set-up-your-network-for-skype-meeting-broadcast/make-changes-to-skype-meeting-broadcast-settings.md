---
title: Внесение изменений в параметры трансляции собраний Skype для организации
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
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="9563c-103">Внесение изменений в параметры трансляции собраний Skype для организации</span><span class="sxs-lookup"><span data-stu-id="9563c-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9563c-104">Центр администрирования Microsoft Teams заменил Центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="9563c-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="9563c-105">Все параметры управления Skype для бизнеса теперь находятся в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="9563c-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="9563c-106">Чтобы управлять функциями Skype для бизнеса в Центре администрирования Teams, вам должна быть назначена роль администратора [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) глобального администратора или администратор Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9563c-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="9563c-107">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="9563c-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="9563c-108">Вы можете включить трансляцию собраний Skype и внести изменения в параметры и политики для этих собраний.</span><span class="sxs-lookup"><span data-stu-id="9563c-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="9563c-109">**Включить трансляцию собрания Skype** Включает трансляцию собраний Skype.</span><span class="sxs-lookup"><span data-stu-id="9563c-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="9563c-110">После того как вы введете трансляцию собраний Skype, необходимо настроить сеть для [трансляции собраний Skype.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="9563c-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="9563c-111">Сделайте это, если вы хотите проводить вебинары и другие трансляции для людей не из вашей компании.</span><span class="sxs-lookup"><span data-stu-id="9563c-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="9563c-112">**Включить функции предварительной версии трансляции собраний Skype для моей организации** Программы клиента Skype для бизнеса предоставляют вам ранний доступ к новым продуктам и функциям.</span><span class="sxs-lookup"><span data-stu-id="9563c-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="9563c-113">Это позволяет вашей организации посмотреть, что будет в ближайшее время, а также протестировать новые возможности в собственной среде и дать отзыв, прежде чем мы разпустим сборки продуктов для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="9563c-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="9563c-114">Предварительная версия Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9563c-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="9563c-115">**Разрешение организаторам планировать анонимные собрания** Это позволяет организаторам создавать трансляции, позволяющие любому пользователю за пределами организации присоединяться без участия в них.</span><span class="sxs-lookup"><span data-stu-id="9563c-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="9563c-116">**Разрешение записи трансляции собраний** Это позволит вам записывать все собрания, которые должен записывать один из организаторов или один из них.</span><span class="sxs-lookup"><span data-stu-id="9563c-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="9563c-117">**URL-адрес службы поддержки helpdesk для участников** Введите ссылку для участников трансляции собрания, чтобы они могли подключиться к собранию или посетить его.</span><span class="sxs-lookup"><span data-stu-id="9563c-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9563c-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9563c-118">Related topics</span></span>

[<span data-ttu-id="9563c-119">Настройка сети для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="9563c-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
