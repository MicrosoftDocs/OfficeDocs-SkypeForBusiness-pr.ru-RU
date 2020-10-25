---
title: Настройка присутствия в Skype для бизнеса Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
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
- O365P_OnlinePresenceDesc
description: 'Learn how to set up Skype for Business so you can see the availability of your co-workers. '
ms.openlocfilehash: f2b149a2b6277d356fe4478ee6de12ec6b078f48
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753454"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="87586-103">Настройка присутствия в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="87586-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87586-104">Центр администрирования Microsoft Teams заменяет центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="87586-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="87586-105">Все параметры, необходимые для управления Skype для бизнеса, теперь находятся в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="87586-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="87586-106">Для управления функциями Skype для бизнеса в центре администрирования Teams необходимо назначить [роль администратора Azure Active Directory](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) для администратора глобального администратора или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="87586-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="87586-107">Дополнительные сведения можно найти в разделе [Управление параметрами Skype для бизнеса в центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="87586-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="87586-108">По умолчанию любой пользователь, который может общаться с одним из сотрудников вашей организации с помощью Skype для бизнеса, также сможет узнать, доступен ли этот пользователь в сети.</span><span class="sxs-lookup"><span data-stu-id="87586-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="87586-109">В Skype для бизнеса показано, доступен ли пользователь в сети, на собрании, в автономном режиме или в другом индикаторе.</span><span class="sxs-lookup"><span data-stu-id="87586-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Пример сетевого статуса пользователя в Skype для бизнеса.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="87586-111">**[Администратор](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** может выбрать пользователей, которые видят свое сетевое присутствие в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="87586-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="87586-112">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="87586-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="87586-113">Перейдите в центр администрирования > **"центр администрирования"** в  >  **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="87586-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="87586-114">В **центре администрирования Skype для бизнеса**выберите пункт **Организация**.</span><span class="sxs-lookup"><span data-stu-id="87586-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="87586-115">В разделе **режим конфиденциальности присутствия**выберите один из указанных ниже параметров и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="87586-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="87586-116">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="87586-116">**Setting**</span></span>|<span data-ttu-id="87586-117">**Кто может просматривать сведения о присутствии пользователя**</span><span class="sxs-lookup"><span data-stu-id="87586-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="87586-118">**Автоматически отображать сведения о присутствии**</span><span class="sxs-lookup"><span data-stu-id="87586-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="87586-119">Любой пользователь Skype для бизнеса в вашей организации, который не был добавлен в **внешний** или **заблокированный** список пользователя, может видеть свое присутствие в сети.</span><span class="sxs-lookup"><span data-stu-id="87586-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="87586-120">**Отображение сведений о присутствии только для контактов пользователя**</span><span class="sxs-lookup"><span data-stu-id="87586-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="87586-121">Любой пользователь в списке контактов человека, которого они не добавили в свой **внешний** или **заблокированный** список.</span><span class="sxs-lookup"><span data-stu-id="87586-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="87586-122">Пользователи могут переопределять параметры по умолчанию в приложении Skype для бизнеса: параметры средств **настройки**  >  **Tools**  >  **Options**.</span><span class="sxs-lookup"><span data-stu-id="87586-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="87586-123">Сведения о том, что пользователи могут изменить в Skype для бизнеса, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="87586-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="87586-124">Управление доступом к сведениям о присутствии в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="87586-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="87586-125">Настройка параметров состояния в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="87586-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="87586-126">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="87586-126">Related topics</span></span>

[<span data-ttu-id="87586-127">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="87586-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="87586-128">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="87586-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


