---
title: Назначение, изменение мест расположения для экстренного реагирования для пользователей
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: В этой статье объясняется, как назначить или изменить место расположения для экстренного реагирования для пользователей в вашей организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5b13cf5d4b4a0cf22077318e3c2c2196840f66e
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232470"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="fe4d4-103">Назначение или изменение местоположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="fe4d4-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="fe4d4-104">Каждый активный телефонный номер должен иметь соответствующее расположение для экстренных случаев при назначении пользователю номера телефона.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="fe4d4-105">(Вы связываете этот адрес при получении номера телефона в Office 365 или при переносе номера телефона.) При связывании номера с местом для экстренного реагирования вы также можете добавить место, чтобы указать более точное расположение в пределах физического места.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="fe4d4-106">Место может представлять собой этаж, здание крыло или номер Office, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="fe4d4-107">Вы можете использовать неограниченное количество мест для заданной ячейки для экстренного реагирования, и вы можете изменить его в случае, если пользователь перейдет на другой офис или здание.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="fe4d4-108">Например, если пользователь переходит из пола 34 в этаж 35.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="fe4d4-109">Чтобы узнать, как получить тарифные планы и оценить их стоимость, ознакомьтесь со статьей [Лицензирование надстроек для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="fe4d4-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="fe4d4-110">Вы можете назначить или изменить место расположения для экстренного реагирования для пользователя в центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fe4d4-111">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe4d4-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fe4d4-112">В левой области навигации центра администрирования Microsoft Teams щелкните номера **голосовых**  >  **телефонов**.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="fe4d4-113">На странице **номера телефонов** выберите в списке номер пользователя, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="fe4d4-114">На панели **редактирования** в разделе **расположение для экстренного**реагирования выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="fe4d4-115">Чтобы назначить место, выполните поиск расположения или места, а затем выберите место в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="fe4d4-116">Чтобы изменить место, уже назначенное пользователю, нажмите **X** , чтобы удалить существующее расположение и место, найти и выбрать место, которое вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="fe4d4-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fe4d4-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="fe4d4-118">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe4d4-118">Using PowerShell</span></span>

<span data-ttu-id="fe4d4-119">Смотрите раздел [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="fe4d4-119">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fe4d4-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fe4d4-120">Related topics</span></span>

- [<span data-ttu-id="fe4d4-121">Управление вызовом экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="fe4d4-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="fe4d4-122">Добавление, изменение и удаление расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="fe4d4-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="fe4d4-123">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="fe4d4-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="fe4d4-124">Назначение или изменение расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="fe4d4-124">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="fe4d4-125">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="fe4d4-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="fe4d4-126">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="fe4d4-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
