---
title: Назначение и изменение мест для экстренного экстренного помощи для пользователей
author: cichur
ms.author: v-cichur
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
description: В этой статье вы узнаете, как назначить или изменить место для экстренного местоположения для пользователей в вашей организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120831"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="b7a60-103">Назначение или изменение расположения для экстренного экстренного помощи для пользователя</span><span class="sxs-lookup"><span data-stu-id="b7a60-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="b7a60-104">Каждый активный номер телефона должен иметь связанное местоположение для экстренного помощи при назначении номера пользователю.</span><span class="sxs-lookup"><span data-stu-id="b7a60-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="b7a60-105">(Адрес связывается при получения номера телефона в Office 365 или при переносе номера.) Если номер связывается с местоположением для экстренного помощи, вы также можете добавить более точное расположение в физическом расположении.</span><span class="sxs-lookup"><span data-stu-id="b7a60-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="b7a60-106">Это может быть этаж, этаж или номер офиса, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="b7a60-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="b7a60-107">Для заданного местоположения для экстренного помощи можно использовать неограниченное количество мест, а также изменить его место при переходе пользователя в другой офис или здание.</span><span class="sxs-lookup"><span data-stu-id="b7a60-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="b7a60-108">Например, если пользователь переходит с 34-го этажа на 35-й.</span><span class="sxs-lookup"><span data-stu-id="b7a60-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="b7a60-109">Чтобы узнать, как получить планы звонков и сколько они стоят, см. лицензирование [надстройки Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="b7a60-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="b7a60-110">Вы можете назначить или изменить расположение для экстренного решения для пользователя в Центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7a60-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b7a60-111">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7a60-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b7a60-112">В левой области навигации Центра администрирования Microsoft Teams щелкните **"Номера**  >  **голосовых телефонов".**</span><span class="sxs-lookup"><span data-stu-id="b7a60-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="b7a60-113">На странице **"Номера телефонов"** перейдите **на** вкладку "Номера", выберите в списке номер пользователя и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="b7a60-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="b7a60-114">В области **"Правка"** в **области "Местоположение для экстренного помощи"** сделайте одно из следующего:</span><span class="sxs-lookup"><span data-stu-id="b7a60-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="b7a60-115">Чтобы назначить место, назначьте его и выберите его в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="b7a60-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="b7a60-116">Чтобы изменить уже назначенное пользователю место, щелкните **X,** чтобы удалить существующее расположение и место, найдите его и выберите нужное место.</span><span class="sxs-lookup"><span data-stu-id="b7a60-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="b7a60-117">В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о номере телефона, отключите или включите для пользователя электронной почты сведения о **телефонном номере.**</span><span class="sxs-lookup"><span data-stu-id="b7a60-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="b7a60-118">По умолчанию этот режим уже существует.</span><span class="sxs-lookup"><span data-stu-id="b7a60-118">By default, this is on.</span></span>

5. <span data-ttu-id="b7a60-119">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b7a60-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="b7a60-120">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7a60-120">Using PowerShell</span></span>

<span data-ttu-id="b7a60-121">См. [set-CsOnlineLisLocation.](/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="b7a60-121">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="b7a60-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b7a60-122">Related topics</span></span>

- [<span data-ttu-id="b7a60-123">Управление экстренным вызовом</span><span class="sxs-lookup"><span data-stu-id="b7a60-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="b7a60-124">Добавление, изменение и удаление расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="b7a60-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="b7a60-125">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="b7a60-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="b7a60-126">Назначение или изменение расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="b7a60-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="b7a60-127">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="b7a60-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="b7a60-128">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="b7a60-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)