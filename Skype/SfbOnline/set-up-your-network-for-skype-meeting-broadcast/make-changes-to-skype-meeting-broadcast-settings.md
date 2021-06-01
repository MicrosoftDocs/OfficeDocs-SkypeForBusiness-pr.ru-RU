---
title: Внесение изменений Skype параметров трансляции собраний для организации
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
description: Вы можете включить Skype собрания и внести изменения в параметры и политики для этих собраний.
ms.openlocfilehash: fae53601c858bf67db57352e18dbc9799243f996
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238651"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="d8d15-103">Внесение изменений Skype параметров трансляции собраний для организации</span><span class="sxs-lookup"><span data-stu-id="d8d15-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="d8d15-104">Центр Microsoft Teams администрирования заменил центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="d8d15-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="d8d15-105">Все параметры управления Skype для бизнеса теперь находятся в Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="d8d15-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="d8d15-106">Чтобы управлять функциями Skype для бизнеса Teams в Центре администрирования azure [AD,](/azure/active-directory/roles/permissions-reference) вам должна быть назначена роль администратора Azure AD глобальный администратор Skype для бизнеса администратор.</span><span class="sxs-lookup"><span data-stu-id="d8d15-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="d8d15-107">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="d8d15-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="d8d15-108">Вы можете включить Skype собрания и внести изменения в параметры и политики для этих собраний.</span><span class="sxs-lookup"><span data-stu-id="d8d15-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="d8d15-109">**Включить Skype собрания** Включает Skype трансляцию собрания.</span><span class="sxs-lookup"><span data-stu-id="d8d15-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="d8d15-110">После того как Skype трансляцию собрания, необходимо настроить сеть для [Skype трансляции собрания](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="d8d15-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="d8d15-111">Сделайте это, если вы хотите проводить вебинары и другие трансляции для людей за пределами вашей компании.</span><span class="sxs-lookup"><span data-stu-id="d8d15-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="d8d15-112">**Включить Skype трансляции собраний для моей организации** Программы Skype для бизнеса предоставляют ранний доступ к новым продуктам и функциям.</span><span class="sxs-lookup"><span data-stu-id="d8d15-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="d8d15-113">Это позволяет вашей организации с обзором предстоящих выпусков и возможностью протестировать новые функции в собственной среде и дать отзыв перед выпуском сборки продукта для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8d15-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="d8d15-114">Skype для бизнеса предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="d8d15-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="d8d15-115">**Разрешение организаторам планировать анонимные собрания** Это позволяет организаторам создавать трансляции, позволяющие всем пользователям за пределами организации присоединяться к собраниям без требования к входу.</span><span class="sxs-lookup"><span data-stu-id="d8d15-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="d8d15-116">**Разрешение записи трансляции собраний** Это позволяет записывать все собрания, которые должны быть записаны в ходе собрания.</span><span class="sxs-lookup"><span data-stu-id="d8d15-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="d8d15-117">**URL-адрес службы поддержки службы технической поддержки для участников** Введите ссылку для участников трансляции собрания, если им требуется помощь в подключении к трансляции собрания или его посещении.</span><span class="sxs-lookup"><span data-stu-id="d8d15-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d8d15-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d8d15-118">Related topics</span></span>

[<span data-ttu-id="d8d15-119">Настройка сети для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="d8d15-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
