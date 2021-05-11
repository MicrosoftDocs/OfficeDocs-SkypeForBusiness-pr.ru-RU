---
title: Управление политиками идентификации вызывающего абонента в Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать политики ИД вызываемого Microsoft Teams и управлять ими, чтобы изменить или заблокировать Teams пользователей в организации.
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308378"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="5ae92-103">Управление политиками идентификации вызывающего абонента в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ae92-103">Manage caller ID policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="5ae92-104">Чтобы установить для ИД звонящая номер телефона учетной записи ресурса и имя вызываемой стороны, используйте командлеты PowerShell New-CsCallingLineIdentity или Set-CsCallingLineIdentity в модуле Teams PowerShell 2.3.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="5ae92-104">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="5ae92-105">(В настоящее время эти параметры недоступны в Центре Microsoft Teams администрирования.)</span><span class="sxs-lookup"><span data-stu-id="5ae92-105">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="5ae92-106">По умолчанию, когда Teams звонит на номер телефона ЗВОНКОВ, Teams номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="5ae92-106">By default, when a Teams user makes a call to a PSTN phone, the phone number of the Teams user is visible.</span></span> <span data-ttu-id="5ae92-107">Точно так же, когда звоня Teams ЗВОНКОВ через ПСПС, номер телефона этого звоня будет виден.</span><span class="sxs-lookup"><span data-stu-id="5ae92-107">Likewise, when a PSTN caller makes a call to a Teams user, the PSTN caller's phone number is visible.</span></span>

<span data-ttu-id="5ae92-108">Администратор может изменить или заблокировать его (или изменить или заблокировать его) с помощью политик ИД вызываемой связи.</span><span class="sxs-lookup"><span data-stu-id="5ae92-108">As an administrator, you can use caller ID policies to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="5ae92-109">С помощью политик ИД звонящая можно отображать альтернативный номер телефона для пользователей Teams в организации, блокировать исходящие телефонные номера, блокировать отображение входящих номеров или устанавливать имя вызываемой стороны (CNAM).</span><span class="sxs-lookup"><span data-stu-id="5ae92-109">You can use caller ID policies to display an alternate phone number for Teams users in your organization, block the outbound phone number, block an incoming number from being displayed, or set the Calling Party Name (CNAM).</span></span> <span data-ttu-id="5ae92-110">Например, когда пользователь звонит, вы можете изменить его ИД, чтобы вместо номера телефона пользователя отображались основной номер телефона и название организации организации.</span><span class="sxs-lookup"><span data-stu-id="5ae92-110">For example, when a user makes a call, you can change the caller ID to display your organization's main phone number and company name instead of the user's phone number.</span></span>

<span data-ttu-id="5ae92-111">Управлять политиками ИД вызываемого звоня можно в центре администрирования Microsoft Teams   >   голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="5ae92-111">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="5ae92-112">Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="5ae92-112">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="5ae92-113">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="5ae92-113">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="5ae92-114">Создание настраиваемой политики ИД вызываемого звоня</span><span class="sxs-lookup"><span data-stu-id="5ae92-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="5ae92-115">В левой области навигации центра администрирования Microsoft Teams политики ИД голосового  >  **звоня.**</span><span class="sxs-lookup"><span data-stu-id="5ae92-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="5ae92-116">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5ae92-116">Click **Add**.</span></span> <br>
<span data-ttu-id="5ae92-117">![Снимок экрана: страница политики "Новый ИД звоня человека" в Центре администрирования](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="5ae92-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="5ae92-118">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="5ae92-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="5ae92-119">В этом окте выберите нужные параметры:</span><span class="sxs-lookup"><span data-stu-id="5ae92-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="5ae92-120">**Блокировать ИД входящих звонков:** включите этот параметр, чтобы не отображаться ИД звонящая при входящих звонках.</span><span class="sxs-lookup"><span data-stu-id="5ae92-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="5ae92-121">**Переопределение** политики ИД вызываемого пользователя: включите этот параметр, чтобы позволить пользователям переопределять параметры политики, касающиеся отображения номера для вызывающих пользователей.</span><span class="sxs-lookup"><span data-stu-id="5ae92-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="5ae92-122">Это означает, что пользователи могут выбрать, следует ли отображать свой ИД вызываемой связи.</span><span class="sxs-lookup"><span data-stu-id="5ae92-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="5ae92-123">Дополнительные сведения см. в [этой](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)ссылке.</span><span class="sxs-lookup"><span data-stu-id="5ae92-123">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="5ae92-124">**Замените ИД вызываемого:** установите для пользователей, чтобы он отображался для пользователей, выбрав один из следующих ок.</span><span class="sxs-lookup"><span data-stu-id="5ae92-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="5ae92-125">**Номер пользователя:** отображает номер пользователя.</span><span class="sxs-lookup"><span data-stu-id="5ae92-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="5ae92-126">**Номер службы:** позволяет настроить номер телефона службы для отображения в качестве ИД звоня.</span><span class="sxs-lookup"><span data-stu-id="5ae92-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="5ae92-127">**Анонимный:** отображает ИД звоняного как анонимный.</span><span class="sxs-lookup"><span data-stu-id="5ae92-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="5ae92-128">**Замените ИД вызываемого** пользователя этим номером службы: выберите номер службы, чтобы заменить его.</span><span class="sxs-lookup"><span data-stu-id="5ae92-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="5ae92-129">Этот параметр доступен, если  вы выбрали Номер службы в **Заменить ИД вызываемого вызова на**.</span><span class="sxs-lookup"><span data-stu-id="5ae92-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="5ae92-130">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5ae92-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="5ae92-131">Изменение политики ИД вызываемого звоня</span><span class="sxs-lookup"><span data-stu-id="5ae92-131">Edit a caller ID policy</span></span>

<span data-ttu-id="5ae92-132">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="5ae92-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="5ae92-133">В левой области навигации центра администрирования Microsoft Teams политики ИД голосового  >  **звоня.**</span><span class="sxs-lookup"><span data-stu-id="5ae92-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="5ae92-134">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5ae92-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="5ae92-135">Измените нужные параметры и нажмите кнопку **Сохранить.**</span><span class="sxs-lookup"><span data-stu-id="5ae92-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="5ae92-136">Назначение пользовательской политики ИД вызываемого пользователя пользователям</span><span class="sxs-lookup"><span data-stu-id="5ae92-136">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="5ae92-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5ae92-137">Related topics</span></span>

[<span data-ttu-id="5ae92-138">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="5ae92-138">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="5ae92-139">Set-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="5ae92-139">Set-CsCallingLineIdentity</span></span>](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="5ae92-140">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="5ae92-140">Assign policies to your users in Teams</span></span>](assign-policies.md)