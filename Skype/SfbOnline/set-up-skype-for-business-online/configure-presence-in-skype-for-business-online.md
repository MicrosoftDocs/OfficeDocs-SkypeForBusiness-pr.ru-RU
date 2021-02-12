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
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="c6992-103">Настройка присутствия в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c6992-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6992-104">Центр администрирования Microsoft Teams заменил Центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="c6992-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="c6992-105">Все параметры управления Skype для бизнеса теперь находятся в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="c6992-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="c6992-106">Чтобы управлять функциями Skype для бизнеса в Центре администрирования Teams, вам должна быть назначена роль администратора [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) глобального администратора или администратор Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c6992-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="c6992-107">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="c6992-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="c6992-108">По умолчанию все, кто может общаться с одним из пользователей в вашей организации с помощью Skype для бизнеса, также могут видеть, находится ли этот человек в сети.</span><span class="sxs-lookup"><span data-stu-id="c6992-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="c6992-109">Skype для бизнеса показывает, доступен ли человек в сети, на собрании, в автономном режиме или по другому индикатору.</span><span class="sxs-lookup"><span data-stu-id="c6992-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Пример сетевого статуса человека в Skype для бизнеса.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="c6992-111">Как администратор **[для](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** всех пользователей в вашей компании, вы можете выбрать, кто может увидеть их сетевое присутствие в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c6992-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="c6992-112">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="c6992-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="c6992-113">Перейдите в Центр администрирования > **центрах**  >  **администрирования Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="c6992-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="c6992-114">В Центре **администрирования Skype для бизнеса выберите** **организацию.**</span><span class="sxs-lookup"><span data-stu-id="c6992-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="c6992-115">В **режиме конфиденциальности** присутствия выберите один из следующих параметров и выберите "Сохранить". </span><span class="sxs-lookup"><span data-stu-id="c6992-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="c6992-116">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="c6992-116">**Setting**</span></span>|<span data-ttu-id="c6992-117">**Кто может просматривать присутствие пользователя**</span><span class="sxs-lookup"><span data-stu-id="c6992-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6992-118">**Автоматически отображать сведения о присутствии**</span><span class="sxs-lookup"><span data-stu-id="c6992-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="c6992-119">Любой пользователь Skype для бизнеса в вашей компании, не  добавленный в список внешних или заблокированных пользователей, сможет видеть его сетевое присутствие. </span><span class="sxs-lookup"><span data-stu-id="c6992-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="c6992-120">**Отображение сведений о присутствии только для контактов пользователя**</span><span class="sxs-lookup"><span data-stu-id="c6992-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="c6992-121">Любой человек из списка контактов, которого он  не добавил в свой список внешних или **заблокированных.**</span><span class="sxs-lookup"><span data-stu-id="c6992-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="c6992-122">Пользователи могут переопределять параметры, заданные по умолчанию в приложении Skype для бизнеса: **"Параметры"**  >  **"Параметры".**  >  </span><span class="sxs-lookup"><span data-stu-id="c6992-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="c6992-123">Сведения о том, что пользователи могут изменять в Skype для бизнеса, см. в указанных здесь статьях.</span><span class="sxs-lookup"><span data-stu-id="c6992-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="c6992-124">Управление доступом к сведениям о присутствии в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c6992-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="c6992-125">Настройка параметров состояния в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c6992-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="c6992-126">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c6992-126">Related topics</span></span>

[<span data-ttu-id="c6992-127">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c6992-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="c6992-128">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c6992-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


