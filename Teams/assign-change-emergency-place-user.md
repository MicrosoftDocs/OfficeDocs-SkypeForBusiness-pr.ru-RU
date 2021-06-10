---
title: Назначение и изменение мест для экстренного размещения для пользователей
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
description: В этой статье вы узнаете, как назначить или изменить расположение для экстренного размещения пользователей в организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120831"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="4e7cd-103">Назначение или изменение местоположения для экстренного экстренного ситуация для пользователя</span><span class="sxs-lookup"><span data-stu-id="4e7cd-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="4e7cd-104">Каждый активный номер телефона должен иметь связанное местоположение для экстренного ситуация при назначении номера пользователю.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="4e7cd-105">(Этот адрес связывается при телефонном номере в Office 365 или при передаче номера телефона.) При связываи номера с местоположением для экстренного ситуация вы также можете добавить более точное расположение в физическом расположении.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="4e7cd-106">В качестве места может быть этаж, здание или номер офиса, в котором находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="4e7cd-107">Вы можете иметь неограниченное количество мест для заданного местоположения для экстренного экстренного ситуация, а также изменить его, если пользователь переходит в другой офис или другое здание.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="4e7cd-108">Например, если пользователь переходит с 34-го этажа на 35-й.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="4e7cd-109">Чтобы узнать, как получить планы звонков и сколько они стоят, см. Teams лицензирования [надстройки.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="4e7cd-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="4e7cd-110">Вы можете назначить или изменить расположение для экстренного ситуация для пользователя в центре администрирования Microsoft Teams с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4e7cd-111">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e7cd-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4e7cd-112">В левой области навигации Центра администрирования Microsoft Teams щелкните **Номера голосовой**  >  **Телефон голосовой Телефон**.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="4e7cd-113">На странице **Телефон номера** щелкните **вкладку** Числа, выберите в списке номер пользователя и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="4e7cd-114">В области **Правка** в области **Местоположение для экстренного ситуация** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="4e7cd-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="4e7cd-115">Чтобы назначить место, найщите его и выберите место в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="4e7cd-116">Чтобы изменить место, которое уже назначено пользователю, щелкните **X,** чтобы удалить существующее расположение и место, найдите его и выберите нужное место.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="4e7cd-117">В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о телефонном номере, отключите или включите отправку электронной почты пользователю со сведениями о **телефонном номере**.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="4e7cd-118">По умолчанию этот режим в том же режиме.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-118">By default, this is on.</span></span>

5. <span data-ttu-id="4e7cd-119">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="4e7cd-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="4e7cd-120">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e7cd-120">Using PowerShell</span></span>

<span data-ttu-id="4e7cd-121">См. [set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="4e7cd-121">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4e7cd-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4e7cd-122">Related topics</span></span>

- [<span data-ttu-id="4e7cd-123">Управление звонками в экстренные службы</span><span class="sxs-lookup"><span data-stu-id="4e7cd-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="4e7cd-124">Добавление, изменение и удаление расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="4e7cd-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="4e7cd-125">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="4e7cd-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="4e7cd-126">Назначение или изменение расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="4e7cd-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="4e7cd-127">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="4e7cd-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="4e7cd-128">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="4e7cd-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)