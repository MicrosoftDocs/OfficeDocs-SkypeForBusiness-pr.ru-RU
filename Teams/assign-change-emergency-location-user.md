---
title: Назначение или изменение расположения для экстренного реагирования для пользователя
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
description: В этой статье вы узнаете, как назначить или изменить местоположение для экстренного ситуация для пользователей в организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102985"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="acc90-103">Назначение или изменение расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="acc90-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="acc90-104">При настройке планов звонков необходимо назначить расположение для экстренного вызова каждому номеру или пользователю.</span><span class="sxs-lookup"><span data-stu-id="acc90-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="acc90-105">В европейских странах местоположение для экстренного звонков связано с номером телефона, который вы получаете из Microsoft 365 или Office 365 или при переносе номера в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="acc90-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="acc90-106">В США местоположение для экстренного ситуация связано с номером телефона, который назначен пользователю.</span><span class="sxs-lookup"><span data-stu-id="acc90-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="acc90-107">Адрес для экстренного устранения проблем можно изменить, если пользователь, назначенный ему, перемещается в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="acc90-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="acc90-108">Дополнительные информацию об адресах и местоположениях для экстренного вызова см. в этой [теме.](./what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="acc90-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](./what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="acc90-109">Чтобы узнать, как получить планы звонков и сколько они стоят, см. Teams лицензирования [надстройки.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="acc90-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="acc90-110">Вы можете назначить или изменить местоположение для экстренного ситуация для пользователя в центре Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="acc90-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="acc90-111">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="acc90-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="acc90-112">В левой области навигации Центра администрирования Microsoft Teams щелкните **Номера голосовой**  >  **Телефон голосовой Телефон**.</span><span class="sxs-lookup"><span data-stu-id="acc90-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="acc90-113">На странице **Телефон номера** щелкните **вкладку** Числа, выберите в списке номер пользователя и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="acc90-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="acc90-114">В области **Правка** в области **Местоположение для экстренного ситуация** сделайте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="acc90-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="acc90-115">Чтобы назначить местоположение для экстренного ситуация, найди его и выберите его.</span><span class="sxs-lookup"><span data-stu-id="acc90-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="acc90-116">Чтобы изменить местоположение для экстренного устранения проблемы, которое уже назначено пользователю, щелкните **X,** чтобы удалить существующее, а затем найдите и выберите нужное расположение.</span><span class="sxs-lookup"><span data-stu-id="acc90-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="acc90-117">В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о телефонном номере, отключите или включите отправку электронной почты пользователю со сведениями о **телефонном номере**.</span><span class="sxs-lookup"><span data-stu-id="acc90-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="acc90-118">По умолчанию этот режим в том же режиме.</span><span class="sxs-lookup"><span data-stu-id="acc90-118">By default, this is on.</span></span>

5. <span data-ttu-id="acc90-119">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="acc90-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="acc90-120">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="acc90-120">Using PowerShell</span></span>

<span data-ttu-id="acc90-121">См. [set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser)</span><span class="sxs-lookup"><span data-stu-id="acc90-121">See [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="acc90-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="acc90-122">Related topics</span></span>

- [<span data-ttu-id="acc90-123">Управление звонками экстренных служб</span><span class="sxs-lookup"><span data-stu-id="acc90-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="acc90-124">Добавление, изменение и удаление расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="acc90-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="acc90-125">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="acc90-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="acc90-126">Назначение или изменение места для расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="acc90-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="acc90-127">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="acc90-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="acc90-128">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="acc90-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)
- [<span data-ttu-id="acc90-129">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="acc90-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)