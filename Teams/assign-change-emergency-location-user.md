---
title: Назначение или изменение расположения для экстренного реагирования для пользователя
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
description: В этой статье вы узнаете, как назначить или изменить местоположение для экстренного помощи пользователям в организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f2e927e90a7ac6b79d6eb63c807e063ca7d78c7
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788663"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="2e856-103">Назначение или изменение расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="2e856-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="2e856-104">При настройке планов звонков необходимо назначить расположение для экстренного вызова каждому номеру или пользователю.</span><span class="sxs-lookup"><span data-stu-id="2e856-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="2e856-105">В европейских странах местоположение для экстренного звонков связано с номером при его переносе из Microsoft 365 или Office 365 либо при переносе номера в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e856-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2e856-106">В США местоположение для экстренного помощи связано с номером телефона, который назначен пользователю.</span><span class="sxs-lookup"><span data-stu-id="2e856-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="2e856-107">Адрес для экстренного помощи можно изменить, если пользователь, который ему назначен, перемещается в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="2e856-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="2e856-108">Дополнительные информацию о местоположениях и адресах для экстренного вызова см. в подмносях "Что такое местоположения для экстренного помощи, места и маршруты [экстренных вызовов?".](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="2e856-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="2e856-109">Чтобы узнать, как получить планы звонков и сколько они стоят, см. лицензирование [надстройки Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="2e856-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
  
<span data-ttu-id="2e856-110">Вы можете назначить или изменить расположение для экстренного решения для пользователя в Центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e856-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2e856-111">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e856-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="2e856-112">В левой области навигации Центра администрирования Microsoft Teams щелкните **номера**  >  **голосовых телефонов.**</span><span class="sxs-lookup"><span data-stu-id="2e856-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="2e856-113">На странице **"Номера телефонов"** перейдите **на** вкладку "Номера", выберите в списке номер пользователя и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="2e856-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="2e856-114">В области **"Правка"** в **области "Местоположение для экстренного помощи"** сделайте одно из следующего:</span><span class="sxs-lookup"><span data-stu-id="2e856-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="2e856-115">Чтобы назначить местоположение для экстренного помощи, наберите его и выберите его.</span><span class="sxs-lookup"><span data-stu-id="2e856-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="2e856-116">Чтобы изменить уже назначенное пользователю расположение для экстренного помощи, щелкните **X,** чтобы удалить существующее расположение, а затем найдите и выберите нужное расположение.</span><span class="sxs-lookup"><span data-stu-id="2e856-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="2e856-117">В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о телефонном номере, отключите или включите для пользователя электронной почты сведения о **номере телефона.**</span><span class="sxs-lookup"><span data-stu-id="2e856-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="2e856-118">По умолчанию этот режим уже существует.</span><span class="sxs-lookup"><span data-stu-id="2e856-118">By default, this is on.</span></span>

5. <span data-ttu-id="2e856-119">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="2e856-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="2e856-120">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e856-120">Using PowerShell</span></span>

<span data-ttu-id="2e856-121">См. [set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)</span><span class="sxs-lookup"><span data-stu-id="2e856-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="2e856-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2e856-122">Related topics</span></span>

- [<span data-ttu-id="2e856-123">Управление экстренным вызовом</span><span class="sxs-lookup"><span data-stu-id="2e856-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="2e856-124">Добавление, изменение и удаление расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="2e856-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="2e856-125">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="2e856-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="2e856-126">Назначение или изменение места для расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="2e856-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="2e856-127">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="2e856-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="2e856-128">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="2e856-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="2e856-129">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="2e856-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
