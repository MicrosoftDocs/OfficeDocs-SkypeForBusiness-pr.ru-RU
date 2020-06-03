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
ms.openlocfilehash: f11bfd9762667823b4ec6b2883c9661f9f5754d0
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539506"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="dd69f-103">Назначение или изменение расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="dd69f-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="dd69f-104">Когда вы настраиваете планы звонков, вам нужно назначить место для экстренного номера каждому абоненту или пользователю.</span><span class="sxs-lookup"><span data-stu-id="dd69f-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="dd69f-105">В европейских странах расположение для экстренного реагирования связано с номером телефона, когда вы получаете его из Office 365 или переносите номер телефона в Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd69f-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="dd69f-106">В США расположение для экстренного реагирования связано с номером телефона, когда он назначен пользователю.</span><span class="sxs-lookup"><span data-stu-id="dd69f-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="dd69f-107">Адрес для экстренного реагирования можно изменить, если пользователь, которому он назначен, переместится в новое место.</span><span class="sxs-lookup"><span data-stu-id="dd69f-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="dd69f-108">Дополнительные сведения об адресах и местоположениях для экстренных случаев смотрите в разделе [Управление вызовом экстренной](what-are-emergency-locations-addresses-and-call-routing.md)помощи.</span><span class="sxs-lookup"><span data-stu-id="dd69f-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="dd69f-109">Сведения о том, как получить план звонков и затраты на него, можно найти [в разделе Лицензирование надстроек для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="dd69f-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="dd69f-110">Вы можете назначить или изменить расположение для экстренного реагирования для пользователя в центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd69f-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="dd69f-111">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd69f-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="dd69f-112">В левой области навигации центра администрирования Microsoft Teams щелкните номера **голосовых**  >  **телефонов**.</span><span class="sxs-lookup"><span data-stu-id="dd69f-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="dd69f-113">На странице **номера телефонов** откройте вкладку **числа** , выберите в списке номер пользователя и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="dd69f-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="dd69f-114">На панели **редактирования** в разделе **расположение для экстренного**реагирования выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="dd69f-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="dd69f-115">Чтобы назначить место для экстренного реагирования, выполните поиск и выберите место для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="dd69f-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="dd69f-116">Чтобы изменить расположение для экстренного реагирования, уже назначенное пользователю, нажмите **X** , чтобы удалить существующее расположение, а затем найдите и выберите расположение, которое вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="dd69f-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="dd69f-117">В зависимости от того, хотите ли вы отправлять электронную почту пользователю с данными о номере телефона, отключите или включите **пользователь электронной почты с информацией о номере телефона**.</span><span class="sxs-lookup"><span data-stu-id="dd69f-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="dd69f-118">По умолчанию это включено.</span><span class="sxs-lookup"><span data-stu-id="dd69f-118">By default, this is on.</span></span>

5. <span data-ttu-id="dd69f-119">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="dd69f-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="dd69f-120">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd69f-120">Using PowerShell</span></span>

<span data-ttu-id="dd69f-121">Смотрите раздел [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="dd69f-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="dd69f-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dd69f-122">Related topics</span></span>

- [<span data-ttu-id="dd69f-123">Управление вызовом экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="dd69f-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="dd69f-124">Добавление, изменение и удаление расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="dd69f-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="dd69f-125">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="dd69f-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="dd69f-126">Назначение или изменение места для расположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="dd69f-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="dd69f-127">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="dd69f-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="dd69f-128">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="dd69f-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="dd69f-129">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="dd69f-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
