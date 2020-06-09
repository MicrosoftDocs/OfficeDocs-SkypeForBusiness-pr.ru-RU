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
description: В этой статье рассказывается о том, как назначить или изменить расположение для экстренного реагирования для пользователей в Организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 450fe848052af1e331964da3d7b695daf0f1567a
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610998"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="9a652-103">Назначение или изменение расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="9a652-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="9a652-104">Когда вы настраиваете планы звонков, вам нужно назначить место для экстренного номера каждому абоненту или пользователю.</span><span class="sxs-lookup"><span data-stu-id="9a652-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="9a652-105">В европейских странах расположение для экстренного реагирования связано с номером телефона, когда вы получаете его из Microsoft 365 или Office 365 или переносите номер телефона в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a652-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="9a652-106">В США расположение для экстренного реагирования связано с номером телефона, когда он назначен пользователю.</span><span class="sxs-lookup"><span data-stu-id="9a652-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="9a652-107">Адрес для экстренного реагирования можно изменить, если пользователь, которому он назначен, переместится в новое место.</span><span class="sxs-lookup"><span data-stu-id="9a652-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="9a652-108">Для получения дополнительных сведений об адресах и расположениях для экстренного реагирования ознакомьтесь со статьей [что такое места для экстренных случаев, места и маршрут звонков](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="9a652-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="9a652-109">Чтобы узнать, как получить тарифные планы и оценить их стоимость, ознакомьтесь со статьей [Лицензирование надстроек для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="9a652-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="9a652-110">Вы можете назначить или изменить расположение для экстренного реагирования для пользователя в центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a652-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9a652-111">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a652-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9a652-112">В левой области навигации центра администрирования Microsoft Teams щелкните номера **голосовых**  >  **телефонов**.</span><span class="sxs-lookup"><span data-stu-id="9a652-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="9a652-113">На странице **номера телефонов** откройте вкладку **числа** , выберите в списке номер пользователя и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="9a652-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="9a652-114">На панели **редактирования** в разделе **расположение для экстренного**реагирования выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9a652-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="9a652-115">Чтобы назначить место для экстренного реагирования, выполните поиск и выберите место для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="9a652-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="9a652-116">Чтобы изменить расположение для экстренного реагирования, уже назначенное пользователю, нажмите **X** , чтобы удалить существующее расположение, а затем найдите и выберите расположение, которое вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="9a652-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="9a652-117">В зависимости от того, хотите ли вы отправлять электронную почту пользователю с данными о номере телефона, отключите или включите **пользователь электронной почты с информацией о номере телефона**.</span><span class="sxs-lookup"><span data-stu-id="9a652-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="9a652-118">По умолчанию это включено.</span><span class="sxs-lookup"><span data-stu-id="9a652-118">By default, this is on.</span></span>

5. <span data-ttu-id="9a652-119">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="9a652-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="9a652-120">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a652-120">Using PowerShell</span></span>

<span data-ttu-id="9a652-121">Смотрите раздел [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="9a652-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="9a652-122">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="9a652-122">Related topics</span></span>

- [<span data-ttu-id="9a652-123">Управление вызовом экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="9a652-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="9a652-124">Добавление, изменение и удаление расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="9a652-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="9a652-125">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="9a652-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="9a652-126">Назначение или изменение места для расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="9a652-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="9a652-127">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="9a652-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="9a652-128">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="9a652-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="9a652-129">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="9a652-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
